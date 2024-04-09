![Electricity-Generation-Featured-Image.jpg](attachment:Electricity-Generation-Featured-Image.jpg)
# Capstone-Project
An exploration of worldwide electricity consumption 

## Overview
In this final project, students are tasked with finding their own dataset, performing multilinear regression analysis to find insights and conclusions. This project looks at data on **world electricity generation**, with the aim of providing an insight into some of the factors that affect electricity generation per capita.  

## The Dataset
The World Energy Consumption dataset was
published on kaggle by Pralabh Poudel, and is a
collection of key metrics maintained by *Our
World in Data*.

This dataset has energy data for every country,
with 129 variables and over 22,000 rows.

Before diving into the data, we decided to focus
on data f rom 2001 onwards. Unfortunately there
was too much missing data between 2019 - 2022,
so our data focuses on 2001 - 2018.

Countries with populations smaller than 2
million were excluded to emphasize trends
within larger population groups.

Our final cleaned dataset had around 2500 rows. And
focused on:
- **net electric imports**
- **GDP per capita**
- **coal production**
- **oil production**
- **greenhouse gas emissions per capita**
- **year**
- percentage share of total energy by type:
**biofuel, coal gas, hydro, oil, nuclear, solar, wind**

  Information about all variables in the dataset can be found below:
  
