# Awesome Loop: reading and curation guide

[← Back to the paper list](../README.md#papers-20252026)

本仓库聚焦在深度方向复用 Transformer 层、模块或层组的 Loop / Looped Transformer：涵盖架构、理论、训练与稳定性、自适应深度、机制分析、推理系统及跨模态应用；相关递归推理单独标注。

## Snapshot and date conventions

- **Last audited:** `2026-10-20`.
- **Main window:** `2025-01-01` through `2026-10-20`.
- **Main catalog:** **398 deduplicated papers** = **306 core** + **89 related** + **3 surveys/position papers**. The dated table has **393 papers** (**76 dated 2025**, **317 dated 2026**); a separate short table retains **5 confirmed publications with unresolved first-public dates**. **118 entries** link verified public author/paper implementation code. Earlier preprints with verified 2025 venues are listed separately and excluded from these counts.
- **Placement:** one reverse-chronological dated timeline, grouped by year and month; same-day entries are sorted by title. Month-only dates are preserved and placed after day-dated entries in the same month, without asserting an unknown day. The Track column identifies scope and topic without splitting the timeline.
- **Dates:** arXiv **v1 submission date** in UTC, rather than latest revision or announcement date; a documented precursor supplies the date when arXiv explicitly identifies a later record as the same work. Non-arXiv entries use a verified primary publication date or month, including publisher-registered online dates, with the date basis recorded in the audit. IEEE Xplore addition dates are labeled as such and are not asserted to be earliest public dates. Conference year never replaces a known original preprint date; recognized conference papers are retained even when their exact first-public date is unresolved.
- **Latest refresh:** **134 main-catalog additions** since the 2026-10-15 snapshot, including historical gaps and recent submissions. The [2026-10-20 audit](search-audit-2026-10-20.md) records primary evidence, aliases, exclusions, and pending candidates; the [previous 323-candidate ledger](search-audit-2026-10-15.md) remains available.
- **Evidence:** titles, dates, and relevance were checked against primary paper records and abstracts, with selected full-text/project checks for ambiguous mechanisms, aliases, and code. This is a dated literature snapshot; it does not claim exhaustive coverage or independent reproduction. Paper inclusion does not imply peer review.

## Scope and inclusion policy

**Core** papers repeatedly apply a learned Transformer layer, block, or stack along computational depth, or substantively analyze, train, stabilize, retrofit, route, or accelerate that mechanism. Both fixed and adaptive loop counts qualify. Explicitly looping pretrained layers, partially looped attention, and looped diffusion Transformers are included when recurrence is part of the architecture or inference method.

**Related** marks selected HRM/TRM-family recursive reasoners, equilibrium/feedback reasoning, partial expert sharing, and depth-looped hybrid/SSM language models. These provide useful comparisons but need not implement the same within-token Transformer-depth recurrence. Their summaries state what is actually repeated. **Survey** marks reviews and substantive position/taxonomy papers rather than new architecture results.

Ordinary autoregressive decoding, chain-of-thought generation, agent/tool feedback loops, diffusion denoising schedules alone, and recurrence over sequence time alone do not qualify as core Loop research. A paper that merely mentions a looped model is insufficient. Compare parameter count, training FLOPs, inference FLOPs, cache memory, data, and tuning separately: parameter efficiency alone does not establish compute efficiency.

**Code** links are author- or paper-linked implementations. **Project** and **Model** links are labeled separately. A missing Code link means no public author implementation was verified in this audit, rather than proof that none exists. Community implementations are not relabeled as official code.

The README groups the dated timeline by year and month for navigation. Entries retain the ordering and date precision documented above.

## Suggested reading order

1. **Why loop?** [Reasoning with Latent Thoughts](https://arxiv.org/abs/2502.17416) and [A Formal Comparison Between Chain of Thought and Latent Thought](https://arxiv.org/abs/2509.25239) for reasoning bias and expressivity.
2. **Large-scale language models:** [Huginn](https://arxiv.org/abs/2502.05171), [Mixture-of-Recursions](https://arxiv.org/abs/2507.10524), and [Ouro](https://arxiv.org/abs/2510.25741) for recurrent cores, token routing, and pretraining.
3. **Make depth usable:** [LoopFormer](https://arxiv.org/abs/2602.11451), [Parcae](https://arxiv.org/abs/2604.12946), and [Residual Scaling](https://arxiv.org/abs/2606.18524) for variable budgets and stability.
4. **Check the comparison budget:** [Iso-Depth Scaling Laws](https://arxiv.org/abs/2604.21106), [Loop the Loopies!](https://arxiv.org/abs/2607.16051), and [SMELT](https://arxiv.org/abs/2609.01343) for controlled scaling evidence.
5. **Serving and memory:** [Parallel Loop Transformer](https://arxiv.org/abs/2510.24824), [MELT](https://arxiv.org/abs/2605.07721), [Looped Latent Attention](https://arxiv.org/abs/2607.15456), and [LoopSpec](https://arxiv.org/abs/2609.17184).
6. **Mechanisms and related reasoners:** [Latent Chain-of-Thought?](https://arxiv.org/abs/2507.02199), [Mechanistic Analysis](https://arxiv.org/abs/2604.11791), [HRM](https://arxiv.org/abs/2506.21734), and [TRM](https://arxiv.org/abs/2510.04871).

## Version notes and unresolved candidates

- **One work, two arXiv records:** [To CoT or To Loop?](https://arxiv.org/abs/2505.19245) explicitly points to [A Formal Comparison Between Chain of Thought and Latent Thought](https://arxiv.org/abs/2509.25239) as its latest version. One row is retained, dated `2025-05-25`; the newer record's own v1 is `2025-09-25`.
- **Renamed papers:** [Think-at-Hard](https://arxiv.org/abs/2511.08577) previously used “Selective Latent Iterations to Improve Reasoning Language Models”; [Gated Recurrent Transformers](https://arxiv.org/abs/2608.15062) appears as “RecurrentGPT” in older indexes. Titles follow the current primary records, without creating duplicate entries.
- **Acronym collision:** Yu et al.'s [LoopCD](https://arxiv.org/abs/2609.24196) and Liu et al.'s [Decoding Looped Transformers Better for (Almost) Free](https://arxiv.org/abs/2610.02185) are different papers with different authors and arXiv IDs, both using the LoopCD name. They are retained separately.
- **Corrected findings:** [Relational Preference Encoding](https://arxiv.org/abs/2604.09870) carries a v2 erratum for ordering artifacts and train/test leakage; its original headline accuracies and inverted-polarity claim are not retained. [What Makes Looped Transformers Perform Better](https://arxiv.org/abs/2510.10089) dropped “(Provably)” from its title; its landscape-bias account is not presented as an unconditional superiority theorem.
- **Date traps:** [Rotate the Loop](https://arxiv.org/abs/2610.14030) has a `2610` identifier but a `2026-09-30` v1 timestamp. The [2026 survey](https://www.preprints.org/manuscript/202610.1404) was submitted on October 12 and publicly posted on October 15; it is labeled Survey and is not peer-reviewed.
- **Code availability:** the paper-provided [Loopy](https://arxiv.org/abs/2610.05265) repository returned public 404, so no public Code link is advertised. Ouro's official [project](https://ouro-llm.github.io/) and model files are linked; its community training reimplementation is not labeled official training code.
- **Resolved mechanism:** [CHERRY's full text, section 4.3.2](https://arxiv.org/html/2606.31796v2#S4.SS3.SSS2) explicitly unrolls a shared Transformer core between a prelude and coda. The earlier abstract-only uncertainty was insufficient; CHERRY is now included.
- **Publisher-date convention:** [SAI](https://ieeexplore.ieee.org/document/11161072/) is dated `2025-09-26` using its verified IEEE Xplore addition date; the ICC conference was June 8–12. Its earliest public date is not established, and the indexing date is labeled explicitly rather than treated as a preprint date.
- **Conference-only metadata:** ACL/CVPR entries with only a publication month retain `YYYY-MM`. [ChainGPT](https://proceedings.iclr.cc/paper_files/paper/2026/hash/74aec30590e07dbe2e29879f9df14fb2-Abstract-Conference.html) and [MoDr](https://proceedings.iclr.cc/paper_files/paper/2026/hash/8a81180649011d1690e05c68bfeaa57c-Abstract-Conference.html) are retained in the confirmed-publications table; OpenReview access challenges still prevent verification of their exact original public dates.
- **Part I is now a formal paper:** [Towards Looped Models Done Right, Part I](https://arxiv.org/abs/2610.23036) was submitted on `2026-10-16`, following an earlier blog resource; it is counted once as a paper. [Part II](https://arxiv.org/abs/2610.06833) remains a distinct paper dated `2026-10-05`. [Polymorphic Universal Transformer](https://aclanthology.org/2026.acl-long.1809/) and the original [LoopCoder](https://aclanthology.org/2026.findings-acl.796/) have official ACL records and are included even without verified arXiv IDs. LoopCoder and LoopCoder-v2 are distinct papers.

- **Formal-title aliases:** [Zero Token-Driven Deep Thinking](https://arxiv.org/abs/2502.12214) and [Efficient Transformer Parameter Reuse via Zero-Token Mechanism](https://aclanthology.org/2026.findings-acl.711/) are one work, retained at the original `2025-02-17` arXiv date.
- **More revision caveats:** [HRM: Perspectives and Misconceptions](https://arxiv.org/abs/2510.00355) reports errors and changed conclusions in v2; the summary avoids its removed findings. [Flow Reasoning Models](https://arxiv.org/abs/2606.29150) has differing abstract-page and HTML titles; these are one identifier, not two papers.
- **Additional date and code checks:** [The Ignition Index](https://arxiv.org/abs/2608.05160) has a `2608` identifier but a `2026-05-26` v1 date. TRM-QE's paper-linked repository returned public 404 during this refresh, so no available Code link is shown. Full dispositions and unresolved publisher-only candidates are in the [latest audit](search-audit-2026-10-20.md).

## Search method and exclusions

The audit combined web and arXiv searches for `looped transformer`, `loop transformer`, `looped language model`, `recurrent depth`, `depth-recurrent`, `recursive transformer`, `universal transformer`, `weight-tied`, `adaptive recurrence`, `looped MoE`, and `latent reasoning`, with citation/project follow-up and recent September–October 2026 searches. Candidate discovery was cross-checked against [HJSang's looped-Transformer list](https://github.com/HJSang/awesome-looped-transformers) and [Awesome Loop Models](https://github.com/huskydoge/Awesome-Loop-Models); metadata and summaries were checked against the individual primary sources linked in each row. The October 20 refresh additionally checked the now-public [survey author corpus](https://github.com/ArminAzizi98/looped-lm-survey), screening 143 unmatched arXiv identifiers and 26 selected publisher-only records; it did not adopt that corpus's own scope or completeness claims.

The audit excludes generic agent loops, token-level repetition in generated reasoning, recurrent GNNs, and broad fixed-point or time-series SSM papers without a substantive Transformer-depth contribution. For example, [Hidden Decoding at Scale](https://arxiv.org/abs/2607.08186) expands the token stream, [Full-bandwidth transformer](https://arxiv.org/abs/2608.08888) feeds state between tokens, and [Bifurcation Models](https://arxiv.org/abs/2605.07277) studies generic scientific equilibrium dynamics. These are not counted as core looped-Transformer papers. The explicitly Related row for [Recurrent Looped Transformer](https://arxiv.org/abs/2610.07591) records its token-state recurrence so its title is not mistaken for a within-token depth-loop design.

Search indexes can lag, and conference-only or unindexed manuscripts can be missed. Ambiguous mechanisms and dates are disclosed above. Product-architecture rumors, social posts, model cards without a formal paper, and implementation repositories alone are not counted as papers. New versions are not new papers; reported empirical improvements remain conditional on each paper's experimental protocol.

## Contributing

Issues and PRs are welcome. Please provide the primary paper URL, arXiv v1 or primary publication date at its verified precision, a brief explanation of what is looped, and any author-linked public code. Add a row in date-descending order, or use the confirmed-publications table if the original date remains unresolved; use the appropriate Core/Related/Survey tag, deduplicate earlier versions, and update the coverage counts and badge together. Preserve original preprint dates when a paper is later accepted or revised.
