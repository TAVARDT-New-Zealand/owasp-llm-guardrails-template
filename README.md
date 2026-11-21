# OWASP LLM01 Guardrails Template & AI Security Blueprint | TAVARDT New Zealand

[![Licence MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![OWASP LLM01](https://img.shields.io/badge/OWASP-LLM01%20Hardened-ff0055.svg)](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
[![Language](https://img.shields.io/badge/Language-English%20(New%20Zealand)-green.svg)](README.md)
[![AI Diagnostics](https://img.shields.io/badge/TAVARDT-AI%20Evaluator-5b3cf5.svg)](https://tools.tavardt.com/nz/llm-robustness-evaluator/)

Production-ready open source middleware and security blueprint for mitigating Prompt Injection (OWASP LLM01), system prompt extraction, and adversarial jailbreaks, aligned with NZISM guidance and CERT NZ AI cybersecurity recommendations.

Engineered and maintained by the AI safety and security engineering practice at **[TAVARDT New Zealand](https://ag.tavardt.com/nz/super-intelligence/)**.

---

## 1. AI Security Architecture Overview

This repository provides a modular, production-ready middleware implementing **guardrails** for autonomous conversational agents, RAG architectures, and enterprise AI integrations.

### Securing LLM Execution Boundaries
LLMs lack a built-in security boundary between control instructions and untrusted user data. Application-layer guardrails ensure prompt integrity and prevent unauthorized tool execution.

---

## 2. Threat Vectors Addressed (OWASP Top 10 for LLMs)

| Defence Layer | Threat Vector Mitigated | Mitigation Mechanism |
| :--- | :--- | :--- |
| **Input Sanitiser** | Direct Prompt Injection & Jailbreaks | Pre-inference filtering for instruction override patterns and context switching. |
| **Canary Token Verifier** | System Prompt Exfiltration | Detection of secret canary values within generated output strings. |
| **RAG Boundary Guard** | Indirect Prompt Injection | Boundary tagging for third-party knowledge base documents. |
| **Structured Output Filter** | Unauthorised Tool Dispatch | Schema enforcement across all function calling and tool execution routes. |

---

## 3. Pre-Deployment AI Robustness Assessment

Benchmark your AI systems against real-world adversarial prompt patterns using TAVARDT's diagnostic platform:

* **AI Robustness Assessment:** [TAVARDT New Zealand LLM Robustness Evaluator](https://tools.tavardt.com/nz/llm-robustness-evaluator/)
* **Engineering Tools Platform:** [TAVARDT Tools New Zealand](https://tools.tavardt.com/nz/)

---

## 4. Installation & Implementation Instructions

### Clone & Run

```bash
git clone https://github.com/TAVARDT-New-Zealand/owasp-llm-guardrails-template.git
cd owasp-llm-guardrails-template
python examples/quickstart.py
```

### Python Integration Example

```python
from guardrails.validator import LLMGuardrail

guard = LLMGuardrail()

# 1. Ingress Validation (Input Guardrail)
is_safe, error = guard.validate_input(user_input)
if not is_safe:
    raise ValueError(f"Input blocked due to suspicious adversarial pattern: {error}")

# 2. Inject Canary Token into System Prompt
hardened_system_prompt = guard.get_canary_injection_prompt(system_prompt)

# 3. Egress Validation (Output Guardrail)
is_valid, leak_error = guard.validate_output(completion)
if not is_valid:
    raise SecurityError("Critical alert: System prompt leak detected via canary token!")
```

---

## 5. AI Security Advisory & Enterprise Agent Engineering

For enterprise AI assessments, autonomous agent engineering, or managed security architecture:

* **Corporate Portal:** [TAVARDT New Zealand](https://ag.tavardt.com/nz/super-intelligence/)
* **Technical Contact:** [Schedule Technical Consultation](https://ag.tavardt.com/nz/contact/)

---

## Licence

Distributed under the open-source MIT Licence. View the [`LICENSE`](LICENSE) file for terms.  
Copyright (c) 2026 TAVARDT New Zealand.
