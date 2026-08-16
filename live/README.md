# Live playable demo (cluster-side)

The interactive demo runs the trained Logic Engine as the game server on a GPU node.

```bash
# on the cluster, inside the AgentWorld project
sbatch slurm/demo_server.sbatch     # prints <node> and port 8777 in its log

# on your laptop
ssh -L 8777:<node>:8777 <cluster-login-host>
# then open http://localhost:8777
```

**Multiplayer:** every browser that opens the page claims its own player slot
(teams auto-balanced; extra visitors become spectators). Each person tunnels the
same port and simply opens the URL — no accounts, no setup.

Controls: `WASD` move · `Q/E` turn · `J` wide beam · `K` long beam.
Toggles: learned/teacher renderer, flat/iso theme, shadow engine on/off,
world size (official 23×23 Melting Pot arena … 72×72) and player count.

What you are looking at: the primary world you play in is advanced **only** by the
5.3M-parameter world model (no game engine in the loop); the optional shadow world runs
ground-truth physics on the same joint actions + randomness, so the live position-agreement
bar is an honest, real-time measurement of model error.

`frontend.html` is the exact browser client the server ships.
