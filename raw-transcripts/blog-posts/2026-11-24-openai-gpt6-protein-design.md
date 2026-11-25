# GPT-6 models demonstrate intrinsic protein-design capabilities
# URL: https://openai.com/index/gpt-6-models-demonstrate-intrinsic-protein-design-capabilities/
# Date: 2026-11-24
# source: OpenAI Blog

Category: Science / Research

## Summary

OpenAI reports that its GPT-6 model family can design protein structures and amino acid sequences using reasoning and general-purpose code, without calling specialized biology models for those designs. The work is described in a preprint, "GPT-6 as a Universal Foundation Model for Protein Biology." An internal research model matched or beat specialized tools on many tasks, and researchers could steer designs through natural-language prompts about attachment sites and desired shapes.

## Background

Proteins carry out most cellular functions, and their amino acid sequences determine three-dimensional shapes. Designing a protein for a goal means finding both a suitable structure and a sequence that folds into it. Specialized models handle this but require expertise and can't easily accept new kinds of instructions. A general-purpose model could adapt more readily.

## Key findings

- GPT-6.2 designs protein backbones and, in some cases, sequences, mostly without specialized models.
- Designs showed evidence of binding across five targets in lab tests run with partner Onava; specialized models were used to generate sequences and select candidates.
- Redesigned antibody fragments retained binding to their targets.
- The model's written reasoning and code draw on math, physics, chemistry, and biology.

## Computational evaluations

**Minibinder design:** The model followed prompts specifying attachment sites and structural class (helices, strands, or both), including coil and strand counts, with high fidelity.

**Motif scaffolding (MotifBench, 30 tasks):** 43.7% of designs from the internal model succeeded, versus 27.8% for RFdiffusion.

**Fold design (CATH, 200 challenges):** 18.9% passed, versus 17.1% for specialized model Proteina.

**Small-molecule docking:** On PoseBusters, GPT-6.2 matched the experimental pose in 93% of predictions; the internal model scored 96%; DiffDock-L scored 50%. On Scarpino set with bond-atom hints: GPT-6.2 scored 92%, internal model 97%, DiffDock 60%.

**Antibody-target docking:** Mean DockQ rose with each generation: ~0.05 (GPT-5.6) → 0.28 (GPT-6) → 0.57 (GPT-6.2) → 0.81 (internal model).

**Mutation effect ranking:** Across four datasets, GPT-6.2 and internal model outperformed ESM2-650M. Rank correlation on stability set improved from 0.41 (GPT-5.6) to 0.66 (internal model).

**Whole-protein structure prediction:** Average TM-score: 0.16 (GPT-5.6), 0.26 (GPT-6.2), 0.38 (internal model) — well below ESMFold2's 0.93. Remains a clear weakness.

## Laboratory results

**Experiment 1 (de novo minibinders):** Of 322 designs tested against five targets, 35 (10.9%) bound: 5 for PD-L1, 3 for IL-7Rα, 1 for TrkA, 8 for VEGF-A, 18 for IL-17A.

**Experiment 2 (new sequences for known structures):** For MDM2, VEGF-A, PD-1, initial screens found binding in 85%, 62%, 14% of designs respectively. For three unpublished structures, 14 of 107 designs (13.1%) bound.

**Antibody redesign:** For six VHHs targeting IL-4Rα, 128 of 182 designs (70%) showed binding. For fragments of five therapeutic antibodies, 179 of 272 (66%) bound PD-1 or PD-L1.

## Limitations

- Campaign used specialized models (Boltz-2, OpenDDE, ESMFold2) to filter candidates — not fully end-to-end, zero-shot de novo design.
- Full structure prediction from sequence remains much weaker than specialized tools ("jagged" capability frontier).
- Some sequence-recovery results may reflect memorization.
- Binding is only an early step; specificity, stability, biological activity, safety, and efficacy still need validation.

## What's next

OpenAI describes this as early work toward "programmable molecular design," where scientists describe desired molecular behavior in plain language. Planned directions: harder targets, testing downstream biological effects, extending to multi-target binders, RNA, small molecules, PROTACs. Biosecurity risks assessed under the Preparedness Framework.
