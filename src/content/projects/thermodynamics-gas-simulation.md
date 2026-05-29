---
title: Thermodynamics Gas Simulation
description: Built a Python gas model for Physics Thermodynamics with elastic particle collisions, pressure tracking, and live temperature visualization.
github: taschnell/gas_model
importance: 30
category: Past projects
---

<div style="display:flex; flex-wrap:wrap; gap:1.5rem; align-items:flex-start;">
  <div style="flex:1 1 360px; min-width:280px;">
    <p>Built a Python gas model for a Physics Thermodynamics class project that simulates 5,000 point particles undergoing elastic collisions in a 2D rectangular container. The simulation advances in fixed timesteps (configurable dt), uses a spatial grid to reduce pairwise checks, and resolves elastic collisions conserving momentum and energy. Pressure is measured from momentum transfer during wall bounces (collected per second) and compared to the ideal gas prediction computed from particle count, area, and measured temperature. Speeds are streamed to <code>speeds.csv</code> for live histogram and kinetic-temperature plotting; optional frame dumps produce the animation shown at right. The model was validated by comparing time-averaged measured pressure to the ideal-gas expectation (percent differences typically <~3% for these parameters).</p>
  </div>
  <div style="flex:0 0 360px; max-width:360px;">
    <img src="/assets/video/ThemoSimVideo.gif" alt="Thermodynamics gas simulation animation" style="width:100%; height:auto; display:block; border-radius:0.75rem; box-shadow: 0 20px 45px rgba(0,0,0,0.12);" />
  </div>
</div>

<!-- Terminal output — full width, sits below the GIF and above the graph -->
<div style="margin-top:1rem; width:100%;">
  <pre style="background: var(--global-surface-color); color: var(--global-text-color); padding:1rem; border-radius:0.75rem; overflow-x:auto; border:1px solid var(--global-divider-color);"><code>Bounces/sec: 2671, Actual Pressure: 2.596e-23 Pa, Ideal Pressure: 2.556e-23, Percent Diff: 1.58%
Bounces/sec: 2538, Actual Pressure: 2.481e-23 Pa, Ideal Pressure: 2.556e-23, Percent Diff: 2.92%
Bounces/sec: 2660, Actual Pressure: 2.551e-23 Pa, Ideal Pressure: 2.556e-23, Percent Diff: 0.181%
Bounces/sec: 2565, Actual Pressure: 2.508e-23 Pa, Ideal Pressure: 2.556e-23, Percent Diff: 1.85%
Bounces/sec: 2623, Actual Pressure: 2.548e-23 Pa, Ideal Pressure: 2.556e-23, Percent Diff: 0.301%
Bounces/sec: 2657, Actual Pressure: 2.543e-23 Pa, Ideal Pressure: 2.556e-23, Percent Diff: 0.476%
Bounces/sec: 2565, Actual Pressure: 2.495e-23 Pa, Ideal Pressure: 2.556e-23, Percent Diff: 2.37%</code></pre>
</div>

<div style="margin-top:2rem;">
  <img src="/assets/img/ThermoSimGraph.png" alt="Simulation speed histogram" style="width:100%; height:auto; display:block; border-radius:0.75rem;" />
</div>
