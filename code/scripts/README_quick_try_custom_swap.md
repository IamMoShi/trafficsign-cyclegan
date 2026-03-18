# Quick Try: Custom Sign Swap

This helper prepares a small CycleGAN-ready dataset and config from two image folders:

- Domain X: real traffic-sign images
- Domain Y: custom sign images

It converts everything to square `.png` files, creates train/test splits, and writes a config JSON.

## Requirements

- `ffmpeg` available in `PATH`
- Python 3.x

## Run

```bash
cd /home/moshi/Documents/Projects/diocles/trafficsign-cyclegan
python code/scripts/quick_try_custom_swap.py \
  --source-x datasets/diocles-acquisition-1 \
  --source-y /absolute/path/to/custom-signs \
  --work-dir datasets/custom_swap_quick \
  --config-path configs/custom_swap_quick_config.json \
  --image-size 128 \
  --max-per-domain 300 \
  --clean
```

The script prints the next `train` and `run` commands when done.

## Notes

- This repo's `input.py` uses `decode_png`, so PNG conversion is required.
- If training fails due to TensorFlow/Python compatibility, keep the generated dataset/config and run training in a compatible environment.

