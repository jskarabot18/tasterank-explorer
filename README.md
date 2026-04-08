# TasteRank Explorer

An interactive force-directed network visualization of wine grape variety similarity, based on WSET Systematic Approach to Tasting (SAT) sensory profiles. The graph uses eigenvector centrality to rank 101 grape varieties by their structural importance in a similarity network, and Louvain community detection to identify six natural clusters.

## Live Site

**[→ Open TasteRank Explorer](https://jskarabot18.github.io/tasterank-explorer/)**

## What's Inside

- **Force-directed graph** built with [D3.js](https://d3js.org/) showing 101 grape varieties and 341 similarity edges
- **TasteRank scores** — eigenvector centrality measuring each variety's structural importance in the network (how similar it is to other highly-connected varieties)
- **6 communities** detected via Louvain algorithm:
  - C0 · Full-bodied Mediterranean Reds (Sagrantino, Nero d'Avola, Syrah, Mourvèdre…)
  - C1 · Light & Aromatic cross-boundary (Riesling, Sauvignon Blanc, Assyrtiko…)
  - C2 · Mid-weight Structured Reds (Pinot Noir, Nebbiolo, Sangiovese, Nerello Mascalese…)
  - C3 · Rich Textural Whites (Chardonnay, Viognier, Marsanne, Sémillon…)
  - C4 · Mineral / Crisp Whites (Grüner Veltliner, Verdicchio, Chenin Blanc…)
  - C5 · Lean Neutral & Aromatic Whites (Gewürztraminer, Muscat Blanc, Ugni Blanc…)
- **SAT profile visualization** — 13-dimension radar for each variety (color depth, aromatic intensity, floral, fruit ripeness, herbal/earthy, spice/oak, acidity, tannin, body, alcohol, flavor intensity, finish, complexity)
- **Cosine similarity edges** connecting each variety to its K=5 nearest neighbors

## Files

| File | Description |
|------|-------------|
| `index.html` | Self-contained interactive network visualization |
| `TasteRank_Summary.pdf` | Overview of methodology and key findings |
| `TasteRank_Technical_Appendix.pdf` | Full technical details: graph construction, centrality math, community detection |
| `TasteRank_Data_Appendix.pdf` | Complete SAT profiles, rankings, and similarity matrices |
| `README.md` | This file |
| `LICENSE` | CC BY-NC 4.0 license |

## How to Use

Open the [live site](https://jskarabot18.github.io/tasterank-explorer/) in any modern browser. Click any node to see its SAT profile and connected varieties. Click a community in the left panel to isolate it. Use the search bar to find a specific grape. Drag nodes to rearrange the layout. Press `Esc` to reset.

To run locally, open `index.html` in a browser — no build tools or server required.

## Methodology

Each grape variety is profiled on 13 sensory dimensions (scored 0–5) based on the WSET Level 3/4 Systematic Approach to Tasting framework. Pairwise cosine similarity is computed across all 101 varieties, and each variety is connected to its 5 most similar neighbors (K-nearest-neighbor graph). Eigenvector centrality on this network produces the TasteRank score — varieties that are similar to other highly-central varieties score highest. Community structure is detected using the Louvain algorithm, yielding six coherent clusters that align well with traditional grape family intuitions while revealing some unexpected cross-boundary connections.

## Key Findings

- **Sagrantino** ranks #1 — the most structurally central grape in the network, deeply connected to the Mediterranean red cluster
- **Community boundaries track sensory logic**, not geography: Nerello Mascalese clusters with Pinot Noir (C2), not with its Sicilian neighbor Nero d'Avola (C0)
- **Riesling and Assyrtiko** are structural outliers among whites — high acidity and complexity place them in the Light & Aromatic community (C1) rather than with mineral whites

## License

This work is licensed under [Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)](https://creativecommons.org/licenses/by-nc/4.0/). You are free to share and adapt this material for non-commercial purposes with attribution.

---

*Jure Skarabot · New York*
