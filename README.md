# Accessible Image Understanding Assistant with Spoken Output

A prototype that looks at an image, generates a caption, answers questions
about it, asks a clarifying question when uncertain, and reads the result
aloud — built for accessibility use cases (helping visually impaired users
understand photos).

## What it does
- Image Captioning — generates a natural description of any photo
- Visual Question Answering (VQA) — answers specific questions about an image
- Clarifying-question detection — flags uncertainty instead of guessing wrong
- Voice output — converts captions to spoken audio (gTTS)

## How it works
Built using Qwen2-VL-2B-Instruct (open-source vision-language model) via
Hugging Face Transformers, running on Google Colab.

## Results
Tested on 20 images (14 everyday photos + 6 deliberately ambiguous ones).
See `results.csv` for full output. Full results and sample audio included
in this repo.

## Connection to prior research
This project extends ideas from Prof. Tatsuya Harada's lab (University of
Tokyo) — specifically their VQA fusion-based approach and Chain-of-Reasoning
work on models that explain their reasoning and ask clarifying questions
when uncertain.

## Honest limitation found
The current confidence-check (comparing word overlap between two rephrased
answers) tends to over-trigger clarifying questions, since language models
naturally vary phrasing even when confident. A more robust approach would
use semantic similarity or the model's own confidence scores — a good
direction for future work.

## Next steps
Extending toward video and audio understanding, in line with where this
research area is heading.
