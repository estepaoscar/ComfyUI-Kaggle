# context.md

## Decisiones importantes
- **No instalar SD WebUI Forge en local**: GPU GTX 760M (2 GB VRAM) + driver nouveau insuficientes.
- **Usar Kaggle como plataforma principal**: GPU T4 (16 GB VRAM) para ejecutar ComfyUI.
- **Krea 2 Turbo INT8 ConvRot como modelo principal**: ~12.57 GB, 8 pasos de inferencia, 12 GB VRAM requeridos.
- **Túnel con Cloudflare Tunnel** (no ngrok): no necesita token ni cuenta.
- **Forge abandonado**: incompatibilidad con Python 3.13 de Colab requiere demasiados parches.
- **Kaggle probado y funcional**.
- **Colab Pay-as-you-go** ($9.99 por 100 unidades ~1,400 imágenes) solo como plan B.

## Parámetros finales
- Flag VRAM: `--normalvram` (por defecto, no usar `--highvram` en T4)
- PyTorch: 2.11.0+cu130 (Kaggle)
- GPU: Tesla T4 (16 GB VRAM) en Kaggle
- Tiempo por imagen: ~137 segundos (2.3 min) a 2K con LoRA
- Costo por imagen: ~$0.007 USD en Colab Pay-as-you-go (plan B)

## Configuraciones
- Notebook principal (Kaggle): `notebooks/2026-11-20_comfyui_krea2_turbo_int8_kaggle_v4.ipynb`
- Notebook Style Reference (Kaggle): `notebooks/2026-11-24_comfyui_krea2_turbo_style_ref_kaggle_v1.ipynb`
- Notebook Wan 2.2 TI2V 5B (Kaggle): `notebooks/2026-11-24_comfyui_wan2_2_ti2v5b_kaggle_v1.ipynb`
- Workflow T2I (Kaggle): `workflows/image_krea2_turbo_t2i_int8-kaggle.json`
- Workflow Style Reference (Kaggle): `workflows/image_krea2_turbo_int8_image_style_reference-kaggle.json`

## Notas relevantes
- Krea 2 Turbo INT8 usa text encoder Qwen3VL 4B FP8 + VAE Qwen + 9 LoRAs de estilo
- Los modelos se descargan frescos cada sesión (~18 GB total, ~2.5 min de descarga)
- Comfy Cloud no es viable: Standard ($20/mes) no permite importar modelos propios
- Colab solo como respaldo si Kaggle no está disponible