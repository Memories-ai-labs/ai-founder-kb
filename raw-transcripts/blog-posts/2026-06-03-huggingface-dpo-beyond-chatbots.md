# Direct Preference Optimization Beyond Chatbots
# URL: https://huggingface.co/blog/Dharma-AI/direct-preference-optimization-beyond-chatbots
# Date: 2026-06-03
# Source: Hugging Face Blog (Dharma-AI)

**Authors:** Erick Lachmann, Dharma-AI team, Gabriel Pimenta de Freitas Cardoso, and contributors

## Overview

This article examines how Direct Preference Optimization (DPO)—a training technique typically applied to conversational AI alignment—successfully addresses text degeneration in specialized OCR models.

## Key Findings

The research demonstrates that DPO reduces text degeneration across multiple model architectures after supervised fine-tuning (SFT). Text degeneration—where models produce repetition loops instead of accurate transcriptions—persisted even after task-focused training. The authors note that "SFT optimizes for correct outputs, but does not explicitly penalize degeneration."

A second training stage using DPO achieved remarkable results: average degeneration reduction of 59.4%, with peak improvements reaching 87.6%.

## Core Innovation

Rather than filtering degenerate outputs as noise, the pipeline deliberately retained them as rejected examples in preference pairs. This inverts conventional data-cleaning practices. The approach requires three structural conditions: failures must be categorically identifiable, scoreable without human annotation, and sufficiently numerous to generate meaningful training signal.

## Broader Implications

The methodology extends beyond OCR. The authors argue that any structured generation task with identifiable, consistent failure modes can leverage this approach—"a structural question about the task's failure mode, not a question about the model family."

## Technical Insight

The research reveals that task capability and degeneration resistance represent distinct distribution properties, explaining why SFT alone cannot reliably eliminate this failure mode.
