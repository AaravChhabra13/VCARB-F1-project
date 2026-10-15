# VCARB tyre degradation, 2026 season

Estimates tyre degradation for Liam Lawson and Arvid Lindblad (VCARB) using public timing data from FastF1.

## Method
1. Remove pit laps, safety car and VSC laps, lap 1, and laps much slower than the fastest (traffic, mistakes).
2. Add back an assumed fuel effect of 0.03 s per lap, so the car getting lighter doesn't hide tyre wear.
3. Fit a straight line of lap time vs tyre age for each stint. The slope is the degradation in seconds per lap.
4. Re-run with fuel values of 0.02 and 0.04 to check how much the answer depends on that assumption.

## Races
| Notebook | Race | Main finding |
|---|---|---|
| `singapore_r17.ipynb` | Round 17, Singapore | Soft wore 2 to 4 times faster than medium for both drivers. Clean result. |
| `bahrain_r16.ipynb` | Round 16, Bahrain | Short stints and noisy laps. Little measurable wear on the hard, except a late jump for Lindblad that could be a cliff or traffic. |

## What I learned
The fuel assumption shifts every slope by the same amount, so the ranking of stints is more reliable than the exact values. Bahrain showed the limits of the method: with fewer than about 15 clean laps per stint, the uncertainty is too wide to say much.

## Limitations
Fuel effect is assumed, not measured. Track evolution isn't removed. Straight lines can't capture a tyre cliff. Public data only.

## Run it
pip install pandas numpy matplotlib scipy fastf1
Then open either notebook and Run All.