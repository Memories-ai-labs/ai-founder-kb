# MolmoMotion: Language-guided 3D Motion Forecasting
# Source: Hugging Face Blog
# URL: https://huggingface.co/blog/allenai/molmomotion
# Date: 2026-06-17
# Publisher: Hugging Face / Allen Institute for AI

---

MolmoMotion represents a new approach to predicting how objects will move in the future. Rather than simply observing motion that has already occurred, this model anticipates upcoming movement based on visual input, 3D point locations, and written action instructions.

The core innovation involves representing motion as "object-attached 3D points in world space," enabling forecasts without requiring full video rendering. The system satisfies three critical requirements: it remains independent of specific object categories, maintains consistency across different camera angles, and produces outputs directly usable by downstream applications.

## Technical Architecture

Two variants were developed:

**Autoregressive version**: Generates future coordinates sequentially, with each new prediction building on previously generated positions. Emphasizes smooth trajectories when outcomes are well-defined.

**Flow-matching variant**: Operates in continuous 3D space by transforming noise into motion patterns, better suited for scenarios with multiple plausible futures.

Both leverage Molmo 2 as their foundational backbone, enabling connections between language instructions and visual elements.

## Dataset and Benchmark

**MolmoMotion-1M** comprises trajectories from 1.16 million videos — the largest corpus of action-described, object-grounded 3D point trajectories assembled to date. The dataset encompasses 736 motion types across 5.6K distinct objects.

**PointMotionBench** provides human-validated evaluation across 2.7K video clips spanning 111 object categories and 61 motion types.

## Performance

- Exceeded existing 3D forecasting methods on PointMotionBench
- 76.3% success rate on simulated robotics pick-and-place tasks vs. 56.0% for baseline
- Outperformed larger competing systems on 4/5 video generation metrics

## Limitations

Employs eight query points per object — sufficient for trajectory forecasting but insufficient for detailed surface geometry, limiting complex deformable motion handling.
