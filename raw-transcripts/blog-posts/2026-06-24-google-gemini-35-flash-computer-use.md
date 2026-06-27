Title: Introducing Computer Use in Gemini 3.5 Flash
Author: Mateo Quiros (Product Manager, Google DeepMind)
URL: https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-computer-use-gemini-3-5-flash/
Date: 2026-06-24
Source: Google DeepMind Blog

---

# Introducing Computer Use in Gemini 3.5 Flash

Computer use is now integrated as a built-in tool in Gemini 3.5 Flash, enabling developers to construct agents capable of interacting across multiple platforms. Previously exclusive to a standalone Gemini 2.5 model, this capability is now native to the main Flash version.

The model excels at function calling and using integrated tools like Search and Maps. With computer use functionality, developers can reliably build custom agents that observe, reason, and execute actions across browser, mobile, and desktop environments. This advancement supports extended automation tasks, including continuous software testing and professional application workflows.

## Performance & Availability

Developers and enterprises can access computer use through the Gemini API and Gemini Enterprise Agent Platform. Benchmarks demonstrate improvements in performance metrics.

Demonstrated applications include analyzing app features and auditing documentation for accessibility compliance.

## Safety Implementation

Google employs targeted adversarial training to mitigate prompt injection risks. Two optional enterprise safeguards are available:

- User confirmation requirements for sensitive operations
- Automatic task termination upon detecting indirect prompt injection attempts

The company recommends a "defense-in-depth" strategy combining these features with secure sandboxing, human oversight, and strict access controls.

## Getting Started

- **Demo:** Test capabilities at a demo hosted by Browserbase
- **Documentation:** Access the Gemini API and Enterprise Agent Platform guides
- **Code:** Review the reference implementation on GitHub

Customer testimonials highlight value delivery across organizations like Browserbase, Browser Use, and UIPath.
