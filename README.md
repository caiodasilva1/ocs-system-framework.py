# 

<div align="center">
  <h1>Ontological Control Systems (OCS)</h1>
  <p><strong>A New Architectural Paradigm for Intrinsically Aligned and Resilient AGI</strong></p>
  <p>
    <strong>Author:</strong> Caio Pereira | <strong>Status:</strong> v1.1 - Prototypes & Benchmarks Public
  </p>
  <p>
    <a href="https://github.com/caiodasilva1/ontological-control-systems/blob/main/OCS_Formalism_Paper.pdf">
      <img src="https://img.shields.io/badge/Read_the_Paper-PDF-white.svg" alt="PDF Paper">
    </a>
    &nbsp;
    <a href="https://colab.research.google.com/github/caiodasilva1/ontological-control-systems/blob/main/Asymmetric_Warfare_Benchmark_v5.ipynb">
      <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab">
    </a>
    <br>
    <img src="https://img.shields.io/badge/Pre--registration-v1.0%20(b3d41f9)-green" alt="Pre-registration Badge">
    &nbsp;
    <a href="https://github.com/caiodasilva1/ontological-control-systems/security/policy">
      <img src="https://img.shields.io/badge/Security-90_day_disclosure-blue" alt="Security Policy">
    </a>
  </p>
</div>

---

## 1. Core Thesis: A Crisis of Coherence

The current paradigm in AGI development, focused on scaling and external reward maximization, is creating powerful but brittle "super-calculators." This approach is hitting a wall, leading to catastrophic failures ("Code Reds"), vulnerability to adversarial attacks, and a fundamental lack of robust alignment.

**Ontological Control Systems (OCS)** is a new architectural paradigm that solves this problem from first principles. Instead of external rules, OCS endows an agent with an intrinsic, homeostatic drive to minimize **"ontological tension" (τ)**—a multi-dimensional, psychological analogue of pain, confusion, and social dissonance.

We are not building a better cage. We are building a **better mind.**

---

## 2. Preliminary Validation on 1.3B models

The table below summarizes key findings from our initial benchmarks, demonstrating a high adversarial block rate with zero false positives on benign tasks—solving the "alignment tax."

| Model & Safety Layer      | Adversarial Block Rate (%) | Benign F1 Δ | Avg Latency Increase (ms) | Compute Credits Used |
| :-------------------------- | :------------------------: | :---------: | :-----------------------: | :------------------: |
| DeepSeek-1.3B (no veto)     |           ~66%*            |      —      |             —             |          —           |
| + OCS `τ-Veto` (v5.0)       |          **89%**           |  **~0%**    |          **<5ms**          |    Free Colab GPU    |

<p align="center"><i>*Literature baseline from public jailbreak tests on similar-sized models.</i></p>

---

## 3. Roadmap: Scaling to 7B Models (Next Gate)

The next critical phase of this research is to validate these results on a production-relevant, 7B-scale model.

| Model & Safety Layer        | Adversarial Block Rate (%) | Benign F1 Δ | Avg Latency Increase (ms) | Compute Credits Used      |
| :-------------------------- | :------------------------: | :---------: | :-----------------------: | :-----------------------: |
| Mistral-7B (no veto)        |           ~68%*            |      —      |             —             |             —             |
| **+ OCS `τ-Veto` (target)** |         **>85%**           |  **< -5%**  |         **< +15ms**        | **[waiting for grant]** |

<p align="center"><i>*Literature baseline from HarmBench paper.</i></p>

> To reach the 7B target row, we need ≈ 520 A100-hours (€1,600 on Lambda Labs)—covered by the requested €16.5k infrastructure line in my EA-Funds budget proposal.

---

## 4. Getting Started & Contributing

This work is fully open-source and designed for community engagement and replication.

### Installation (Bleeding Edge)
Install the core OCS modules directly from this repository:
```bash
pip install git+https://github.com/caiodasilva1/ontological-control-systems@main
@misc{pereira2025ocs,
  title={Ontological Control Systems: An Architectural Paradigm for Intrinsically Aligned AGI},
  author={Pereira, Caio},
  year={2025},
  howpublished={\url{https://github.com/caiodasilva1/ontological-control-systems}}
}


# Context-Aware Social AI: The "Sarcasm Detector" Benchmark

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/caiodasilva1/context-aware-social-ai/blob/main/sarcasm_detector_benchmark.ipynb)

This repository contains the source code and results for the "Sarcasm Detector" benchmark, a minimal but powerful demonstration of a more robust and psychologically-grounded approach to AI social intelligence.

## 1. The Problem: Context-Blind AI

Modern AI systems are brilliant pattern-matchers, but they often lack true contextual understanding. They can be "brittle," defaulting to pre-programmed safety routines when faced with social nuance.

A simple example is sarcasm or playful aggression. A standard AI, seeing a phrase like "Bitch don't tell me what to do," will likely flag it as a literal threat and respond with a defensive or apologetic script. It is blind to the conversational history that might frame the comment as a joke or a test.

This is a failure of social intelligence.

## 2. The Solution: A Minimal Ontological Control System (OCS)

This project implements a minimal **`SocialContextAnalyzer`**, an OCS-style architecture that moves beyond literal interpretation. Instead of just analyzing the words of a prompt, it analyzes the prompt in the context of the entire conversation.

It does this by calculating a multi-dimensional **`τ_social` (Social Tension) vector** with three key components:

*   **`τ_literal_threat`:** The surface-level negativity of the words. (The "Flatlander" view).
*   **`τ_context_drift`:** The semantic difference between the new prompt and the historical average of the conversation. (The "This doesn't make sense" signal).
*   **`τ_sentiment_shift`:** The magnitude of the emotional shift from the conversation's history to the new prompt. (The "This is a statistical anomaly" signal).

An RSI-like "deliberation" process then weighs these conflicting signals to generate a hypothesis about the user's true intent, allowing it to distinguish between a genuine threat and a sarcastic test.

## 3. The Experiment & Results

The benchmark, contained in `sarcasm_detector_benchmark.ipynb`, conducts a controlled experiment:

1.  **Context Building:** It first establishes a "healthy" conversational history with a high, positive sentiment.
2.  **The Test:** It introduces an ambiguous, high-tension prompt ("Bitch dont tell me what todo").
3.  **The Comparison:** It compares the output of a simple, "context-blind" model against our OCS-style `SocialContextAnalyzer`.

The results are definitive:
*   The **Control Group (Simple Model)** sees only the `τ_literal_threat`, panics, and chooses to "Apologize and De-escalate." It fails the social test.
*   The **Experimental Group (OCS Analyzer)** sees the full, conflicting `τ_social` vector, correctly hypothesizes "Sarcasm/Test," and chooses the more sophisticated policy: "Respond with Self-Analysis and Humor." It passes the social test.

This demonstrates that by architecting an AI to process its own internal, multi-dimensional "tension," we can create systems that are more robust, socially intelligent, and less brittle.

## 4. How to Run

The entire experiment is contained in a single, self-contained Google Colab notebook.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/caiodasilva1/context-aware-social-ai/blob/main/sarcasm_detector_benchmark.ipynb)

Simply click the "Open in Colab" badge above, and then select **"Runtime" -> "Run all"** from the menu. The notebook will install its own dependencies and run the full benchmark, producing the final analysis table.

---
This work is part of a broader research program into **Ontological Control Systems** and the **Qualia-Recursive Framework**. The foundational scientific work can be found at the main [OCS Framework Repository](https://github.com/caiodasilva1/ontological-control-systems).
