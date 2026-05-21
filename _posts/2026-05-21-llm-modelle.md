
# Q Gtp5: rstelle liste von LLM : Firma , LLM Name, LLM Version , Releasedatum, größe kontext fenster , auf rtx5070ti möglich , auf dgx spark möglich , relative token / sek schätzung , recherchiere auch im web
## A
Hier ist eine **praxisorientierte LLM-Liste** mit Hardware-Einschätzung für **RTX 5070 Ti** und **NVIDIA DGX Spark**.

**Annahmen:** RTX 5070 Ti = **16 GB GDDR7, 896 GB/s**; DGX Spark = **128 GB Unified Memory**, laut NVIDIA für Modelle bis ca. **200B Parameter** ausgelegt. ([NVIDIA](https://www.nvidia.com/en-us/geforce/graphics-cards/50-series/rtx-5070-family/?utm_source=chatgpt.com "GeForce RTX 5070 Family Graphics Cards"))  
„Möglich“ bedeutet: lokale Inferenz mit offenen Gewichten, typischerweise quantisiert. Cloud-only/proprietäre Modelle sind lokal **nicht** möglich.

|Firma|LLM Name|Version|Release|Kontextfenster|RTX 5070 Ti möglich|DGX Spark möglich|Relative Token/s Schätzung|
|---|--:|--:|--:|--:|---|---|---|
|OpenAI|GPT|GPT-5.5|23.04.2026|1.050K API; 400K Codex|Nein, proprietär|Nein, proprietär|nur API|
|Anthropic|Claude|Opus 4.6|05.02.2026|1M Beta|Nein, proprietär|Nein, proprietär|nur API|
|Google|Gemini|2.5 Pro|17.06.2025 GA|1M|Nein, proprietär|Nein, proprietär|nur API|
|Meta|Llama|4 Scout 17B-16E|05.04.2025|10M|Nein, 109B total zu groß|Ja, quantisiert|DGX: niedrig–mittel|
|Meta|Llama|4 Maverick 17B-128E|05.04.2025|1M|Nein, 400B total zu groß|Nein / nur stark verteilt|—|
|Google|Gemma|4 E4B|02.04.2026|128K|Ja, sehr gut|Ja|RTX: sehr hoch; DGX: hoch|
|Google|Gemma|4 31B Dense|02.04.2026|256K|Nein / nur extrem quantisiert|Ja|DGX: mittel|
|Google|Gemma|3 27B|12.03.2025|128K|Grenzwertig, Q3/Q4 kurzer Kontext|Ja|RTX: niedrig; DGX: mittel|
|Alibaba/Qwen|Qwen|Qwen3-8B|29.04.2025|32K nativ; 128K via YaRN|Ja, sehr gut|Ja|RTX: hoch; DGX: hoch|
|Alibaba/Qwen|Qwen|Qwen3-14B|29.04.2025|32K nativ; 128K via YaRN|Ja, Q4, kurzer/mittlerer Kontext|Ja|RTX: mittel; DGX: hoch|
|Alibaba/Qwen|Qwen|Qwen3-30B-A3B|29.04.2025|bis 128K validiert|Eher nein; ca. 17.5 GB VRAM genannt|Ja|DGX: hoch für Größe|
|Alibaba/Qwen|Qwen|Qwen3-235B-A22B|29.04.2025|128K|Nein|Grenzwertig/Nein, >200B total|DGX: sehr niedrig falls passend|
|Alibaba/Qwen|Qwen|Qwen3-Next-80B-A3B|10.09.2025|256K bei Coder-Next|Nein|Ja|DGX: mittel–hoch|
|Mistral AI|Mistral Small|3.1 24B Instruct|17.03.2025|128K|Grenzwertig, Q3/Q4 kurzer Kontext|Ja|RTX: niedrig; DGX: mittel|
|Microsoft|Phi|Phi-4-mini-instruct 3.8B|26.02.2025 / 03.03.2025 HF|128K|Ja, sehr gut|Ja|RTX: sehr hoch; DGX: hoch|
|DeepSeek|DeepSeek|R1 / V3.1 671B MoE|20.01.2025 / 21.08.2025|128K bei V3/V3.1|Nein|Nein, viel zu groß|—|
|DeepSeek|DeepSeek|V4 Preview|24.04.2026|1M|Nein|Nein, 1.6T zu groß|—|

Quellenbasis: OpenAI nennt für GPT-5.5 ein 1.050.000-Token-Kontextfenster im API-Modellblatt und 400K in Codex. ([OpenAI Developers](https://developers.openai.com/api/docs/models/gpt-5.5?utm_source=chatgpt.com "GPT-5.5 Model | OpenAI API")) Anthropic beschreibt Opus 4.6 mit 1M Kontextfenster in Beta. ([Anthropic](https://www.anthropic.com/news/claude-opus-4-6?utm_source=chatgpt.com "Introducing Claude Opus 4.6")) Google gibt Gemini 2.5 Pro mit 1M Kontextfenster und GA-Release am 17.06.2025 an. ([blog.google](https://blog.google/innovation-and-ai/models-and-research/google-deepmind/gemini-model-thinking-updates-march-2025/?utm_source=chatgpt.com "Gemini 2.5: Our most intelligent AI model")) Für Llama 4 nennt Meta Scout mit 17B aktiven Parametern, 16 Experten und 10M Kontext; Maverick hat 17B aktive Parameter mit 128 Experten, externe Modellkataloge geben 400B total und 1M Kontext an. ([Meta AI](https://ai.meta.com/blog/llama-4-multimodal-intelligence/?utm_source=chatgpt.com "The Llama 4 herd: The beginning of a new era of natively ..."))

Für lokale Nutzung sind **Phi-4-mini, Gemma 4 E4B, Qwen3-8B und Qwen3-14B** die sinnvollsten Kandidaten auf einer RTX 5070 Ti. Auf **DGX Spark** werden zusätzlich **Gemma 4 31B, Mistral Small 3.1, Qwen3-30B-A3B, Qwen3-Next-80B-A3B und Llama 4 Scout** interessant. Qwen3-235B, Llama 4 Maverick, DeepSeek R1/V3/V4 sind wegen Gesamtgewichten deutlich außerhalb dessen, was ein einzelner RTX-5070-Ti- oder DGX-Spark-Rechner praktisch lokal stemmen sollte.