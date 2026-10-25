# Awesome Loop: reading guide

[← Back to the paper list](../README.md#papers-20252026)

## Suggested reading order

1. **Why loop?** [Reasoning with Latent Thoughts](https://arxiv.org/abs/2502.17416) and [A Formal Comparison Between Chain of Thought and Latent Thought](https://arxiv.org/abs/2509.25239) for reasoning bias and expressivity.
2. **Large-scale language models:** [Huginn](https://arxiv.org/abs/2502.05171), [Mixture-of-Recursions](https://arxiv.org/abs/2507.10524), and [Ouro](https://arxiv.org/abs/2510.25741) for recurrent cores, token routing, and pretraining.
3. **Make depth usable:** [LoopFormer](https://arxiv.org/abs/2602.11451), [Parcae](https://arxiv.org/abs/2604.12946), and [Residual Scaling](https://arxiv.org/abs/2606.18524) for variable budgets and stability.
4. **Check the comparison budget:** [Iso-Depth Scaling Laws](https://arxiv.org/abs/2604.21106), [Loop the Loopies!](https://arxiv.org/abs/2607.16051), and [SMELT](https://arxiv.org/abs/2609.01343) for controlled scaling evidence.
5. **Serving and memory:** [Parallel Loop Transformer](https://arxiv.org/abs/2510.24824), [MELT](https://arxiv.org/abs/2605.07721), [Looped Latent Attention](https://arxiv.org/abs/2607.15456), and [LoopSpec](https://arxiv.org/abs/2609.17184).
6. **Mechanisms and related reasoners:** [Latent Chain-of-Thought?](https://arxiv.org/abs/2507.02199), [Mechanistic Analysis](https://arxiv.org/abs/2604.11791), [HRM](https://arxiv.org/abs/2506.21734), and [TRM](https://arxiv.org/abs/2510.04871).

## Scope and inclusion policy

**Core** papers repeatedly apply a learned Transformer layer, block, or stack along computational depth, or substantively analyze, train, stabilize, retrofit, route, or accelerate that mechanism. Both fixed and adaptive loop counts qualify. Explicitly looping pretrained layers, partially looped attention, and looped diffusion Transformers are included when recurrence is part of the architecture or inference method.

**Related** marks selected HRM/TRM-family recursive reasoners, equilibrium/feedback reasoning, partial expert sharing, and depth-looped hybrid/SSM language models. These provide useful comparisons but need not implement the same within-token Transformer-depth recurrence. Their summaries state what is actually repeated. **Survey** marks reviews and substantive position/taxonomy papers rather than new architecture results.

Ordinary autoregressive decoding, chain-of-thought generation, agent/tool feedback loops, diffusion denoising schedules alone, and recurrence over sequence time alone do not qualify as core Loop research. A paper that merely mentions a looped model is insufficient. Compare parameter count, training FLOPs, inference FLOPs, cache memory, data, and tuning separately: parameter efficiency alone does not establish compute efficiency.

**Code** links are author- or paper-linked implementations. **Project** and **Model** links are labeled separately. A missing Code link means no public author implementation is listed; it does not establish that none exists. Community implementations are not relabeled as official code.

## Date conventions and ordering

- Use the arXiv **v1 submission date in UTC**, rather than a revision or announcement date. When arXiv explicitly identifies a later record as the same work, preserve the documented precursor's original date.
- For non-arXiv papers, use the primary publication date at its verified precision. Preserve month-only dates as `YYYY-MM`; do not guess a day or infer an original date from the conference year.
- Keep publisher indexing dates labeled as indexing dates, rather than claiming they establish the earliest public release.
- List papers in reverse chronological order, grouped by year and month. Sort same-day entries by title, and place month-only dates after day-dated entries in that month.
- Keep confirmed publications with unresolved first-public dates in their separate table. Count each work once, preserving its original preprint date when it is revised, renamed, or accepted.

## Contributing

Issues and PRs are welcome. Please provide the primary paper URL, arXiv v1 or primary publication date at its verified precision, a brief explanation of what is looped, and any author-linked public code. Add a row in date-descending order, or use the confirmed-publications table if the original date remains unresolved; use the appropriate Core/Related/Survey tag, deduplicate earlier versions, and update the coverage counts and badge together. Preserve original preprint dates when a paper is later accepted or revised.
