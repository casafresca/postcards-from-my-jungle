# Image experiment record

These measurements were produced in Google Colab on a Tesla T4. The dataset was `huggan/AFHQ`, shuffled with seed 498. One hundred separate examples were reserved for validation.

| Run | Training images | Resolution | Epochs | Final train loss | Final validation loss |
| --- | ---: | ---: | ---: | ---: | ---: |
| small-32 | 500 | 32 × 32 | 5 | 0.3150 | 0.2840 |
| more-data-32 | 1000 | 32 × 32 | 5 | 0.1943 | 0.1917 |
| higher-resolution-64 | 1000 | 64 × 64 | 5 | 0.1777 | 0.1646 |
| longer-training-64 | 1000 | 64 × 64 | 200 | 0.0511 | 0.0575 |

The initial twenty-epoch output was mostly texture and noise. Compare [that contact sheet](initial-20-epoch-contact.png) with the [final fifty-image contact sheet](fifty-images.png). Continuing to two hundred epochs produced recognizable mammalian faces and hybrid features. The small AFHQ face dataset still restricts variety and whole-body anatomy.

Noise prediction losses are diagnostic and are not perceptual-quality scores; values at different image resolutions should not be treated as a visual ranking. The final selected run is `longer-training-64`. Full measured histories are stored in each run’s metrics.json.

The notebooks have been cleaned for replay rather than supplied with fabricated execution counts. The original interactive session used checkpoint resumption and recovered from a mixed-precision scaler interruption. Its final output images, epoch histories, seeds, dataset fingerprint, and model configuration are preserved here. Repeating training on a different runtime may change individual outputs.
