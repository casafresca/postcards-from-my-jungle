# Run and publish the project

The project contains fifty trained DDPM image studies, sixteen AudioLDM WAV calls, sixteen invented language entries, and a separately labeled concept cover. The notebooks are cleaned reproduction workflows; their execution cells are intentionally empty. Actual measured histories are in `experiments/*/metrics.json`, `image-run.json`, `sound-run.json`, and `audio-quality.json`. The training session ran in Colab on a Tesla T4 with Python 3.13 and Torch 2.11.0+cu130.

## Reproduce the images

Upload `image-generation.ipynb` to Colab, select a T4 GPU, and run its cells. It compares dataset size, resolution, and training length. The last run trains for 200 epochs. Download the export before disconnecting: Colab's `/content` storage is temporary. Checkpoints resume within the same runtime but do not preserve the complete random-number-generator state, so interrupted reruns are not guaranteed to reproduce identical pixels.

The original run first reached twenty epochs, was visually inspected, and then continued to two hundred. The initial texture/noise contact sheet is retained for comparison. The cleaned notebook performs the full final training directly, without the interactive recovery steps. CPU data-loader workers can be set to zero if notebook multiprocessing emits warnings.

## Reproduce the sounds

Upload `sound-generation.ipynb`, select a T4 GPU, run generation, and export its WAV files. It uses the pre-trained `cvssp/audioldm-s-full-v2` model; no audio-model training is claimed. Sixteen prompts and seeds produce clips from 2 to 9.5 seconds. Peak normalization occurs before PCM encoding; fades soften the boundaries. Listen to the generated results and revise weak calls rather than relying only on numerical checks.

## Website

Serve this folder with a static HTTP server, or use GitHub Pages. Opening the HTML directly from disk may block loading the JSON manifests. The slideshow reads `image-manifest.json` and `sound-manifest.json`. Fifty image studies share sixteen sound/language identities using specimen IDs. Names were curated after image generation, so the training notebook and original audio source may show earlier working names. The concept cover is an additional slide. Audio requires a deliberate click, and changing slides stops the previous call.

## GitHub Pages

Repository: [casafresca/postcards-from-my-jungle](https://github.com/casafresca/postcards-from-my-jungle). Pages uses GitHub Actions; the included workflow publishes the static page and media on pushes to `main`. Check the latest workflow and live page before assuming a later change has deployed. Full model checkpoints are excluded from the website and repository.

## Sources

- [Diffusers DDPM training tutorial](https://huggingface.co/docs/diffusers/tutorials/basic_training)
- [AFHQ mirror](https://huggingface.co/datasets/huggan/AFHQ) and [original dataset provenance](https://github.com/clovaai/stargan-v2)
- [AudioLDM model card](https://huggingface.co/cvssp/audioldm-s-full-v2) and [pipeline documentation](https://huggingface.co/docs/diffusers/api/pipelines/audioldm)
- [GitHub Pages quickstart](https://docs.github.com/en/pages/quickstart)

The implementations were prepared from primary library and model documentation. See `ASSET-CREDITS.md` for attribution and `LANGUAGE.md` for the structured language prompt.
