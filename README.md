# de_kroko_asr_onnx

[![Release](https://github.com/JunkleTech/de_kroko_asr_onnx/actions/workflows/release.yml/badge.svg)](https://github.com/JunkleTech/de_kroko_asr_onnx/actions/workflows/release.yml)

German **Kroko 128L** automatic speech recognition (ASR) model in ONNX format,
packaged for use with [sherpa-onnx](https://github.com/k2-fsa/sherpa-onnx).

---

## Contents

The release ZIP archive (`de_kroko_128l.zip`) contains the following files sourced from
[hudaiapa88/sherpa-stt-onnx – de/kroko_128l](https://huggingface.co/hudaiapa88/sherpa-stt-onnx/tree/main/de/kroko_128l)
on Hugging Face:

| File | Description |
|------|-------------|
| `encoder-*.onnx` | Encoder network (RNN-T / Transducer) |
| `decoder-*.onnx` | Decoder (prediction) network |
| `joiner-*.onnx`  | Joiner network |
| `tokens.txt`     | Vocabulary / token list |

---

## Pipeline

A GitHub Actions workflow (`.github/workflows/release.yml`) automatically:

1. Downloads all model files from Hugging Face (`de/kroko_128l`).
2. Verifies that encoder, decoder, joiner, and tokens files are all present.
3. Compresses them into `de_kroko_128l.zip`.
4. Publishes the ZIP as a versioned [GitHub Release](https://github.com/JunkleTech/de_kroko_asr_onnx/releases).

The workflow is triggered on every push to `main` and can also be started
manually via **Actions → Run workflow**.

---

## Usage

```bash
# Download the latest release
gh release download --repo JunkleTech/de_kroko_asr_onnx --pattern "*.zip"
unzip de_kroko_128l.zip -d de_kroko_128l
```

Then point your sherpa-onnx configuration at the extracted directory.

---

## License

The model weights and vocabulary files are licensed under the
**[Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0)**.

The pipeline code in this repository is also released under the
**[Apache License 2.0](LICENSE)**.

> **Attribution:** Model originally published by
> [hudaiapa88](https://huggingface.co/hudaiapa88) on Hugging Face.
