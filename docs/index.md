# Carbon and Code: Environmental and Social Impacts of Data Centers
*Evaluating hyperscale data center siting in South Dakota through spatial analysis of water vulnerability, community buffers, and distributed alternatives.*

![Rows of illuminated server racks inside a data center](assets/hero/hero11.jpg)

[See the completed OLC example](olc-example.md){ .md-button .md-button--primary }
[See the completed fire example](example.md){ .md-button }
[Open the Hackathon directions](instructions.md){ .md-button }

### People and Roles

| Name | Affiliation | Contact | Starting role |
|---|---|---|---|
| Cully Pourier | Hackathon Participant | Team Carbon & Code | Project framing, visual documentation, repository curation |
| Leon Red Kettle | Hackathon Participant | Team Carbon & Code | Spatial analysis, zoning criteria, architectural modeling |
| Emmanuel Akwasi Opoku | Hackathon Participant | Team Carbon & Code | Technical pipeline, data synthesis, narrative integration |
| Brittany Mark | Hackathon Participant | Team Carbon & Code | Data engineering, pipeline streaming, source verification |

## Team Norms and Decision Making { #team-norms-and-decision-making }

Our team norms:

- Prioritize community impact and environmental protection over pure technical complexity.
- Maintain transparent documentation of all assumptions and data limits.
- Ensure every team member contributes to both technical artifacts and storytelling.

Our decision rule:

- Consensus first; if time-constrained, the member leading the specific technical module decides how to proceed while documenting trade-offs.

## Our Question 📣 { #project-question .oasis-report-out-section }

Our working question:

> How can emerging data center markets like South Dakota use spatial Earth observation and infrastructure data to proactively zone hyperscale data centers away from vulnerable watersheds and educational facilities, favoring distributed edge architectures over resource-intensive centralized facilities?

What would count as progress by noon on September 16:

- Extraction and spatial filtering of the IM3 Data Center Atlas for South Dakota.
- A functional multi-layer GIS workflow defining a "Traffic Light" zoning schema (Red, Yellow, Green zones).
- An interactive map or prototype visualizing buffer zones around municipal water service areas and public infrastructure.

## Why This Matters 📣 { #why-this-matters .oasis-report-out-section }

This matters because:

- Mature markets like Hillsboro, Oregon demonstrate that uncoordinated data center expansion leads to acute resource strain and severe community pushback after infrastructure is already locked in.
- South Dakota is an emerging frontier: currently hosting just 3 MW of operational capacity, but facing a planned influx of over 500 MW (including the proposed 500 MW Gemini facility).
- In semi-arid regions, evaporative cooling systems consume between 100,000 and 1,000,000+ gallons of potable water daily per facility.
- Proximity to hyperscale facilities imposes chronic noise pollution (85–96 dB) and backup generator emissions (PM2.5/NOx), which peer-reviewed educational reporting links to adverse impacts on learning and school performance.

People who might use, question, or improve this work:

- Tribal land-use planners and regional municipal zoning boards establishing data sovereignty frameworks.
- Environmental justice advocates evaluating watershed depletion and grid reliability.
- Infrastructure planners modeling distributed edge alternatives against centralized hyperscale footprints.

## What We Tried to Build 📣 { #what-we-tried-to-build .oasis-report-out-section }
[US Datacenters vs. Aqueduct Baseline Water Stress]docs/assets/hero/Datacenter-3.png
By the end of the Hackathon, we tried to make:

- A reproducible spatial zoning pipeline that takes proposed data center coordinates and evaluates compliance against environmental and human-health exclusion boundaries.
- An interactive map artifact showing current vs. projected facilities against municipal water basins, electric transmission lines, and high-speed fiber corridors.

Our chosen pathway and why it fit:

- **Data Investigator & Technical Extender:** We are combining open-source infrastructure projections with federal environmental layers to evaluate whether planned centralized sites encroach on vulnerable community resources.

## Data and Evidence { #data-and-evidence }

| Dataset | Source | Place | Period | What it measures |
|---|---|---|---|---|
| IM3 Open Source Data Center Atlas | MultiSector Dynamics / PNNL | Continental US / South Dakota | Feb 2026 Release (Projections to 2035) | Operational (MW) and projected hyperscale facilities, site footprint, siting costs |
| Municipal Water Service Areas | IM3 / USGS / State GIS | Continental US / Regional SD | 2024–2026 | Delineated service polygons for public water supply and municipal utility coverage |
| Electric Transmission Lines | EIA / HIFLD / DHS | South Dakota regional grid | 2024–2026 | Voltage capacity, line pathways, and grid interconnect corridors |
| High-Speed Fiber Provider Density | FCC / IM3 Atlas | Regional US / South Dakota | 2025–2026 | Broadband routing density and fiber optic trunk lines |
| Public Schools & Community Infrastructure | HIFLD / NCES | South Dakota | 2024–2026 | Geographic coordinates of K-12 educational facilities for noise buffer mapping |

## Methods and Tools { #methods-and-tools }

Methods, tools, or approaches we tried:

