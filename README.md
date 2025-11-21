<!-- PROJECT HEADER -->

<h1 align="center">🎧 Generative Audio with Stable Diffusion (No-API)</h1>
<h3 align="center">Text → Audio Generation using Stable Audio by Stability AI</h3>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.10+-green?style=for-the-badge">
  <img src="https://img.shields.io/badge/Diffusers-Stable%20Audio-blue?style=for-the-badge">
  <img src="https://img.shields.io/badge/HuggingFace-Models-orange?style=for-the-badge">
  <img src="https://img.shields.io/badge/Jupyter-Notebook-yellow?style=for-the-badge">
  <img src="https://img.shields.io/badge/Status-Active-success?style=for-the-badge">
</p>

---

# 🌟 Overview

This project demonstrates **state-of-the-art Text-to-Audio generation** using:

✔ Stable Audio – *Stability AI’s open-source generative audio model*
✔ HuggingFace Diffusers
✔ PyTorch
✔ Jupyter Notebook workflow

You simply provide a **text prompt**, and the model synthesizes a **high-quality audio clip** (e.g., nature sounds, music, SFX, ambient noise).

---

# 📁 Project Structure

```
01_Generative_Audio_with_StableDiffusion/
├─ assets/
│  ├─ stable_audio_output.wav
│  ├─ stable_audio_output.wav.meta.json
│  └─ stable_audio_output1.wav
└─ notebooks/
   └─ 01_StableDiffusion_text2audio.ipynb
```

---

# 🎧 Sample Outputs

### 🔊 **Sample Output 1**

`assets/stable_audio_output.wav`

### 🔊 **Sample Output 2**

`assets/stable_audio_output1.wav`

These were generated using Stable Audio with prompts like:

> “Elephant trumpet sound with deep resonance in a forest, cinematic ambience.”

---

# 🚀 Features

### 🌈 **Text → Audio Generation**

Turn simple text prompts into rich audio.

### 🎼 **Multiple Waveform Outputs**

Generate multiple variations per prompt.

### 🧠 **Reproducibility**

Uses deterministic seeds for consistent audio.

### 💾 **Automatic Saving**

Generated audio clips are saved as `.wav`.

### 🔥 **High-quality generation**

Leverages Stability AI's `stable-audio-open-1.0` model.

---

# 🛠 Installation

### 1️⃣ Create & activate a virtual environment (optional)

```bash
conda create -n audio_env python=3.10
conda activate audio_env
```

### 2️⃣ Install dependencies

```bash
pip install torch diffusers soundfile huggingface_hub accelerate
```

### 3️⃣ Login to HuggingFace

```bash
huggingface-cli login
```

---

# 📒 Run the Notebook

Open:

```
notebooks/01_StableDiffusion_text2audio.ipynb
```

Run all cells to:

✔ Load Stable Audio
✔ Provide prompts
✔ Generate & save `.wav` files

---

# 📝 Example Prompts (Copy-Paste Ready)

### 🎵 Music

```
Lo-fi beat with vinyl crackle, warm piano chords, soft drums at 70 BPM.
```

### 🐘 Animal SFX

```
Elephant trumpet sound with deep resonance in a forest, cinematic ambience.
```

### 🌧 Nature & Atmosphere

```
Meditative rain with distant thunder and soft wind chimes.
```

### 🚀 Sci-Fi

```
Spaceship engine hum with low-frequency vibration and metallic resonance.
```

### 🏙 Urban Ambience

```
Busy street ambiance with cars passing and soft human chatter.
```

---

# 🧩 Code Preview

```python
from diffusers import StableAudioPipeline
import torch, soundfile as sf

pipe = StableAudioPipeline.from_pretrained(
    "stabilityai/stable-audio-open-1.0",
    torch_dtype=torch.float16
).to("cuda")

audio = pipe(
    prompt="Elephant trumpet sound",
    audio_end_in_s=10,
    num_inference_steps=200,
).audios[0]

sf.write("output.wav", audio.T.cpu().numpy(), pipe.vae.sampling_rate)
```

---

# 📘 Documentation Included

✔ Notebook explanation
✔ Working audio examples
✔ Prompt library
✔ Metadata (`.meta.json`)

---

# 🤝 Contribution

Pull requests are welcome!Feel free to add:

- New prompts
- New audio outputs
- Improvements in notebook

---

# ⭐ Support the Project

If you like this work, please ⭐ star the repository — it motivates continuous improvements!

---

# 📝 License

This project is for **educational / research purposes only**.
Audio model belongs to **Stability AI** under their respective license.

---
