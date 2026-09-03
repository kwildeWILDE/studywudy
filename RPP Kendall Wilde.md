
### Week 1 - Microscale Atmospheric Processes for Wind Science (meters–seconds)

#### Concepts to cover

-~~ Structure of the atmospheric boundary layer: surface layer, mixed layer, residual layer, stable nocturnal layer~~

-~~ Turbulence basics: turbulent kinetic energy (TKE), eddies, Reynolds decomposition, turbulence intensity~~

-~~ Atmospheric stability: Monin–Obukhov similarity theory, Richardson number, Obukhov length~~

-~~ Wind shear and veer (vertical change in speed/direction) and their causes (surface friction, thermal stratification, low-level jets)~~

-~~ Terrain and surface-roughness effects on near-surface flow; complex-terrain flow distortion~~

- ~~Diurnal cycle of the ABL and its impact on turbulence/shear at hub height (~80–160 m)~~

#### Core readings

- ~~Stull, R.B., *~~~~An Introduction to Boundary Layer Meteorology~~*~~ — Ch. 1–5, 9~~

- Kaimal & Finnigan, *Atmospheric Boundary Layer Flows* — Ch. 1–3 
  
#### Hands-on exercise
-~~ Create GitHub repo and get familiar with cloning, pulling, committing pushing~~

