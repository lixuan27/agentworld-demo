# ARBITER · SkirmishCTF — a playable multiplayer world model

**Showcase site:** https://lixuan27.github.io/agentworld-demo/

Reproduces and extends **MASS** (arXiv 2608.06257, "Multiplayer World Models with
Authoritative Shared State") in a new scene: a paintball capture-the-flag team world whose
rules come verbatim from the public Melting Pot substrate `paintball__capture_the_flag`
(Apache-2.0). Every model — the 5.3M Logic Engine and both renderers (flat 2D / isometric
2.5D) — is trained from scratch; no pretrained components anywhere.

- One typed authoritative state is the only recurrent memory; all views decode from it.
- Population invariance measured exactly: PIE = 0.00000 with up to 48 injected distractors.
- Trained on N ≤ 8 players, still places 77% of 1,024 players exactly right in one step.
- Renderer theme swap on frozen dynamics: flat PSNR 40.0 / iso PSNR 51.3, from scratch.
- Honest reporting: the pre-registered chain-conditioning fix failed and is documented as such.

`live/` documents the interactive server where you play *inside* the model.
