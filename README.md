# Dragon dataset (cropped)

Download `dragon_1024_c656.zip` from the [releases page](https://github.com/Hineven/temp_repo/releases) of this repository. It is the Dragon dataset that the paper's models were trained and evaluated on. It unpacks to one folder, `easydragonsphere_vol7b_tief_1024_c656/`, with 500 views at 1024×1024 in the 400/50/50 split, `mesh.ply`, `meta.json` (IOR 1.38), and the `transforms_*.json` files.

With the code package and the Dragon checkpoint, run from the package root:

```bash
python -m volapp.predict --ckpt <dragon ckpt.pt> --dataset <path>/easydragonsphere_vol7b_tief_1024_c656 --split test --out outputs/dragon_torch
python -m volapp.evaluate --pred-dir outputs/dragon_torch --dataset <path>/easydragonsphere_vol7b_tief_1024_c656 --split test
```

The raw full-frame set `dataset_easydragonsphere_vol7b_tief_hw1` (45° field of view) gives different numbers. It holds the same renders with a wider framing: PSNR matches, but SSIM and LPIPS cover the whole frame and do not match the paper.
