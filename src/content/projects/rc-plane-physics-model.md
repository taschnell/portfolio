---
title: RC Plane Physics Model
description: Developed a Python model of RC aircraft aerodynamics that matched real-world data within 3% error.
github: taschnell/RcPlaneSim
importance: 40
category: Past projects
---

<div style="display:flex; flex-wrap:wrap; gap:1.5rem; align-items:flex-start;">
  <div style="flex:1 1 360px; min-width:280px;">
    <p>This RC Plane Modeling Project was produced by Johann Kaufmann, Teo Schnell, and Chris Chavez. It builds a dynamic aircraft model that responds to motor wattage and incoming airspeed, using measured propeller data and GPS flight telemetry to keep the simulation grounded in reality.</p>
    <p>The model is based on NASA propeller thrust theory from <a href="https://www1.grc.nasa.gov/beginners-guide-to-aeronautics/propeller-thrust/" target="_blank" rel="noopener noreferrer">NASA’s guide</a>. Using SciPy, we fit the relationship between motor wattage and exhaust velocity `Ve`, then related that exhaust velocity to oncoming airspeed `Vo` to model the drop in thrust as the plane accelerates.</p>
    <p>The project goals were clear from the slideshow:
      model aircraft behavior as wattage and airspeed change; identify thrust and drag formulas; choose a representative mass; find `Ve` from watts and speed; and capture how thrust decreases as velocity rises.
    </p>
  </div>
  <div style="flex:0 0 360px; max-width:360px;">
    <video controls style="width:100%; height:auto; display:block; border-radius:0.75rem; box-shadow:0 20px 45px rgba(0,0,0,0.12);">
      <source src="/assets/video/RCFlightTest%20Footage.mp4" type="video/mp4" />
      Your browser does not support the video tag.
    </video>
  </div>
</div>

<div style="margin-top:1rem; width:100%;">
  <pre style="background: var(--global-surface-color); color: var(--global-text-color); padding:1rem; border-radius:0.75rem; overflow-x:auto; border:1px solid var(--global-divider-color);">Thrust = 0.5 * P * A_prop * (Ve^2 - Vo^2)
Ve = BaseVe + Vo^(2/3)
BaseVe = 5.83805 * ln(0.14987 * Watts)
Drag = 0.5 * C * P * A_plane * Vo^2
Acceleration = (Thrust - Drag) / mass
Velocity += Acceleration * dt
Position += Velocity * dt
</pre>
</div>

<div style="display:flex; flex-wrap:wrap; gap:1.5rem; align-items:flex-start; margin-top:1.5rem;">
  <div style="flex:1 1 360px; min-width:280px;">
    <p>This project used real experimental data. The plane was mounted to a car, and airspeed was measured with an anemometer while the propeller’s exhaust velocity and power draw were recorded. GPS telemetry provided the plane’s velocity, acceleration, and position for direct validation.</p>
  </div>
  <div style="flex:1 1 360px; min-width:280px;">
    <img src="/assets/img/RcPlaneMount.png" alt="RC plane mounted for testing" style="width:100%; height:auto; display:block; border-radius:0.75rem; box-shadow:0 20px 45px rgba(0,0,0,0.12);" />
  </div>
</div>

<div style="margin-top:2rem; width:100%;">
  <pre style="background: var(--global-surface-color); color: var(--global-text-color); padding:1rem; border-radius:0.75rem; overflow-x:auto; border:1px solid var(--global-divider-color);">Parameters:
P = 1.255 kg/m³
A_plane = 0.10 m²
A_prop = 0.025 m²
C = 0.10 (tested 0.07–0.20)
mass = 1.0 kg
dt = 0.01 s
</pre>
</div>

<div style="margin-top:2rem;">
  <img src="/assets/img/RcPlanePvT%20at%20200W%20Simulated%20and%20Actual%20Data.png" alt="RC plane simulated vs actual 200W graph" style="width:100%; height:auto; display:block; border-radius:0.75rem;" />
</div>

<div style="margin-top:1rem; width:100%;">
  <pre style="background: var(--global-surface-color); color: var(--global-text-color); padding:1rem; border-radius:0.75rem; overflow-x:auto; border:1px solid var(--global-divider-color);">Accuracy examples:
800 W: predicted 118.8 km/h | 33.1 m/s, actual 120 km/h | 33.3 m/s
305 W: predicted 97.2 km/h | 27.2 m/s, actual 95 km/h | 25.6 m/s
200 W: predicted 86.4 km/h | 24.3 m/s, actual 83.0 km/h | 23.1 m/s
</pre>
</div>
