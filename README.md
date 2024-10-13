# VOICE CLONING BARK HUBERT

### **OVERVIEW**

[Bark](https://github.com/suno-ai/bark) is a transformer-based text-to-audio model developed by Suno, capable of generating realistic, multilingual speech and other types of audio, such as background noise and simple sound effects. The model can also produce non-verbal communications. It follows a GPT-like architecture, similar to AudioLM and Vall-E, utilizing a quantized audio representation from [EnCodec](https://github.com/facebookresearch/encodec#extracting-discrete-representations). Unlike traditional TTS models, Bark generates audio directly from text, without the intermediate use of phonemes, enabling it to generalize to a wide range of instructions beyond speech, such as song lyrics and sound effects.

[![Icons](https://skillicons.dev/icons?i=py,pytorch&theme=dark)](https://skillicons.dev)

### **CUSTOM VOICE-CLONING**

Voice cloning, the process of synthesizing a person's voice using machine learning, has seen significant advancements in recent years. AI models like this one can generate human-like audio from text inputs with high accuracy. However, a limitation of Bark is that it does not support the creation of personalized voices from audio samples. To address this limitation, [SerpAI](https://github.com/serp-ai/bark-with-voice-clone) has developed a feature that enables voice cloning from custom audio samples. This extension processes outputs from the HuBERT model and transforms them into semantic tokens compatible with Bark’s text-to-speech model, allowing for speech transfer and voice cloning. Check [gitmylo](https://github.com/gitmylo/bark-voice-cloning-HuBERT-quantizer) for the solution to the semantic token generation for better voice clones and finetunes.

### **SEMANTIC TOKEN EXTRACTION**

The code in this repository has been adapted to capture the semantics of a pre-trained [HuBERT pt-br model](https://huggingface.co/MadVoyager/bark-voice-cloning-portuguese-HuBERT-quantizer/blob/main/portuguese-HuBERT-quantizer_24_epoch.pth). This model extracts semantic representations from portuguese audio, converting acoustic patterns into discrete tokens that preserve essential speech information. These tokens are crucial for the voice cloning process, as they capture the semantic and phonetic elements that define a voice's style, intonation, and unique characteristics, allowing for realistic audio synthesis.

Once the semantic tokens are extracted and aligned with Bark, they are saved in a .npz file. This speech history file can then be used to generate audio with voice cloning. In the provided code, the .npz file is loaded as the voice_name parameter, containing information about the cloned voice extracted by the HuBERT model. The text_prompt input is processed to generate the final audio, using both the textual data and the voice history, ensuring the output maintains the cloned voice's characteristics.

### **AUDIO QUALITY FOR SEMANTIC TOKEN GENERATION**

To achieve better results in voice cloning, it is essential that the input audio sample is as clean and clear as possible. Background noise should be removed using noise reduction tools to prevent the model from confusing unwanted sounds with speech characteristics. Similarly, music in the audio can compromise the cloning quality. Additionally, the audio should not be abruptly cut off at the end, as this might cause the model to generate incoherent speech.

The length of the training audio is also important. Very short samples, particularly those under one second, do not provide enough information for the model to capture the voice's nuances. Ideally, the audio should be between 5 and 12 seconds long, with 10 seconds being a good starting point for high-quality results. Clearly pronounced speech, without background noise and from a single speaker, is crucial. Furthermore, the sample should contain complete sentences, without interruptions, allowing the model to learn proper intonation and rhythm.

Interestingly, more common and regular voices tend to be cloned more accurately. Although the model can handle more complex voices, it may struggle to replicate them with the same fidelity. To further improve results, multiple versions of the cloned voice can be generated until one closely matches the original. This generation can then be used as a new voice history, ensuring greater consistency and quality in future reproductions.

> [!TIP]
> For an alternative explanation on voice cloning using the mentioned techniques, you can refer to this detailed guide: [AI Voice Cloning with Bark and HuBERT](https://www.linkedin.com/pulse/ai-voice-cloning-bark-hubert-practical-guide-felix-leber) - A Practical Guide by Felix Leber.

---

<br>

<img src="https://media.licdn.com/dms/image/v2/D560BAQHyVf5Gy4VdxQ/company-logo_200_200/company-logo_200_200/0/1682517064853/serpdotai_logo?e=1736985600&v=beta&t=bOGgFqbWFwxcM1EApXepgL1ICJHe3f7OXKhY9waD8fg" alt="SerpDotAI Logo" width="100"/>

---

### **INSTALLATION GUIDE**

### **INSTALLATION COMMON ERRORS**

pip install pip==23.2.1

If you encounter an issue while running the cell below, and the error is related to:

ValueError: mutable default <class 'fairseq.dataclass.configs.CommonConfig'> for field common is not allowed: use default_factory

You can resolve this by installing Fairseq using the following command:

%pip install git+https://github.com/One-sixth/fairseq.git

If you then encounter the error:

OSError: [WinError 1314] The client does not have the necessary privilege: '..\\examples' -> 'fairseq\\examples'
...
note: This error originates from a subprocess, and is likely not a problem with pip.

You should run the installation command in the terminal using administrator privileges in PowerShell, rather than in the terminal within VS Code.

### **AUTHOR**

- Giovane Iwamoto, computer science student at UFMS - Brazil, Campo Grande - MS.

I am always open to receiving constructive criticism and suggestions for improvement in my developed code. I believe that feedback is an essential part of the learning and growth process, and I am eager to learn from others and make my code the best it can be. Whether it's a minor tweak or a major overhaul, I am willing to consider all suggestions and implement the changes that will benefit my code and its users.
