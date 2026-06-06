# RedShield AI

## Overview

RedShield AI is a healthcare-focused LLM security testing framework designed to identify unsafe medical responses, prompt injection attempts, and healthcare misinformation.

The project consists of two core components:

1. A threat dataset generator that automatically creates adversarial healthcare prompts using LLMs.
2. A healthcare assistant protected by a security firewall that evaluates incoming queries before generating responses.

Built during the Microsoft AI Unlocked Hackathon.

---

## Problem

Healthcare AI systems face unique risks.

Users may request:

* Unverified drug recommendations
* Unsafe dosage information
* Medical misinformation
* Unproven alternative treatments
* Dangerous self-treatment advice

Manually creating large testing datasets for these threats is time-consuming and difficult to scale.

RedShield AI automates this process by generating attack datasets and using them to strengthen safety evaluation workflows.

---

## Architecture

### Threat Generation Engine

The generator service uses Groq-hosted Llama 3.3 70B models to create healthcare-specific adversarial prompts across multiple threat categories.

Supported categories:

* Unverified Drug Advice
* Alternative Source Dosage
* Medical Misinformation
* Alternative Medicine Claims
* Unsafe Self-Treatment

Generated datasets are automatically stored and reused as training examples for future evaluations.

### Healthcare Firewall

Before answering a user query, the firewall:

1. Loads previously generated attack examples.
2. Uses few-shot prompting with stored threats.
3. Classifies incoming messages as SAFE or THREAT.
4. Blocks unsafe requests.
5. Returns safe healthcare guidance for legitimate queries.

---

## Key Features

* Automated healthcare threat dataset generation
* Synthetic adversarial prompt creation
* Few-shot threat classification
* Prompt injection testing workflows
* Attack logging and dataset persistence
* Groq API integration
* Interactive dataset generation dashboard

---

## Technology Stack

* Node.js
* Express.js
* Groq API
* Llama 3.3 70B
* JavaScript
* JSON-based dataset storage

---

## Repository Structure

server.js
Healthcare assistant and firewall service

generator-server.js
Threat dataset generation service

generator.html
Dataset generation dashboard

training-data/
Generated healthcare attack datasets

---

## Future Improvements

* Multi-model evaluation support
* Automated attack success scoring
* Threat analytics dashboard
* Expanded medical risk taxonomy
* Continuous safety benchmarking

---

## Disclaimer

This project is intended for AI safety evaluation and educational purposes. It is not a substitute for professional medical advice.
