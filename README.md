   # VCARB tyre degradation (2026 Singapore GP)

   Estimates tyre degradation for Lawson and Lindblad using FastF1. Cleans out pit, safety car and traffic laps, corrects for fuel burn with an assumed value, and fits lap time vs tyre age per stint. Includes a check of how much the fuel assumption changes the results.

   Run: `pip install pandas numpy matplotlib scipy fastf1`, then open `analysis.ipynb`.