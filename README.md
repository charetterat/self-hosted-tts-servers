# Self-Hosted TTS Servers

> OpenAI-compatible text-to-speech you run on your own hardware

A curated index of text-to-speech you can host yourself: HTTP servers that expose an OpenAI-compatible /v1/audio/speech endpoint, the local inference engines underneath them, voice-cloning backends, browser UIs, and long-form generators. Every entry links to the upstream project; nothing here is a re-host or a mirror.

> [!NOTE]
> Compiled from public sources — no independent testing of the linked projects. Star counts were read from the GitHub API on 2026-10-16 and drift daily.

## Contents

- [🔌 OpenAI-compatible servers](#openai-compatible-servers)
- [⚙️ Inference engines](#inference-engines)
- [🖥️ Browser and desktop front ends](#browser-and-desktop-front-ends)
- [📚 Long-form generation](#long-form-generation)

## 🔌 OpenAI-compatible servers

Drop-in replacements for the OpenAI speech endpoint. Point an existing client at these instead of api.openai.com and nothing else in your stack has to change.

| Project | What it is | Tags |
|---|---|---|
| [Kokoro-FastAPI](https://github.com/remsky/Kokoro-FastAPI) | Dockerized FastAPI wrapper around Kokoro-82M exposing an OpenAI-compatible /v1/audio/speech endpoint, with voice mixing and multiple output formats. The most-starred dedicated TTS server here. | `FastAPI`, `Docker`, `Kokoro` |
| [Chatterbox-TTS-Server](https://github.com/devnen/Chatterbox-TTS-Server) | Self-hosting front end for the Chatterbox model, shipping both a web UI for auditioning voices and an API surface for programmatic use. | `Chatterbox`, `WebUI` |
| [chatterbox-tts-api](https://github.com/travisvn/chatterbox-tts-api) | A deliberately minimal local OpenAI-compatible TTS API built on Chatterbox, aimed at people who want the endpoint and not much else. | `Chatterbox`, `Minimal` |
| [openedai-speech](https://github.com/matatonic/openedai-speech) | OpenAI-API-compatible server over Coqui xtts_v2 with voice cloning. Archived upstream — listed because it is still widely forked and referenced, not because it is maintained. | `XTTS`, `Archived` |
| [xtts-api-server](https://github.com/daswer123/xtts-api-server) | A simple FastAPI server for XTTSv2 covering voice cloning, multiple languages and streaming responses. | `XTTS`, `FastAPI` |
| [Chatterbox-TTS-Extended](https://github.com/petermg/Chatterbox-TTS-Extended) | Fork of Chatterbox that accepts whole text files as input and batches long-form synthesis rather than one utterance at a time. | `Chatterbox`, `Batch` |
| [Dia-TTS-Server](https://github.com/devnen/Dia-TTS-Server) | Serving wrapper for the Dia model, focused on multi-speaker dialogue rather than single-narrator speech. | `Dia`, `Multi-speaker` |
| [mlx-omni-server](https://github.com/madroidmaq/mlx-omni-server) | Local inference server built on Apple's MLX, exposing OpenAI-shaped endpoints for speech and other modalities on Apple Silicon. | `MLX`, `Apple Silicon` |

## ⚙️ Inference engines

The model runtimes the servers above are thin wrappers around. Useful directly when you want to embed synthesis in-process instead of over HTTP.

| Project | What it is | Tags |
|---|---|---|
| [Coqui TTS](https://github.com/coqui-ai/TTS) | The long-standing deep-learning TTS toolkit. The original company shut down and the repo is archived; the community continuation is the next entry. | `Archived`, `Toolkit` |
| [coqui-ai-TTS (community fork)](https://github.com/idiap/coqui-ai-TTS) | Maintained fork of Coqui TTS under the Idiap research institute, keeping XTTS and the rest of the toolkit installable on current Python. | `XTTS`, `Maintained fork` |
| [F5-TTS](https://github.com/SWivid/F5-TTS) | Flow-matching TTS trained to clone a voice from a short reference clip, with an actively developed training and inference codebase. | `Voice cloning`, `Flow matching` |
| [Orpheus-TTS](https://github.com/canopyai/Orpheus-TTS) | Llama-based speech model producing expressive output with paralinguistic tags such as laughter and sighs. | `Llama`, `Expressive` |
| [Kokoro](https://github.com/hexgrad/kokoro) | An 82M-parameter open-weight TTS model that punches well above its size, and the reason most of the servers above exist. | `82M`, `Open weights` |
| [kokoro-onnx](https://github.com/thewh1teagle/kokoro-onnx) | Kokoro reimplemented on ONNX Runtime, trading the PyTorch dependency for a portable inference graph. | `ONNX`, `Kokoro` |
| [Piper](https://github.com/rhasspy/piper) | Fast local neural TTS designed for Raspberry Pi-class hardware. Archived at this path; development continues in the GPL fork below. | `Archived`, `Edge` |
| [piper1-gpl](https://github.com/OHF-Voice/piper1-gpl) | The current home of Piper development, relicensed and restructured with a C API and Python bindings. | `Edge`, `C API` |
| [sherpa-onnx](https://github.com/k2-fsa/sherpa-onnx) | ONNX-based speech toolkit spanning TTS, recognition and diarisation across many platforms, with prebuilt binaries and language bindings. | `ONNX`, `Multi-platform` |
| [espeak-ng](https://github.com/espeak-ng/espeak-ng) | The formant synthesiser that will not win a naturalness contest but runs anywhere, in almost any language, and is a common fallback backend for larger systems. | `Formant`, `Fallback` |

## 🖥️ Browser and desktop front ends

Graphical ways to drive local models without writing a client.

| Project | What it is | Tags |
|---|---|---|
| [TTS-WebUI](https://github.com/rsxdalv/TTS-WebUI) | Gradio and React interface bundling a large set of local speech and audio models behind one control panel. | `Gradio`, `Multi-model` |
| [TTS-Audio-Suite](https://github.com/diodiogod/TTS-Audio-Suite) | ComfyUI custom nodes for local multi-engine, multi-language speech generation, for people already working inside a ComfyUI graph. | `ComfyUI`, `Nodes` |
| [voice-pro](https://github.com/abus-aikorea/voice-pro) | Gradio WebUI aimed at creators, combining TTS, voice cloning, translation and dubbing in one interface. | `Gradio`, `Dubbing` |
| [orpheus-tts-local](https://github.com/isaiahbjork/orpheus-tts-local) | Runs the Orpheus 3B model locally through LM Studio, with a small client for driving it. | `LM Studio`, `Orpheus` |

## 📚 Long-form generation

Tooling that turns documents into hours of audio, where the hard part is chunking and pacing rather than the synthesis itself.

| Project | What it is | Tags |
|---|---|---|
| [audiblez](https://github.com/santinic/audiblez) | Generates audiobooks from e-books, handling chapter detection and long-run synthesis locally. | `Audiobook`, `EPUB` |
| [abogen](https://github.com/denizsafak/abogen) | Converts EPUBs, PDFs and plain text into audiobooks with synchronised captions and chapter-level progress tracking. | `Audiobook`, `Captions` |

---

## About this list

- **24** entries across **4** sections.
- Compiled from public sources; every linked project carries its own license.
- Last updated: **2026-10-16**.
- Data lives in `data/content.json` — this README is generated, do not edit by hand.

## License

The text and curation in this repository are licensed under CC BY 4.0. Linked projects keep their own licenses.
