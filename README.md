# sucorn_loras
This repository contains Stable Diffusion Low-Rank Adaptations (LoRAs) from datasets collected through [sucorn](https://github.com/speckly/sucorn)
This is currently a work in progress

# Usage
Filenames will end with `.safetensors`. Filenames will also contain a number, where n is the epoch number where the checkpoint is saved. It is recommended to download the one with the highest number.
The location of your download depends on where you are hosting Stable Diffusion on. For example, [AUTOMATIC1111's](https://github.com/AUTOMATIC1111/stable-diffusion-webui) default location for LoRA is `stable-diffusion-webui/models/Lora`

# Training parameters
`space-hopper` series only for SD 1.5
Activation tag: space hopper, bouncing
Remove tags: `i forgor :skullemoji:`
Date: 18 July 2024
```
batch_size: 2
resolution: (512, 512)
enable_bucket: True
min_bucket_reso: 256
max_bucket_reso: 1024
bucket_reso_steps: 64
bucket_no_upscale: False

image_count: 416
num_repeats: 1
shuffle_caption: True
keep_tokens: 1
caption_dropout_rate: 0.0
caption_dropout_every_n_epoches: 0
caption_tag_dropout_rate: 0.0
color_aug: False
flip_aug: False
face_crop_aug_range: None
random_crop: False
token_warmup_min: 1,
token_warmup_step: 0,
is_reg: False
class_tokens: None
caption_extension: .txt
```

`overfitting-test`
Activation tag: bouncing on space hopper
Remove tags: space hopper, balloon, ball, gym ball, beach ball, volleyball, sitting
Date: 20 July 2024
```
batch_size: 3
resolution: (512, 512)
enable_bucket: True
min_bucket_reso: 256
max_bucket_reso: 1024
bucket_reso_steps: 64
bucket_no_upscale: False

image_count: 767
num_repeats: 10
shuffle_caption: True
keep_tokens: 1
caption_dropout_rate: 0.0
caption_dropout_every_n_epoches: 0
caption_tag_dropout_rate: 0.0
color_aug: False
flip_aug: False
face_crop_aug_range: None
random_crop: False
token_warmup_min: 1,
token_warmup_step: 0,
is_reg: False
class_tokens: None
caption_extension: .txt
```
# Example Output
Can be better when I have the time :)

![image](https://github.com/user-attachments/assets/2edca16b-62aa-4c36-9c8c-f940c1b613fd)
Generation parameters:
```
1girl, absurdres, high resolution, masterpiece, fubuki, white blouse, [midriff::12], detached sleeves, black short shorts, blue neckerchief, thigh strap, single thighhigh, white hair, single side braid, bouncing, sitting, jumping, :D, space hopper, garden, motion lines, <lora:fubuki:1> <lora:space_hopper:1>
Negative prompt: bad fingers
Steps: 20, Sampler: DPM++ 2M SDE, Schedule type: Karras, CFG scale: 7, Seed: 2245042501, Size: 512x768, Model hash: d4c1719023, Model: animekawa_v10, VAE hash: 735e4c3a44, VAE: vaeFtMse840000EmaPruned_vae.safetensors, Denoising strength: 0.6, Hires upscale: 2, Hires steps: 10, Hires upscaler: R-ESRGAN 4x+ Anime6B, Lora hashes: "fubuki: ce30cae7c555, space_hopper: f4112c058273", Version: v1.9.3
```

# Credits

[LoRA Trainer and Dataset Maker](https://github.com/hollowstrawberry/kohya-colab) based on the work of [kohya-ss](https://github.com/kohya-ss/sd-scripts) and [Linaqruf](https://github.com/Linaqruf/kohya-trainer)