- ~~Pull a public meteorological tower dataset (e.g., NREL [M2](https://midcdmz.nlr.gov/apps/day.pl?NWTC) tower at NWTC) with multi-level wind speed/direction/temperature.~~

- ~~In Python: compute wind shear exponent (power law), bulk Richardson number, and turbulence intensity by height and time of day.~~

- ~~Plot diurnal cycles of shear and turbulence intensity — identify the transition between convective (daytime) and stable (nighttime) regimes.~~

### Week 2 — Remote sensing

#### Concepts to cover

- **Doppler lidar wind retrieval fundamentals:**

  -~~ Radial (line-of-sight) velocity measurement principle~~

  - ~~Scan strategies: VAD (velocity-azimuth display), DBS (Doppler beam swinging), staring/RHI~~

  -~~ Dual-Doppler retrieval geometry for full 3D wind vectors~~ ( Might need to double check if I understand this)

  - ~~Sources of retrieval uncertainty: signal-to-noise ratio, beam spreading, assumption of flow homogeneity~~
  
 - ~~LiSBOA for scan optimization and LiDARGO data processing~~


- **Thermodynamic profiling basics:**

  -~~ Why temperature/humidity profiles matter for stability and turbine-load context, not just wind~~

  - Optimal estimation theory (Rodgers' framework) — the statistical backbone of TROPoe
  
 - TROPoe main workflow

#### Core readings

- ~~Turner, D.D. & Löhnert, U. (2014), *"Information Content and Uncertainties in Thermodynamic Profiles from Optimal Estimation Retrievals,"* J. Appl. Meteor. Climatol. — explains the optimal-estimation math in an applied way~~
-~~ Letizia, S. & Michaud-Belleau, V. & Turner, D.D. & Abraham, A. "*Thermodynamic profiling through ASSIST observations and TROPoe retrievals*" NREL Tech Report, 2025~~
- ~~Stefano Letizia, Rachel Robey, Nicola Bodini, Miguel Sanchez Gomez, Julie K. Lundquist, Raghavendra Krishnamurthy, Patrick J. Moriarty; *Tilted lidar profiling: Development and testing of a novel scanning strategy for inhomogeneous flows*. **J. Renewable Sustainable Energy** 1 July 2024; 16 (4): 043310. [https://doi.org/10.1063/5.0209729](https://doi.org/10.1063/5.0209729)~~
- ~~Letizia, S., Zhan, L., & Iungo, G. V. (2021). LiSBOA (LiDAR Statistical Barnes Objective Analysis) for optimal design of lidar scans and retrieval of wind statistics – Part 1: Theoretical framework. _Atmos. Meas. Tech., 14_, 2065–2093. doi:10.5194/amt-14-2065-2021~~
- ~~Letizia et al., "*Collection, processing, quality control, and statistical analysis of the nacelle-mounted lidar data at AWAKEN*" NLR Tech Report, 2026.~~

#### Hands-on exercise

- In Python (xarray), load a TROPoe output file: plot retrieved temperature/humidity profile time-height cross-sections, and plot the associated uncertainty profiles.

- Reproduce independently the dual-Doppler retrieval in CORSAIR (from [corsair/s19.lidar.z01.b0](https://wdh.energy.gov/ds/corsair/s19.lidar.z01.b0), [corsair/s40.lidar.z01.b0](https://wdh.energy.gov/ds/corsair/s40.lidar.z01.b0) to [corsair/fc.ddoppler.z01.c1](https://wdh.energy.gov/ds/corsair/fc.ddoppler.z01.c1))

### Week 3 — Weather-Driven Power Outages
#### Concepts to cover

- ~~Major weather drivers of outages: high wind/downed lines, ice/freezing rain accretion on lines and towers, lightning, extreme heat (thermal derating, demand spikes), wildfire (PSPS events), flooding~~

-~~ Basics of grid vulnerability: transmission vs. distribution exposure, vegetation/tree-related failures, cascading failures~~

- ~~Outage prediction modeling approaches: statistical/regression models, machine-learning outage prediction (weather features → outage counts), reliability metrics (SAIDI, SAIFI, CAIDI)~~

#### Core readings

- ~~ J. Lee, Z. Zhang, and S. G. Paal, "A data-driven approach to predicting power outages during winter storms in the southern U.S. leveraging nonparametric machine learning models," _Computational Urban Science_, vol. 5, no. 1, art. 62, 2025, doi: 10.1007/s43762-025-00222-9.~~

- ~~S. Lee, J. Y. Choi, G. S. Jung, A. Tabassum, N. Stenvig, and S. Chinthavali, "Predicting power outage during extreme weather events with EAGLE-I and NWS datasets," in _Proc. 2023 IEEE 24th Int. Conf. Information Reuse and Integration for Data Science (IRI)_, Bellevue, WA, USA, Aug. 2023, pp. 211–212, doi: 10.1109/IRI58017.2023.00042.~~

 - ~~D. Cerrai, M. Koukoula, P. Watson, and E. N. Anagnostou, "Outage prediction models for snow and ice storms," _Sustainable Energy, Grids and Networks_, vol. 21, art. 100294, 2020, doi: 10.1016/j.segan.2019.100294.~~

#### Hands-on exercise

- Pull a public outage dataset (EAGLE-I county-level outage data or DOE OE-417 reports) and a matching NOAA Storm Events dataset for the same region/time window.

- In Python: join outage counts with storm event type/severity by county and date; produce simple summary statistics or a plot showing outage counts vs. wind gust speed or ice accumulation.

- Optional stretch: fit a simple regression relating a weather variable (peak gust, precipitation type) to outage magnitude.


###  Week 4 — Wind Turbine Extreme Loads

#### Concepts to cover

- IEC 61400-1 design standard basics: design load cases (DLCs), normal vs. extreme wind conditions

- Extreme Wind Speed Model (EWM) and Extreme Operating Gust (EOG); return-period wind speeds (50-year gust, etc.)

- Turbulence intensity classes and their role in fatigue vs. extreme (ultimate) loads

- Wind shear and veer profile effects on rotor loading (asymmetric loading across the rotor disk)

- Low-level jets and their outsized contribution to extreme shear/turbulence events relevant to hub-height turbines

- Coherence and turbulence spectra (Kaimal spectrum) as inputs to load simulation tools

- Brief intro to load-simulation tools: OpenFAST (NREL's aeroelastic simulation code) — just enough to know what it consumes (wind field input, e.g., from TurbSim) and produces (load time series)

#### Core readings

- IEC 61400-1 standard summary (an NREL or DNV technical summary is more digestible than the full standard)

- NREL TurbSim and OpenFAST user guides — just the introductory/overview sections

- A review paper connecting atmospheric extremes (shear, turbulence, LLJs) to turbine loading, if available from NWTC publications

#### Hands-on exercise

- Using the tower/lidar dataset from Week 1, identify one or two extreme events (high shear, high turbulence, or a low-level jet period).

- Characterize the event: plot the vertical profile of wind speed and direction during the event vs. a "normal" period, and estimate the shear exponent and turbulence intensity during the event.

- Optional stretch: compare the event's turbulence intensity to the IEC turbulence class thresholds to see whether it would exceed standard design assumptions.

### Month 2
- Explore CORSAIR dataset looking for interesting events (weather fronts, gravity waves, MCS, extreme winds)
- Error analysis of lidar and TROPoe to M2 
- Propose improved scanning strategy (include dynamics, lower shear error)
- Survey ARIES/FC infrastructures that can be used as case studies

### Month 3
- Extend ALEX framework to FC dataset
- Get familiar with M5 new dataset and dashboard (work with Nicholas)
- Build library of hazard at FC based on M5, M2 and lidar

### Month 4-6
- Write manuscript about CORSAIR and ARIES hazards


