# Transformer Training 12 — Training over Slow Links: Top-k, Error Feedback, DeMo, DiLoCo

Between data centres the link can be a thousand times slower than NVLink, and sending the whole gradient every step stops being affordable. Send less (top-k, DeMo), or less often (DiLoCo): the mechanisms, the bytes, and a toy run of all four, with the real measurements one link away.

**Live site:** https://brendanjameslynskey.github.io/Transformer_Training_12_Training_over_Slow_Links/

WAN bandwidth; top-k sparsification; error feedback; why compressed vectors are all-gathered; DeMo; DiLoCo; a four-worker toy of all four (labelled a toy, with the Compute in Transit results site for real runs); bytes against bandwidth; queueing and stragglers.

## Live, animated companion

This deck is the slide companion to Part 2 (Training) of [Transformer Decoder Explained](https://transformer-training-explained.vercel.app/training), where the same model trains in your browser:

- [Chapter 13: Training over slow links](https://transformer-training-explained.vercel.app/training/13-slow-links)

## Where the numbers come from

Every measured number on these slides comes from the site's [results.md](https://github.com/BrendanJamesLynskey/transformer-explainer/blob/main/results.md) (seeded NumPy reference runs; CI recomputes them), filled in at build time from its `results.json`. Numbers from papers are cited on the slide with a link. The model is tiny (5,376 parameters, one book, a CPU): its runs show mechanisms, not what happens at scale, and the slides say so where it matters. GPU runs of the site's Colab notebooks are pending; no GPU number appears here.

Part of the [Transformer Training sub-hub](https://github.com/BrendanJamesLynskey/LLM_Hub_Transformer_Training) &middot; [LLMs hub](https://github.com/BrendanJamesLynskey/LLMs)
