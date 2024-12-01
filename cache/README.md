# cache

This folder is the cache directory for Hugging Face (HF).

When using online mode, downloaded models will be cached in this folder.

For [offline mode](https://huggingface.co/docs/transformers/main/installation#offline-mode) use, please download the models in advance and specify the model directory,
such as the `microsoft/OmniParser` model below.

The folder structure for `./cache/huggingface/hub/models--microsoft---OmniParser` is as follows.

```
.
├── blobs
│   ├── ...
├── refs
│   └── main
└── snapshots
    └── 7f4732c12e58f7dab3e06f9ec63b021f689317d5
        ├── icon_caption_blip2
        │   ├── ...
        ├── icon_caption_florence
        │   ├── ...
        └── icon_detect
            ├── ...

4 directories, 25 files
```

It will use `./OmniParser/weights`.

For more details, refer to [up@gpu-online/docker-compose.yml](./../docker/up@gpu-online/docker-compose.yml).


## Pre-download for offline mode

Running in online mode will automatically download the model.

install cli

```bash
pip install -U "huggingface_hub[cli]"
```

download model

```bash
huggingface-cli download --cache-dir ./cache/huggingface/hub --revision main --local-dir ./OmniParser/weights microsoft/OmniParser
huggingface-cli download --cache-dir ./cache/huggingface/hub --revision master --local-dir ./cache/.EasyOCR/model xiaoyao9184/easyocr --include english_g2.pth
huggingface-cli download --cache-dir ./cache/huggingface/hub --revision master --local-dir ./cache/.EasyOCR/model xiaoyao9184/easyocr --include craft_mlt_25k.pth 
```