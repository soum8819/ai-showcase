# AI Builds

Four interactive pieces by Soumya (Sam) Dey, made by directing an AI agent from start to finish. I chose the ideas, the look and the details, and I checked every claim and every frame before shipping.

**Live site:** https://soum8819.github.io/ai-showcase/

| Project | What it is | Open |
|---|---|---|
| **Inside GPT-2** | A scrubbable, code-rendered explainer of how a language model picks its next word, animated from GPT-2 small's real outputs | [Open](https://soum8819.github.io/ai-showcase/inside-gpt2/) |
| **Neon Downpour** | A first-person shooter on a rain-soaked neon rooftop, with every model, texture, light and sound generated in code | [Play](https://soum8819.github.io/ai-showcase/neon-downpour/) |
| **AI Factory** | A cinematic 3D flythrough of a GPU cluster, then free orbit and tap-to-inspect racks | [Open](https://soum8819.github.io/ai-showcase/ai-factory/) |
| **Agent Attack Lab** | An isometric simulation of OWASP LLM Top 10 (2025) attacks against a tool-using AI agent, with guardrails you can toggle | [Open](https://soum8819.github.io/ai-showcase/agent-attack-lab/) |

## Inside GPT-2: how the data was made

The animation is driven by the model's real numbers, not illustrations.

- GPT-2 small (124,439,808 parameters) was loaded from the ONNX Model Zoo export and run in a NumPy reimplementation, so attention weights and per-layer states could be read out.
- That NumPy implementation matched the official ONNX runtime's logits within 0.0001 before any value was used.
- For six preset sentences, the page shows real token IDs, real 768-number embeddings, attention weights for all 144 heads, a layer-by-layer readout of the best guess (the "logit lens"), the final top-10 probabilities and a six-token greedy continuation.
- The 3D embedding map is a PCA projection of GPT-2's real token embeddings.
- Model sizes were checked against OpenAI's `gpt-2` source code.
- For sentences you type yourself, tokenization and map positions are real. Later steps are clearly labeled as simulated, because the page does not run the model live.

## Notes

- Neon Downpour needs a desktop browser with a mouse and keyboard. Phones get the attract-mode scene. Graphics settings (High, Medium, Low) are on the title screen, and resolution drops automatically if the frame rate does.
- Every page is a single self-contained HTML file. Libraries load from public CDNs.

## Credits and licenses

- Inside GPT-2 shows content created with **GPT-2** by OpenAI ([modified MIT license](https://github.com/openai/gpt-2/blob/master/LICENSE)). The model weights came from the [ONNX Model Zoo](https://github.com/onnx/models) (Apache 2.0). No weights are included in this repository.
- [gpt-tokenizer](https://github.com/niieani/gpt-tokenizer) (MIT) tokenizes your own sentences.
- [three.js](https://threejs.org) (MIT) powers the 3D pieces.
- Fonts come from Google Fonts (SIL Open Font License).

The code in this repository is released under the MIT license. See `LICENSE`.
