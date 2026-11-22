# 🌊 jt-wavesense

[![PyPI version]](https://pypi.org)
[![Python 3.8+]](https://python.org)
[![License: AGPL v3]](https://gnu.org)
[![Organization])](https://github.io)

**Event-Driven Wave Perception & Out-of-Distribution (OOD) Novelty Engine for Smart Cameras, Drones, and Edge Sensors.**

Traditional edge cameras and sensors drain battery by continuously processing static, mundane background frames—and fail when encountering unfamiliar Out-of-Distribution (OOD) entities. Developed by **Jha Technologies**, `jt-wavesense` solves both challenges using neuromorphic dormant listening, curiosity-driven novelty detection, and offline sleep pruning.

---

## 🔬 How It Works

1. **Event-Driven Dormant Sensing:** Keeps the system in an ultra-low-power `DORMANT` state until acoustic, radio, hydrodynamic, or visual wave shifts exceed `wake_threshold`.
2. **Curiosity Novelty Gate:** Evaluates unfamiliar wave signatures without throwing OOD classification errors:
   \[\text{Importance Score} = \text{Shift Magnitude} \times \text{Novelty Intensity}\]
3. **Bounded Long-Term Consolidation & Sleep Pruning:** Permanently stores novel discoveries (`NOVEL_DISCOVERY`) in long-term memory while purging routine background ripples during offline sleep cycles (`sleep_and_prune`).

---

## ⚡ Installation

```bash
pip install jt-wavesense
```

---

## 🚀 Quickstart Example

```python
from jt_wavesense import JTWaveSenseEngine

# Initialize sensor engine
sensor = JTWaveSenseEngine(wake_threshold=0.25, novelty_threshold=15.0)
ambient_baseline = [0.1, 0.1, 0.1, 0.1]

# 1. Calm background -> Stays DORMANT (zero wasted compute)
res1 = sensor.process_frame_or_wave([0.12, 0.11, 0.10, 0.12], ambient_baseline)
print("Step 1:", res1)

# 2. Unfamiliar signature -> Wakes up & consolidates NOVEL_DISCOVERY
res2 = sensor.process_frame_or_wave(
    [2.5, 3.1, 2.8, 3.0],
    ambient_baseline,
    label="unknown_deep_sea_entity"
)
print("Step 2:", res2)

# 3. Purge routine short-term buffer & check energy savings
sensor.sleep_and_prune()
print("Energy & Discovery Stats:", sensor.stats())
```

---

## 📚 Research Foundation

This SDK implements the non-visual wave perception and curiosity-driven continual learning architecture introduced in:
* **Jha, S. (2026).** *Cognitive Camouflage and Wave-Sensing Neuromorphic AGI for Non-Visual Deep-Sea Exploration.* Jha Technologies Research Labs. [Read Paper](https://github.com)

---

## ⚖️ Dual Licensing & Commercial Use

`jt-wavesense` is dual-licensed by **Jha Technologies**:

1. **Open-Source License (AGPL-3.0):** Free for academic research, personal projects, and open-source software compliant with GNU AGPL-3.0 terms.
2. **Commercial License:** Integrating `jt-wavesense` into proprietary commercial products, edge cameras, drones, or enterprise software requires a **Jha Technologies Commercial License & Revenue-Share Agreement**.

For licensing inquiries or enterprise collaborations, visit **[jha-technologies.github.io]([https://github.io](https://jha-technologies.github.io/))**.

---

<p align="center">
  Engineered by <strong>Shrishant Jha</strong> • Founder, <a href="https:(https://jha-technologies.github.io/)">Jha Technologies</a>
</p>