|variable                                     |class     |description                                  |
|:--------------------------------------------|:---------|:--------------------------------------------|
|country                                      |character |Geographic location                                     |
|year                                         |double    |Year of observation                                        |
|iso_code                                     |character |ISO 3166-1 alpha-3 three-letter country codes                                     |
|population                                   |double    |Population                                   |
|gdp                                          |double    |Total real gross domestic product, inflation-adjusted                                          |
|biofuel_cons_change_pct                      |double    |Annual percentage change in biofuel consumption                      |
|biofuel_cons_change_twh                      |double    |Annual change in biofuel consumption, measured in terawatt-hours                      |
|biofuel_cons_per_capita                      |double    |Per capita primary energy consumption from biofuels, measured in kilowatt-hours                      |
|biofuel_consumption                          |double    |Primary energy consumption from biofuels, measured in terawatt-hours                         |
|biofuel_elec_per_capita                      |double    |Per capita electricity generation from biofuels, measured in kilowatt-hours                      |
|biofuel_electricity                          |double    |Electricity generation from biofuels, measured in terawatt-hours                          |
|biofuel_share_elec                           |double    |Share of electricity generation that comes from biofuels                           |
|biofuel_share_energy                         |double    |Share of primary energy consumption that comes from biofuels                         |
|carbon_intensity_elec                        |double    |Carbon intensity of electricity production, measured in grams of carbon dioxide emitted per kilowatt-hour                    |
|coal_cons_change_pct                         |double    |Annual percentage change in coal consumption                        |
|coal_cons_change_twh                         |double    |Annual change in coal consumption, measured in terawatt-hours                      |
|coal_cons_per_capita                         |double    |Per capita primary energy consumption from coal, measured in kilowatt-hours                      |
|coal_consumption                             |double    |Primary energy consumption from coal, measured in terawatt-hours                          |
|coal_elec_per_capita                         |double    |Per capita electricity generation from coal, measured in kilowatt-hours                      |
|coal_electricity                             |double    |Electricity generation from coal, measured in terawatt-hours                            |
|coal_prod_change_pct                         |double    |Annual percentage change in coal production                        |
|coal_prod_change_twh                         |double    |Annual change in coal production, measured in terawatt-hours                     |
|coal_prod_per_capita                         |double    |Per capita coal production, measured in kilowatt-hours                       |
|coal_production                              |double    |Coal production, measured in terawatt-hours                            |
|coal_share_elec                              |double    |Share of electricity generation that comes from coal                       |
|coal_share_energy                            |double    |hare of primary energy consumption that comes from coal                        |
|electricity_demand                           |double    |Electricity demand, measured in terawatt-hours                      |
|electricity_generation                       |double    |Electricity generation, measured in terawatt-hours                     |
|electricity_share_energy                     |double    |Electricity generation as a share of primary energy                  |
|energy_cons_change_pct                       |double    |Annual percentage change in primary energy consumption                |
|energy_cons_change_twh                       |double    |Annual change in primary energy consumption, measured in terawatt-hours                 |
|energy_per_capita                            |double    |Primary energy consumption per capita, measured in kilowatt-hours                      |
|energy_per_gdp                               |double    |Energy consumption per unit of GDP. This is measured in kilowatt-hours per 2011 international-$                            |
|fossil_cons_change_pct                       |double    |Annual percentage change in fossil fuel consumption                     |
|fossil_cons_change_twh                       |double    |Annual change in fossil fuel consumption, measured in terawatt-hours                     |
|fossil_elec_per_capita                       |double    |Per capita electricity generation from fossil fuels, measured in kilowatt-hours. This is the sum of electricity generated from coal, oil and gas.                       |
|fossil_electricity                           |double    |Electricity generation from fossil fuels, measured in terawatt-hours. This is the sum of electricity generation from coal, oil and gas.                        |
|fossil_energy_per_capita                     |double    |Per capita fossil fuel consumption, measured in kilowatt-hours. This is the sum of primary energy from coal, oil and gas.              |
|fossil_fuel_consumption                      |double    |Fossil fuel consumption, measured in terawatt-hours. This is the sum of primary energy from coal, oil and gas.              |
|fossil_share_elec                            |double    |Share of electricity generation that comes from fossil fuels (coal, oil and gas combined)                       |
|fossil_share_energy                          |double    |Share of primary energy consumption that comes from fossil fuels                   |
|gas_cons_change_pct                          |double    |Annual percentage change in gas consumption                     |
|gas_cons_change_twh                          |double    |Annual change in gas consumption, measured in terawatt-hours                        |
|gas_consumption                              |double    |Primary energy consumption from gas, measured in terawatt-hours                       |
|gas_elec_per_capita                          |double    |Per capita electricity generation from gas, measured in kilowatt-hours                   |
|gas_electricity                              |double    |Electricity generation from gas, measured in terawatt-hours                     |
|gas_energy_per_capita                        |double    |Per capita primary energy consumption from gas, measured in kilowatt-hours                  |
|gas_prod_change_pct                          |double    |Annual percentage change in gas production                      |
|gas_prod_change_twh                          |double    |Annual change in gas production, measured in terawatt-hours                    |
|gas_prod_per_capita                          |double    |Per capita gas production, measured in kilowatt-hours                    |
|gas_production                               |double    |Gas production, measured in terawatt-hours                       |
|gas_share_elec                               |double    |Share of electricity generation that comes from gas                       |
|gas_share_energy                             |double    |Share of primary energy consumption that comes from gas              |
|greenhouse_gas_emissions                     |double    |Greenhouse-gas emissions produced in the generation of electricity, measured in million tonnes of CO2 equivalent              |
|hydro_cons_change_pct                        |double    |Annual percentage change in hydropower consumption                  |
|hydro_cons_change_twh                        |double    |Annual change in hydropower consumption, measured in terawatt-hours                 |
|hydro_consumption                            |double    |Primary energy consumption from hydropower, measured in terawatt-hours                     |
|hydro_elec_per_capita                        |double    |Per capita electricity generation from hydropower, measured in kilowatt-hours              |
|hydro_electricity                            |double    |Electricity generation from hydropower, measured in terawatt-hours                   |
|hydro_energy_per_capita                      |double    |Per capita primary energy consumption from hydropower, measured in kilowatt-hours              |
|hydro_share_elec                             |double    |Share of electricity generation that comes from hydropower                         |
|hydro_share_energy                           |double    |Share of primary energy consumption that comes from hydropower                 |
|low_carbon_cons_change_pct                   |double    |Annual percentage change in low-carbon energy consumption               |
|low_carbon_cons_change_twh                   |double    |Annual change in low-carbon energy consumption, measured in terawatt-hours             |
|low_carbon_consumption                       |double    |Primary energy consumption from low-carbon sources, measured in terawatt-hours            |
|low_carbon_elec_per_capita                   |double    |Per capita electricity generation from low-carbon sources, measured in kilowatt-hours       |
|low_carbon_electricity                       |double    |Electricity generation from low-carbon sources, measured in terawatt-hours. This is the sum of electricity generation from renewables and nuclear power                 |
|low_carbon_energy_per_capita                 |double    |Per capita primary energy consumption from low-carbon sources, measured in kilowatt-hours             |
|low_carbon_share_elec                        |double    |Share of electricity generation that comes from low-carbon sources. This is the sum of electricity from renewables and nuclear                 |
|low_carbon_share_energy                      |double    |Share of primary energy consumption that comes from low-carbon sources. This is the sum of primary energy from renewables and nuclear                   |
|net_elec_imports                             |double    |Net electricity imports, measured in terawatt-hours                         |
|net_elec_imports_share_demand                |double    |Net electricity imports as a share of electricity demand           |
|nuclear_cons_change_pct                      |double    |Annual percentage change in nuclear consumption                |
|nuclear_cons_change_twh                      |double    |Annual change in nuclear consumption, measured in terawatt-hours                |
|nuclear_consumption                          |double    |Primary energy consumption from nuclear power, measured in terawatt-hours                 |
|nuclear_elec_per_capita                      |double    |Per capita electricity generation from nuclear power, measured in kilowatt-hours            |
|nuclear_electricity                          |double    |Electricity generation from nuclear power, measured in terawatt-hours                  |
|nuclear_energy_per_capita                    |double    |Per capita primary energy consumption from nuclear, measured in kilowatt-hours          |
|nuclear_share_elec                           |double    |Share of electricity generation that comes from nuclear power             |
|nuclear_share_energy                         |double    |Share of primary energy consumption that comes from nuclear power              |
|oil_cons_change_pct                          |double    |Annual percentage change in oil consumption                      |
|oil_cons_change_twh                          |double    |Annual change in oil consumption, measured in terawatt-hours                  |
|oil_consumption                              |double    |Primary energy consumption from oil, measured in terawatt-hours                         |
|oil_elec_per_capita                          |double    |Per capita electricity generation from oil, measured in kilowatt-hours               |
|oil_electricity                              |double    |Electricity generation from oil, measured in terawatt-hours           |
|oil_energy_per_capita                        |double    |Per capita primary energy consumption from oil, measured in kilowatt-hours                  |
|oil_prod_change_pct                          |double    |Annual percentage change in oil production                     |
|oil_prod_change_twh                          |double    |Annual change in oil production, measured in terawatt-hours                |
|oil_prod_per_capita                          |double    |Per capita oil production, measured in kilowatt-hours                     |
|oil_production                               |double    |Oil production, measured in terawatt-hours                   |
|oil_share_elec                               |double    |Share of electricity generation that comes from oil                         |
|oil_share_energy                             |double    |Share of primary energy consumption that comes from oil                    |
|other_renewable_consumption                  |double    |Primary energy consumption from other renewables, measured in terawatt-hours            |
|other_renewable_electricity                  |double    |Electricity generation from other renewable sources including biofuels, measured in terawatt-hours           |
|other_renewable_exc_biofuel_electricity      |double    |Electricity generation from other renewable sources excluding biofuels, measured in terawatt-hours   |
|other_renewables_cons_change_pct             |double    |Annual percentage change in energy consumption from other renewables       |
|other_renewables_cons_change_twh             |double    |Annual change in other renewable consumption, measured in terawatt-hours       |
|other_renewables_elec_per_capita             |double    |Per capita electricity generation from other renewables including biofuels, measured in kilowatt-hours     |
|other_renewables_elec_per_capita_exc_biofuel |double    |Per capita electricity generation from other renewables excluding biofuels, measured in kilowatt-hours |
|other_renewables_energy_per_capita           |double    |Per capita primary energy consumption from other renewables, measured in kilowatt-hours      |
|other_renewables_share_elec                  |double    |Share of electricity generation that comes from other renewables including biofuels       |
|other_renewables_share_elec_exc_biofuel      |double    |Share of electricity generation that comes from other renewables excluding biofuels    |
|other_renewables_share_energy                |double    |Share of primary energy consumption that comes from other renewables                |
|per_capita_electricity                       |double    |Electricity generation per capita, measured in kilowatt-hours                  |
|primary_energy_consumption                   |double    |Primary energy consumption, measured in terawatt-hours         |
|renewables_cons_change_pct                   |double    |Annual percentage change in renewable energy consumption             |
|renewables_cons_change_twh                   |double    |Annual change in renewable energy consumption, measured in terawatt-hours            |
|renewables_consumption                       |double    |Primary energy consumption from renewables, measured in terawatt-hours               |
|renewables_elec_per_capita                   |double    |Per capita electricity generation from renewables, measured in kilowatt-hours         |
|renewables_electricity                       |double    |Electricity generation from renewables, measured in terawatt-hours           |
|renewables_energy_per_capita                 |double    |Per capita primary energy consumption from renewables, measured in kilowatt-hours        |
|renewables_share_elec                        |double    |Share of electricity generation that comes from renewables                  |
|renewables_share_energy                      |double    |Share of primary energy consumption that comes from renewables                    |
|solar_cons_change_pct                        |double    |Annual percentage change in solar consumption                   |
|solar_cons_change_twh                        |double    |Annual change in solar consumption, measured in terawatt-hours             |
|solar_consumption                            |double    |Primary energy consumption from solar, measured in terawatt-hours               |
|solar_elec_per_capita                        |double    |Per capita electricity generation from solar, measured in kilowatt-hours                |
|solar_electricity                            |double    |Electricity generation from solar, measured in terawatt-hours                   |
|solar_energy_per_capita                      |double    |Per capita primary energy consumption from solar, measured in kilowatt-hours                 |
|solar_share_elec                             |double    |Share of electricity generation that comes from solar                      |
|solar_share_energy                           |double    |Share of primary energy consumption that comes from solar                 |
|wind_cons_change_pct                         |double    |Annual percentage change in wind consumption                  |
|wind_cons_change_twh                         |double    |Annual change in wind consumption                 |
|wind_consumption                             |double    |Primary energy consumption from wind, measured in terawatt-hours                 |
|wind_elec_per_capita                         |double    |Per capita electricity generation from wind, measured in kilowatt-hours              |
|wind_electricity                             |double    |Electricity generation from wind, measured in terawatt-hours                     |
|wind_energy_per_capita                       |double    |Per capita primary energy consumption from wind, measured in kilowatt-hours                      |
|wind_share_elec                              |double    |Share of electricity generation that comes from wind                        |
|wind_share_energy                            |double    |Share of primary energy consumption that comes from wind                    |
