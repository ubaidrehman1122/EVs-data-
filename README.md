Electric Vehicle Fleet Charging Dataset
Overview
This dataset provides a comprehensive simulation of a 250-vehicle electric vehicle (EV) fleet with realistic technical parameters, charging schedules, and time-varying electricity pricing. Designed for research in smart charging optimization, demand response, Vehicle-to-Grid (V2G) applications, and energy management systems, the dataset captures the complexity of managing large-scale EV charging under real-world constraints.
Files Included
1. ev_parameters.csv
Technical specifications for each vehicle in the fleet:
Column	Description	Range/Values
vehicle_id	Unique vehicle identifier	1–250
battery_capacity_kwh	Total battery capacity	40.0–100.0 kWh
max_charge_rate_kw	Maximum AC charging power	3.7, 7.4, or 11 kW (typical residential/commercial AC levels)
max_discharge_rate_kw	Maximum V2G discharge power	2.96–8.8 kW (80% of charge rate)
efficiency	Round-trip charging/discharging efficiency	0.9 (90%)
min_soc	Minimum allowable state of charge	0.2 (20%)
max_soc	Maximum allowable state of charge	1.0 (100%)
Key Characteristics:
•	Mixed fleet with varied battery capacities (predominantly 40–85 kWh)
•	Three charging capability tiers representing common EVSE standards:
o	Slow charging: 3.7 kW (standard household outlet)
o	Fast AC charging: 7.4 kW (dual-phase residential/commercial)
o	Rapid AC charging: 11 kW (three-phase commercial)
2. ev_schedules.csv
Daily charging requirements and availability windows for each vehicle:
Column	Description
vehicle_id	Vehicle identifier (matches ev_parameters.csv)
arrival_hour	Time vehicle becomes available for charging (decimal hours)
departure_hour	Time vehicle must be ready for departure (decimal hours)
arrival_soc	State of charge upon arrival (fraction)
required_soc	Target state of charge at departure (fraction)
energy_demand_kwh	Energy required to reach target SOC (kWh)
Key Characteristics:
•	Realistic overnight parking patterns (typical arrival: 16:00–21:00, departure: 7:00–10:00)
•	Cross-midnight sessions handled correctly (departure hour < arrival hour indicates next-day departure)
•	Arrival SOC distribution reflects typical daily driving patterns (mean ~0.45)
•	Energy demands range from minimal top-ups (<1 kWh) to full recharges (>60 kWh)
•	Includes edge cases: vehicles arriving with minimum SOC (0.2), requiring full charges to 100%
3. energy_prices.csv
Time-of-use electricity pricing for a representative 24-hour period:

ime-of-use electricity pricing for a representative 24-hour period:
Column	Description
hour	Hour of day (0–23)
price_eur_kwh	Electricity price in EUR/kWh
Price Profile Characteristics:
Price Profile Characteristics:
•	Off-peak (00:00–05:00, 23:00): €0.05/kWh (lowest cost)
•	Shoulder periods (06:00–09:00, 15:00–16:00, 20:00–22:00): €0.08–€0.12/kWh
•	Peak periods (07:00–08:00, 17:00–19:00): €0.15/kWh (highest cost)
•	Reflects typical European residential time-of-use tariff structure with pronounced evening peak
Dataset Statistics
•	Fleet size: 250 vehicles
•	Total daily energy demand: ~6,850 kWh
•	Average battery capacity: 60.2 kWh
•	Average energy demand per vehicle: 27.4 kWh
•	Charging infrastructure distribution:
o	3.7 kW chargers: ~45% of fleet
o	7.4 kW chargers: ~30% of fleet
o	11 kW chargers: ~25% of fleet
•	Typical parking duration: 10–14 hours (overnight)
Potential Applications
This dataset is suitable for research and development in:
•	Optimal charging scheduling (minimizing cost while meeting constraints)
•	Grid impact analysis (load flattening, peak shaving)
•	V2G/Bi-directional charging strategies
•	Renewable energy integration (solar/wind-powered charging)
•	Machine learning for load forecasting
•	Multi-objective optimization (cost vs. battery degradation)
•	Real-time pricing response algorithms
•	Fleet management systems for commercial EV operations
Usage Example
Price Profile Characteristics:
Off-peak (00:00–05:00, 23:00): €0.05/kWh (lowest cost)
Shoulder periods (06:00–09:00, 15:00–16:00, 20:00–22:00): €0.08–€0.12/kWh
Peak periods (07:00–08:00, 17:00–19:00): €0.15/kWh (highest cost)
Reflects typical European residential time-of-use tariff structure with pronounced evening peak
Dataset Statistics
Fleet size: 250 vehicles
Total daily energy demand: ~6,850 kWh
Average battery capacity: 60.2 kWh
Average energy demand per vehicle: 27.4 kWh
Charging infrastructure distribution:
3.7 kW chargers: ~45% of fleet
7.4 kW chargers: ~30% of fleet
11 kW chargers: ~25% of fleet
Typical parking duration: 10–14 hours (overnight)
Potential Applications
This dataset is suitable for research and development in:
Optimal charging scheduling (minimizing cost while meeting constraints)
Grid impact analysis (load flattening, peak shaving)
V2G/Bi-directional charging strategies
Renewable energy integration (solar/wind-powered charging)
Machine learning for load forecasting
Multi-objective optimization (cost vs. battery degradation)
Real-time pricing response algorithms
Fleet management systems for commercial EV operations
Usage Example
Citation
If you use this dataset in academic research, please cite appropriately:

Electric Vehicle Fleet Charging Dataset. (2026). 
https://github.com/ubaidrehman1122/EVs-data-
License
CC BY 4.0 for open research use

