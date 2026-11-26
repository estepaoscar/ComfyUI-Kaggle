# ComfyUI en Kaggle — Krea 2 Turbo INT8

Ejecución de **ComfyUI con Krea 2 Turbo INT8 ConvRot** en Kaggle Notebooks (GPU Tesla T4, 16 GB VRAM) para generación de imágenes y video vía Cloudflare Tunnel.

## Stack
- **Plataforma**: Kaggle Notebooks (GPU T4, 16 GB VRAM)
- **Framework**: ComfyUI
- **Modelo principal**: Krea 2 Turbo INT8 ConvRot (~12.57 GB, 8 pasos, 12 GB VRAM)
- **Modelo video**: Wan 2.2 TI2V 5B
- **Túnel**: Cloudflare Tunnel (sin token, sin cuenta)
- **Flag VRAM**: `--normalvram` (por defecto en T4)
- **PyTorch**: 2.11.0+cu130

## Contenido del repo

### Notebooks (`notebooks/`)
| Archivo | Descripción |
|---------|-------------|
| `2026-11-20_comfyui_krea2_turbo_int8_kaggle_v4.ipynb` | **T2I** — Text-to-Image con Krea 2 Turbo INT8 |
| `2026-11-24_comfyui_krea2_turbo_style_ref_kaggle_v1.ipynb` | **Style Reference** — Imagen + referencia de estilo |
| `2026-11-24_comfyui_wan2_2_ti2v5b_kaggle_v1.ipynb` | **Wan 2.2 TI2V 5B** — Text+Image-to-Video |

### Workflows (`workflows/`)
| Archivo | Descripción |
|---------|-------------|
| `image_krea2_turbo_t2i_int8-kaggle.json` | Workflow T2I |
| `image_krea2_turbo_int8_image_style_reference-kaggle.json` | Workflow Style Reference |

### Configuración
- `AGENTS.md` — Contexto del proyecto para Pi
- `context.md` — Parámetros finales y decisiones
- `.agents/skills/iso-filenames/SKILL.md` — Convención de nombres ISO

## Uso en Kaggle
1. Crear notebook nuevo en Kaggle con **GPU T4** activada
2. Subir el notebook `.ipynb` deseado
3. Ejecutar celdas en orden
4. Al final aparecerá URL Cloudflare Tunnel (`https://*.trycloudflare.com`)
5. Abrir en navegador → ComfyUI listo

## Rendimiento
- ~137 seg/imagen (2.3 min) a 2K con LoRA
- Descarga modelos cada sesión: ~18 GB, ~2.5 min

## Convenciones
- Nomenclatura ISO: `AAAA-MM-DD_Descripción_Versión.ext` (skill `iso-filenames`)

---

> **Nota**: No es viable en local (GTX 760M 2 GB VRAM + driver nouveau sin CUDA). Kaggle es la plataforma principal; Colab Pay-as-you-go solo como respaldo.