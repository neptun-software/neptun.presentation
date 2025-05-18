---
layout: default
---

# Technische Umsetzung: KI

<style>
.logo-container {
  background: white;
  border-radius: 24px;
  padding: 1.5rem;
  width: 220px;
  height: 220px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 2rem;
}
</style>

<div class="grid grid-cols-2 gap-16">
  <div>
    <div class="logo-container">
      <img src="https://www.rwkv.com/images/avatar.png" class="w-48" />
    </div>
    <h2 class="text-2xl font-bold mb-4">KI-Basis-Modell</h2>
    <ul class="space-y-2">
      <li>RWKV-5-World-0.4B-v2-20231113-ctx4096 RNN als Basis-Modell</li>
      <li>Vorteile von RNNs und LLMs</li>
    </ul>
  </div>

  <div>
    <div class="logo-container">
      <img src="https://raw.githubusercontent.com/josStorer/RWKV-Runner/3e97b6ff0e3dddf1e1aece8eda843a984ec8d79a/frontend/src/assets/images/logo.png" class="w-24" />
    </div>
    <h2 class="text-2xl font-bold mb-4">Fine-Tuning</h2>
    <ul class="space-y-2">
      <li>RWKV-Runner UI zum Testen- und Trainieren/Fine-Tunen von RWKV-Modellen</li>
      <li>Unsere Modelle sind auf HuggingFace unter neptun-org/neptun.ai herunterladbar</li>
    </ul>
  </div>
</div>
