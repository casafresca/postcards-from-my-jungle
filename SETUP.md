# Production status and completion

This folder is the repository source. It is named `postcards-from-my-jungle` as required. The website is functional as a clearly labeled concept edition. It currently has **one concept illustration, sixteen language phrases, zero trained animal images, and zero generated audio files**. The notebooks contain real training/inference code but their local copies have no execution outputs yet. Do not submit this as a completed training project.

## Colab

1. Upload `image-generation.ipynb` to Colab and select a T4 GPU. Run the training cell. Four experiments execute sequentially, record measured losses, save checkpoints, and generate 50 images. Inspect comparisons for quality; the longest run is only the default selection, not a proven winner.
2. Run the export cell and extract `jungle-images.zip` into this repository root, merging its `images/` folder and replacing `image-manifest.json`.
3. Upload `sound-generation.ipynb`, select a T4 GPU, run its generation cell, and listen to every clip. Export and extract `jungle-sounds.zip` here, merging `sounds/` and replacing `sound-manifest.json`.
4. Download the executed notebooks from Colab and replace these unexecuted local copies. Retain the loss logs, comparison images, prompts, seeds, and run metadata. `/content` is temporary: download before disconnecting. Checkpoints resume only in the same runtime.
5. Revise README from planned methods to actual findings; keep it 250–350 words. Review species interpretations against the actual images and adjust assignments in `image-manifest.json`.

The site reads both manifests. Fifty image slides share sixteen calls/phrases using the specimen mapping. Changing a slide always stops the prior call. Audio requires a deliberate click. No generated-media placeholders are counted as completed work.

## GitHub Pages

Create a **public** repository named `postcards-from-my-jungle` on your own GitHub account and upload this folder’s contents at its root. Under Settings → Pages, choose **GitHub Actions** as the source. The included workflow publishes only the website and media, excluding notebooks and training checkpoints from the hosted artifact. A push to `main` triggers deployment. Wait for the deployment job to succeed and use its reported URL; do not claim the expected URL is live before verification.

The GitHub connector supports content updates but does not expose repository creation or Pages settings. Those actions require a signed-in browser or authenticated GitHub CLI.

## Sources

- https://huggingface.co/docs/diffusers/tutorials/basic_training
- https://huggingface.co/datasets/huggan/AFHQ
- https://github.com/clovaai/stargan-v2 (original AFHQ provenance and terms)
- https://huggingface.co/cvssp/audioldm-s-full-v2
- https://huggingface.co/docs/diffusers/api/pipelines/audioldm
- https://docs.github.com/en/pages/quickstart

The two suggested course notebooks could not be read through public web retrieval; these implementations were prepared from primary model/library documentation instead.
