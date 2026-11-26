# ComfyUI en Kaggle — Krea 2 Turbo INT8

## Propósito del proyecto
Ejecutar **ComfyUI con Krea 2 Turbo INT8 ConvRot** en Kaggle (GPU T4 16 GB VRAM) para generación de imágenes y video.

## Stack
- **Plataforma**: Kaggle Notebooks (GPU Tesla T4, 16 GB VRAM)
- **Framework**: ComfyUI
- **Modelo principal**: Krea 2 Turbo INT8 ConvRot (~12.57 GB, 8 pasos, 12 GB VRAM)
- **Modelos video**: LTX 2.5 I2V, Wan 2.2 TI2V 5B
- **Túnel**: Cloudflare Tunnel (sin token, sin cuenta)

## Decisión técnica
**No es viable instalar nada en local** (GTX 760M 2 GB VRAM + driver nouveau sin CUDA).

## Configuración activa (Kaggle)
- Flag VRAM: `--normalvram` (por defecto, no `--highvram` en T4)
- PyTorch: 2.11.0+cu130
- Tiempo por imagen: ~137 seg (2.3 min) a 2K con LoRA
- Modelos se descargan cada sesión (~18 GB, ~2.5 min)

## Notebooks principales
- T2I: `2026-11-20_comfyui_krea2_turbo_int8_kaggle_v4.ipynb`
- Style Reference: `2026-11-24_comfyui_krea2_turbo_style_ref_kaggle_v1.ipynb`
- LTX 2.5 I2V: `2026-11-24_comfyui_ltx2_5_i2v_kaggle_v1.ipynb`
- Wan 2.2 TI2V 5B: `2026-11-24_comfyui_wan2_2_ti2v5b_kaggle_v1.ipynb`

## Workflows
- T2I: `image_krea2_turbo_t2i_int8-kaggle.json`
- Style Reference: `image_krea2_turbo_int8_image_style_reference-kaggle.json`
- Video I2V: `video_ltx2_5_i2v-kaggle.json`

## Convenciones
- Nomenclatura ISO según skill `iso-filenames`

## Skills de proyecto
- `iso-filenames`: Aplica la convención de nombres AAAA-MM-DD_Descripción_Versión a todo archivo creado en este proyecto.