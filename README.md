# C-ESRGAN-AI-Upscaler
 - Uses ESRGAN SuperRes AI to Upscale &amp; Enhance Videos, Gifs, and Images

Performance Note
Very slow, but very good quality upscale. This tool uses your GPU to upscale individual frames via ESRGAN and then re-encodes them into a high-fidelity video file.

A LOT LESS VRAM USAGE THAN PYTHON VERSION

WORKS BEST FOR 40 & 50 SERIES CARDS


--- Settings.json ---
crf

Maps to the NVENC QP (Quantization Parameter).

Lower = Higher Quality.

0 = Mathematically Lossless.

Note: At 0, the bitrate is extremely high. Windows Media Player may struggle to play it, but it is perfect for archival or uploading to YouTube.

speed_preset

NVENC-specific speed/quality balance.

Options: p1 (Fastest) to p7 (Slowest/Best Quality).

Note: The standard CPU presets (e.g., veryslow) are replaced by these p values for GPU encoding.

worker_count

The number of parallel instances of ESRGAN running.

Higher numbers process more frames at once but require more VRAM.

--- ESRGAN.json ---
model_name

The specific AI model used for the upscale.

Main Model: realesrgan-x4plus (Best for general high-detail photos/videos).

Anime Model: realesrgan-x4plus-anime (Optimized for 2D art).

Anime Video Models: realesr-animevideov3-x2 / x3 / x4 (Faster, specialized for animation).

face_enhance

Uses GFPGAN to reconstruct and sharpen faces that may be blurry in the original source.

tile_size

Breaks the image into smaller "tiles" to save VRAM.

If you get "Out of Memory" errors on large 4K/8K frames, lower this number (e.g., 256 or 512).

Set to 0 for auto-detect.

pre_pad

Adds a border of pixels around tiles to prevent "seam" lines from appearing between tiles. Default is usually 10.

gpu_id

Specifies which GPU to use if you have multiple. 0 is the default primary GPU.

tta_mode

Test-Time Augmentation.

Slows down the process significantly but can slightly improve quality by upscaling multiple versions of the same frame and merging them.
