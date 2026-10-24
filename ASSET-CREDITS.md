# Concept illustration provenance

File: `images/concept-fernfox.png`
Tool: Codex built-in image generation, 24 October 2026. User reports using free Codex; no additional billing tier for the image tool is asserted.
Purpose: a separately labeled visual concept for the website while model training is pending. This image is **not** part of the fifty trained DDPM outputs.

Prompt:
Use case: stylized-concept. Asset type: single landscape concept postcard for a fictional lo-fi jungle field journal. Primary request: an imagined small animal, a moss-green fox with feathery fern ears, an opalescent moth ruff, a long curled tail and inquisitive amber eyes, sitting on a wet fallen tree in a dense nocturnal tropical jungle. Deep emerald and nearly black leaves, tiny pale cyan bioluminescent mushrooms, soft warm light on the creature. Dreamlike low fidelity 35mm film photograph mixed with 1990s natural history diorama, visible fine grain, halation, slightly blurry handmade textures, evocative and tender rather than frightening. Landscape composition, animal fully visible in middle right with jungle around it. No text, no collage, no borders, no watermark.

## Model and dataset attribution

The image experiments use the AFHQ animal-face dataset mirrored at [huggan/AFHQ](https://huggingface.co/datasets/huggan/AFHQ). Original dataset provenance and terms: [StarGAN v2, Clova AI](https://github.com/clovaai/stargan-v2). The small DDPM implementation follows the approach described in the [Hugging Face diffusion training tutorial](https://huggingface.co/docs/diffusers/tutorials/basic_training).

The audio workflow uses [AudioLDM small full v2](https://huggingface.co/cvssp/audioldm-s-full-v2), by Haohe Liu and collaborators at the Centre for Vision, Speech and Signal Processing, University of Surrey. The model card lists CC BY-NC-SA 4.0 for the model. Paper: [AudioLDM: Text-to-Audio Generation with Latent Diffusion Models](https://arxiv.org/abs/2301.12503), 2023. This is an educational, noncommercial art project. No audio-model training is claimed.

Interface fonts: DM Sans and Libre Caslon Display, served by Google Fonts, with system-font fallbacks. All creature descriptions, phrases, and field-journal branding are fictional.
