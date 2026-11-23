# Track A Proposal: Reproducing and Extending iA* for Grid-Based Path Planning

## 1. Benchmark paper

Xiangyu Chen, Fan Yang, and Chen Wang, “iA*: Imperative Learning-based A* Search for Path Planning,” *IEEE Robotics and Automation Letters*, vol. 10, no. 12, pp. 12987–12994, 2025. DOI: [10.1109/LRA.2025.3625500](https://doi.org/10.1109/LRA.2025.3625500).

- Paper/PDF: https://arxiv.org/abs/2403.15870
- Official authors’ Python code: https://github.com/sair-lab/iAstar
- Project page: https://sairlab.org/iastar/
- Dataset and pretrained models: linked in the official GitHub README.
- Venue rank: *IEEE Robotics and Automation Letters* is Q1 in the 2025 SCImago/SJR listing (2025 SJR: 1.589).

## 2. Result to reproduce

I will reproduce the **64×64 Motion Planning (MP) dataset results in Table I**, comparing the authors’ iA* method with classical A*.

The primary metric will be **Exp (reduction ratio of node explorations/search area)**. The paper reports **69.4% (±2.9)** for iA* on the 64×64 MP maps, compared with **0%** for A* (the reference baseline). I will also record the reported secondary metrics: **Rt = 50.4% (±5.7)** for iA*, and **path length (PL) = 75.0 (±3.4)**, compared with A* PL = 73.0 (±3.1). I will compare my measured values with these paper results and report any differences.

## 3. Research question

**On 64×64 Motion Planning maps, how does increasing obstacle density by adding obstacles to otherwise free cells affect iA*’s search-area reduction (Exp), runtime reduction (Rt), path length (PL), and success rate compared with the original maps?**

## 4. Data and compute

I will use the publicly available 64×64 MP benchmark maps and the authors’ released pretrained iA* model, with the official Python implementation as the starting point. Experiments will use Python and PyTorch in Google Colab with its available NVIDIA Tesla T4 GPU. My HP laptop will be used for code editing, result analysis, plots, and report preparation. I will first verify the authors’ inference/benchmark workflow and compatible dependencies; I will not assume that the current Colab environment is already compatible.

For the extension, I will create controlled higher-obstacle-density versions of selected test maps, preserve the start and goal cells, and retain only maps for which a valid route exists. I will use the same maps and start/goal pairs for the original and modified conditions.

## 5. Plan and fallback

- **By 4 December:** Set up the official code and required data/model; run a small 64×64 test; obtain A* and iA* outputs; calculate Exp, Rt, PL, and success rate; compare the reproduction with Table I.
- **By 18 December:** Complete the selected 64×64 MP reproduction, run the obstacle-density extension, prepare comparison tables and plots, document setup and deviations, and complete the 4–6 page IEEE-style report.
- **Fallback:** If the full benchmark or dependency setup cannot be completed, run the official pretrained iA* model on a smaller, clearly reported subset of 64×64 MP maps and compare it with A* on the same instances. If the pretrained model cannot be loaded, report the setup limitation honestly and reduce the experiment to the smallest reproducible subset rather than claiming the paper’s result was reproduced.

---
**Repository:** https://github.com/Kainat256/iAstar-Path-Planning-Capstone
