# nanochat-arush

> A research-focused, learning-first fork of nanochat for end-to-end understanding and experimentation with micro-LLMs.

⚠️ **Important note on attribution**  
This repository is a **derivative work** based on **nanochat** by : Andrej Kerpathy
All core architecture, training pipeline design, and baseline implementation credit belongs to the original author.  
This fork exists for **educational, experimental, and research-oriented purposes**.

---

## What this repository is

This project is my **hands-on study and experimental fork** of nanochat — a minimal, end-to-end implementation of a ChatGPT-style Large Language Model that can be trained and served on modest budgets.

The goal of this fork is **not** to claim originality over nanochat, but to:

- Deeply understand **every stage** of modern LLM systems:
  - Tokenization
  - Pretraining
  - Mid-training
  - Supervised Fine-Tuning (SFT)
  - Evaluation
  - Inference & Web UI
- Run **controlled experiments** on small and mid-scale models
- Document **failure modes, hallucinations, and limitations** of micro-models
- Add **clarity, commentary, and structured learning notes** on top of the original codebase
- Serve as a **research-grade learning artifact**, not a black-box demo

This repository is intentionally kept **close to upstream nanochat**, preserving its philosophy of:
> minimalism, readability, hackability, and end-to-end ownership.

---

## What I changed vs upstream nanochat

| Area | Status | Description |
|----|----|----|
| Documentation | ✅ | Rewritten README with learning + research framing |
| Code Comments | 🚧 | Adding inline explanations for training scripts |
| Experiments | 🚧 | Controlled runs with depth, batch size, and data scaling |
| Evaluation Notes | 🚧 | Interpretation of CORE / MMLU / GSM8K scores |
| CPU/MPS Runs | 🚧 | Small-model configs for local experimentation |
| Research Logs | 🚧 | Structured experiment notes and findings |

> 🚧 = planned or in progress  
This fork is intentionally **iterative**, mirroring real research workflows.

---

## Why nanochat?

nanochat is uniquely valuable because it:

- Trains an LLM **from scratch**, end to end
- Avoids framework bloat and over-configuration
- Makes LLM training **cognitively accessible**
- Produces a tangible **ChatGPT-like system**, including UI
- Fits within realistic academic / personal compute budgets

This makes it an ideal base for **learning-oriented research** rather than production deployment.

---

## Quick start (summary)

The fastest way to experience the full pipeline is via the speedrun script.

bash
bash speedrun.sh

After training completes, launch the web UI:

python -m scripts.chat_web


Then open the displayed URL in your browser to interact with the model.

For full original instructions and detailed explanations, refer to the upstream nanochat repository.

Experiments & observations (example)
Experiment 1: ~$100 tier model (d20)

Model depth: 20 layers

Training time: ~4 hours on 8×H100

Behavior:

Coherent short responses

Frequent factual hallucinations

Weak multi-step reasoning

Key takeaway:

Small models exhibit strong fluency illusions but lack robustness

Hallucinations emerge even with seemingly confident tone

Detailed experiment logs will be added in /experiments.

Key learnings so far

Chinchilla-optimal scaling improves efficiency, not intelligence

Gradient accumulation is critical for low-VRAM environments

Evaluation scores can be misleading without qualitative inspection

Micro-models are excellent for systems learning, not task accuracy

Ownership of the full training loop changes how you reason about LLMs

Intended audience

This fork is intended for:

Students learning LLM systems engineering

Researchers studying scaling behavior of small models

Engineers wanting to understand training beyond APIs

MS / PhD applicants building auditable, real-world artifacts

It is not intended as a production-ready chatbot.

Attribution & license

This repository is a fork of nanochat by Andrej Karpathy.
Original repository: https://github.com/karpathy/nanochat

Original code: © Andrej Karpathy, MIT License

Modifications, documentation, and experiment notes: © Arush Singhal

All original license terms are preserved.

Disclaimer

This project is for educational and research purposes only.
It makes no claims of state-of-the-art performance or commercial readiness.