| Approach | What we did | What happened |
|---|---|---|
| Spatial Data Extraction | Downloaded existing and projected geospatial layers from the IM3 Open Source Atlas | Isolated regional points for South Dakota, identifying the 500 MW Gemini site in Minnehaha County |
| Buffer Zone Calculation | Defined a 2-mile precautionary buffer around schools and critical water service areas | Flagged potential overlap areas between projected hyperscale sites and sensitive community infrastructure |
| Centralized vs. Distributed Comparison | Modeled resource intensity differences between 500 MW centralized sites and 2 MW distributed edge sites | Clarified the trade-off: distributed edge sites dramatically reduce localized water cooling stress |

### Working visual or output

![Working figure, map, screenshot, or prototype](assets/figures/figure1.png)

*Figure 1: IM3 Open Source Data Center Atlas showing national infrastructure corridors, existing data centers, and 2035 projected hyperscale hubs layered against municipal water basins.*

### Failed attempts and useful obstacles

- National datasets required extensive spatial cropping to avoid computational lag when running polygon intersections locally.
- Determining precise daily water consumption for specific proprietary cooling towers is rarely disclosed publicly; we used standardized conservative ranges (100k to 1M gal/day) based on published literature.

## What We Made { #what-we-made }

- **Main artifact:** A prototype "Smart Zoning Engine" mapping pipeline separating regional land into Red (Exclusion), Yellow (Buffer), and Green (Viable Distributed Corridor) zones.
- **Code or notebook:** Jupyter Notebooks executing GeoPandas spatial joins between projected facility points, school locations, and water boundaries.
- **Reusable data or output:** A clean GeoJSON subset of South Dakota data infrastructure, ready for integration into open-source web mapping libraries.

## What We Learned 📣 { #what-we-learned .oasis-report-out-section }

**Observation — what happened:** 
Statewide data shows South Dakota currently operates only 3 MW across two Tierpoint facilities in Sioux Falls. However, pipeline data indicates a single planned project—the Gemini Data Center in Minnehaha County—represents 500 MW of demand, fundamentally shifting the state’s infrastructure footprint overnight.

**Evidence — what supports it:** 
CleanView project registries and the IM3 Data Center Atlas corroborate this 500 MW projection alongside rural edge developments like the 2 MW Sequitor Edge project in Rapid City.

**Interpretation — what we think it means:** 
South Dakota is at a critical policy crossroads. Adopting a centralized hyperscale model concentrates extreme water and power demands into localized municipal systems. Shifting focus toward distributed, smaller-scale edge nodes allows data infrastructure to expand along existing transmission corridors without exceeding watershed capacities.

### Claim ladder

| Level | Team statement |
|---|---|
| **What We Observed** | Planned data center capacity in South Dakota is projected to expand by over 16,000% (from 3 MW to 505 MW), driven by a single hyperscale development. |
| **What We Think** | Siting centralized facilities without proactive buffer zoning threatens semi-arid water supplies and risks educational and noise disruptions for adjacent communities. |
| **What We Don’t Know** | The exact proprietary cooling design (evaporative vs. closed-loop air cooled) planned for upcoming regional sites. |
| **What We Should Not Claim** | That all data center development is inherently destructive, or that economic benefits cannot coexist with strict environmental zoning. |

## What Didn’t Work { #what-didnt-work }

- Attempting to dynamically query real-time water drawdown rates from local aquifers proved impossible within hackathon time constraints due to fragmented state and municipal reporting. We pivoted to using verified municipal service boundaries as proxy vulnerability zones.

## What Remains Uncertain 📣 { #what-remains-uncertain .oasis-report-out-section }

![Rows of illuminated server racks inside a data center](docs/assets/hero/Datacenters2.png)
![Likely Voltage Charge](docs/assets/hero/Datacenters6.png)

What these data or artifacts cannot tell us:

- The exact power purchase agreements (PPAs) or backup fuel types (diesel vs. battery storage) contracted by incoming operators.
- The degree of closed-loop water recycling technology that developers might voluntarily adopt prior to groundbreaking.

What would strengthen or challenge our interpretation:

- On-the-ground acoustic baseline readings near existing urban facilities.
- Transparent municipal utility contracts outlining water volume allocations for prospective tech developments.

## What’s Next 📣 { #whats-next .oasis-report-out-section }

Next technical step:

- Expand the Python pipeline to automatically calculate dynamic watershed drawdown models based on customizable facility wattage sliders (2 MW to 500 MW).

Next stewardship or collaboration step:

- Share the spatial zoning criteria with regional planning groups, municipal boards, and Tribal land stewards to ensure community self-determination drives infrastructure siting decisions.

## Who Should Be Involved Next { #who-should-be-involved-next }

Potential roles or perspectives—not claims of consultation or approval:

- Tribal historic preservation and water resource departments.
- Local public school administrators and community health researchers.
- Rural electric cooperatives and municipal water utility engineers.

What those people should help frame, interpret, question, or review:

- Thresholds for acceptable acoustic buffers near classrooms and cultural spaces.
- Real-world water table tolerances during seasonal drought conditions.

## Code, Data, Citation and Reuse { #code-data-citation-and-reuse }

- **Source curriculum:** [OLC Climate Resiliency and Digital Sovereignty Learning Lab](https://github.com/olc-techsupport/Education-Climate-Resiliency-Digital-Sovereignty) [@olcClimateResiliency]
- **Primary Data:** MultiSector Dynamics IM3 Open Source Data Center Atlas (PNNL / DOE)
- **State Data:** CleanView South Dakota Data Center Pipeline & USGS National Hydrography Dataset
