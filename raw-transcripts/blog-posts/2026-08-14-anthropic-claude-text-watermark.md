# How Claude's text watermark works
# URL: https://www.anthropic.com/news/claude-text-watermark
# Date: 2026-08-14
# Source: Anthropic News

## Overview

Anthropic is implementing text watermarking in Claude to comply with the EU AI Act. The technique, based on Google DeepMind's SynthID-Text method, embeds an undetectable pattern in generated text by altering the source of randomness used when selecting words.

## How It Works

Rather than using arbitrary random number generators, watermarking uses a cryptographic key and preceding context to determine word selection. As Anthropic explains: "the words that Claude picks are still random, but now, one can check the sequence of words and see if it's consistent with the choices Claude would make if it was using the key."

## User Impact

- **No quality degradation**: Watermarked text is indistinguishable from unwatermarked versions to readers
- **No performance cost**: Zero impact on speed or pricing since no extra tokens are generated
- **No privacy concerns**: Watermarks contain no identifying information about users or organizations
- **Limited scope**: Watermarking only applies to words Claude actively generates, not heavily edited human text

## Technical Limitations

The watermark works best on longer, creative passages with multiple equivalent word choices. It's less effective on:
- Factual statements requiring specific accuracy
- Code (where exact syntax matters)
- Edited rather than newly written content

## Detection and Verification

Anthropic plans to release a watermark detection API, allowing verification of Claude's involvement. However, the watermark cannot distinguish between "Claude wrote this" and "Claude heavily edited this," nor identify other AI systems' outputs.

## Context

This follows significant user backlash (Aug 12, TechCrunch) when users learned that watermarks could expose AI use in workplace/academic contexts. Anthropic's invisible+persistent approach contrasts with Google's visible+removable watermark approach announced the same week.
