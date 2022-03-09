```
{
    "FuelFactors": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "existing_fuel_resource_name": {
                        "type": "string",
                        "enum": [
                            "Coal",
                            "Diesel",
                            "Electricity",
                            "FuelOilNo1",
                            "FuelOilNo2",
                            "Gasoline",
                            "NaturalGas",
                            "OtherFuel1",
                            "OtherFuel2",
                            "Propane"
                        ]
                    },
                    "units_of_measure": {
                        "type": "string"
                    },
                    "energy_per_unit_factor": {
                        "type": "number"
                    },
                    "source_energy_factor": {
                        "type": "number",
                        "units": "J/J"
                    },
                    "source_energy_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "co2_emission_factor": {
                        "type": "number",
                        "units": "g/MJ"
                    },
                    "co2_emission_factor_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "co_emission_factor": {
                        "type": "number",
                        "units": "g/MJ"
                    },
                    "co_emission_factor_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "ch4_emission_factor": {
                        "type": "number",
                        "units": "g/MJ"
                    },
                    "ch4_emission_factor_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "nox_emission_factor": {
                        "type": "number",
                        "units": "g/MJ"
                    },
                    "nox_emission_factor_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "n2o_emission_factor": {
                        "type": "number",
                        "units": "g/MJ"
                    },
                    "n2o_emission_factor_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "so2_emission_factor": {
                        "type": "number",
                        "units": "g/MJ"
                    },
                    "so2_emission_factor_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "pm_emission_factor": {
                        "type": "number",
                        "units": "g/MJ"
                    },
                    "pm_emission_factor_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "pm10_emission_factor": {
                        "type": "number",
                        "units": "g/MJ"
                    },
                    "pm10_emission_factor_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "pm2_5_emission_factor": {
                        "type": "number",
                        "units": "g/MJ"
                    },
                    "pm2_5_emission_factor_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "nh3_emission_factor": {
                        "type": "number",
                        "units": "g/MJ"
                    },
                    "nh3_emission_factor_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "nmvoc_emission_factor": {
                        "type": "number",
                        "units": "g/MJ"
                    },
                    "nmvoc_emission_factor_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "hg_emission_factor": {
                        "type": "number",
                        "units": "g/MJ"
                    },
                    "hg_emission_factor_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "pb_emission_factor": {
                        "type": "number",
                        "units": "g/MJ"
                    },
                    "pb_emission_factor_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "water_emission_factor": {
                        "type": "number",
                        "units": "L/MJ"
                    },
                    "water_emission_factor_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "nuclear_high_level_emission_factor": {
                        "type": "number",
                        "units": "g/MJ"
                    },
                    "nuclear_high_level_emission_factor_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "nuclear_low_level_emission_factor": {
                        "type": "number",
                        "units": "m3/MJ"
                    },
                    "nuclear_low_level_emission_factor_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    }
                }
            }
        },
        "group": "Output Reporting",
        "legacy_idd": {
            "field_info": {
                "existing_fuel_resource_name": {
                    "field_name": "Existing Fuel Resource Name",
                    "field_type": "a"
                },
                "units_of_measure": {
                    "field_name": "Units of Measure",
                    "field_type": "a"
                },
                "energy_per_unit_factor": {
                    "field_name": "Energy per Unit Factor",
                    "field_type": "n"
                },
                "source_energy_factor": {
                    "field_name": "Source Energy Factor",
                    "field_type": "n"
                },
                "source_energy_schedule_name": {
                    "field_name": "Source Energy Schedule Name",
                    "field_type": "a"
                },
                "co2_emission_factor": {
                    "field_name": "CO2 Emission Factor",
                    "field_type": "n"
                },
                "co2_emission_factor_schedule_name": {
                    "field_name": "CO2 Emission Factor Schedule Name",
                    "field_type": "a"
                },
                "co_emission_factor": {
                    "field_name": "CO Emission Factor",
                    "field_type": "n"
                },
                "co_emission_factor_schedule_name": {
                    "field_name": "CO Emission Factor Schedule Name",
                    "field_type": "a"
                },
                "ch4_emission_factor": {
                    "field_name": "CH4 Emission Factor",
                    "field_type": "n"
                },
                "ch4_emission_factor_schedule_name": {
                    "field_name": "CH4 Emission Factor Schedule Name",
                    "field_type": "a"
                },
                "nox_emission_factor": {
                    "field_name": "NOx Emission Factor",
                    "field_type": "n"
                },
                "nox_emission_factor_schedule_name": {
                    "field_name": "NOx Emission Factor Schedule Name",
                    "field_type": "a"
                },
                "n2o_emission_factor": {
                    "field_name": "N2O Emission Factor",
                    "field_type": "n"
                },
                "n2o_emission_factor_schedule_name": {
                    "field_name": "N2O Emission Factor Schedule Name",
                    "field_type": "a"
                },
                "so2_emission_factor": {
                    "field_name": "SO2 Emission Factor",
                    "field_type": "n"
                },
                "so2_emission_factor_schedule_name": {
                    "field_name": "SO2 Emission Factor Schedule Name",
                    "field_type": "a"
                },
                "pm_emission_factor": {
                    "field_name": "PM Emission Factor",
                    "field_type": "n"
                },
                "pm_emission_factor_schedule_name": {
                    "field_name": "PM Emission Factor Schedule Name",
                    "field_type": "a"
                },
                "pm10_emission_factor": {
                    "field_name": "PM10 Emission Factor",
                    "field_type": "n"
                },
                "pm10_emission_factor_schedule_name": {
                    "field_name": "PM10 Emission Factor Schedule Name",
                    "field_type": "a"
                },
                "pm2_5_emission_factor": {
                    "field_name": "PM2.5 Emission Factor",
                    "field_type": "n"
                },
                "pm2_5_emission_factor_schedule_name": {
                    "field_name": "PM2.5 Emission Factor Schedule Name",
                    "field_type": "a"
                },
                "nh3_emission_factor": {
                    "field_name": "NH3 Emission Factor",
                    "field_type": "n"
                },
                "nh3_emission_factor_schedule_name": {
                    "field_name": "NH3 Emission Factor Schedule Name",
                    "field_type": "a"
                },
                "nmvoc_emission_factor": {
                    "field_name": "NMVOC Emission Factor",
                    "field_type": "n"
                },
                "nmvoc_emission_factor_schedule_name": {
                    "field_name": "NMVOC Emission Factor Schedule Name",
                    "field_type": "a"
                },
                "hg_emission_factor": {
                    "field_name": "Hg Emission Factor",
                    "field_type": "n"
                },
                "hg_emission_factor_schedule_name": {
                    "field_name": "Hg Emission Factor Schedule Name",
                    "field_type": "a"
                },
                "pb_emission_factor": {
                    "field_name": "Pb Emission Factor",
                    "field_type": "n"
                },
                "pb_emission_factor_schedule_name": {
                    "field_name": "Pb Emission Factor Schedule Name",
                    "field_type": "a"
                },
                "water_emission_factor": {
                    "field_name": "Water Emission Factor",
                    "field_type": "n"
                },
                "water_emission_factor_schedule_name": {
                    "field_name": "Water Emission Factor Schedule Name",
                    "field_type": "a"
                },
                "nuclear_high_level_emission_factor": {
                    "field_name": "Nuclear High Level Emission Factor",
                    "field_type": "n"
                },
                "nuclear_high_level_emission_factor_schedule_name": {
                    "field_name": "Nuclear High Level Emission Factor Schedule Name",
                    "field_type": "a"
                },
                "nuclear_low_level_emission_factor": {
                    "field_name": "Nuclear Low Level Emission Factor",
                    "field_type": "n"
                },
                "nuclear_low_level_emission_factor_schedule_name": {
                    "field_name": "Nuclear Low Level Emission Factor Schedule Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "existing_fuel_resource_name",
                "units_of_measure",
                "energy_per_unit_factor",
                "source_energy_factor",
                "source_energy_schedule_name",
                "co2_emission_factor",
                "co2_emission_factor_schedule_name",
                "co_emission_factor",
                "co_emission_factor_schedule_name",
                "ch4_emission_factor",
                "ch4_emission_factor_schedule_name",
                "nox_emission_factor",
                "nox_emission_factor_schedule_name",
                "n2o_emission_factor",
                "n2o_emission_factor_schedule_name",
                "so2_emission_factor",
                "so2_emission_factor_schedule_name",
                "pm_emission_factor",
                "pm_emission_factor_schedule_name",
                "pm10_emission_factor",
                "pm10_emission_factor_schedule_name",
                "pm2_5_emission_factor",
                "pm2_5_emission_factor_schedule_name",
                "nh3_emission_factor",
                "nh3_emission_factor_schedule_name",
                "nmvoc_emission_factor",
                "nmvoc_emission_factor_schedule_name",
                "hg_emission_factor",
                "hg_emission_factor_schedule_name",
                "pb_emission_factor",
                "pb_emission_factor_schedule_name",
                "water_emission_factor",
                "water_emission_factor_schedule_name",
                "nuclear_high_level_emission_factor",
                "nuclear_high_level_emission_factor_schedule_name",
                "nuclear_low_level_emission_factor",
                "nuclear_low_level_emission_factor_schedule_name"
            ],
            "alphas": {
                "fields": [
                    "existing_fuel_resource_name",
                    "units_of_measure",
                    "source_energy_schedule_name",
                    "co2_emission_factor_schedule_name",
                    "co_emission_factor_schedule_name",
                    "ch4_emission_factor_schedule_name",
                    "nox_emission_factor_schedule_name",
                    "n2o_emission_factor_schedule_name",
                    "so2_emission_factor_schedule_name",
                    "pm_emission_factor_schedule_name",
                    "pm10_emission_factor_schedule_name",
                    "pm2_5_emission_factor_schedule_name",
                    "nh3_emission_factor_schedule_name",
                    "nmvoc_emission_factor_schedule_name",
                    "hg_emission_factor_schedule_name",
                    "pb_emission_factor_schedule_name",
                    "water_emission_factor_schedule_name",
                    "nuclear_high_level_emission_factor_schedule_name",
                    "nuclear_low_level_emission_factor_schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "energy_per_unit_factor",
                    "source_energy_factor",
                    "co2_emission_factor",
                    "co_emission_factor",
                    "ch4_emission_factor",
                    "nox_emission_factor",
                    "n2o_emission_factor",
                    "so2_emission_factor",
                    "pm_emission_factor",
                    "pm10_emission_factor",
                    "pm2_5_emission_factor",
                    "nh3_emission_factor",
                    "nmvoc_emission_factor",
                    "hg_emission_factor",
                    "pb_emission_factor",
                    "water_emission_factor",
                    "nuclear_high_level_emission_factor",
                    "nuclear_low_level_emission_factor"
                ]
            }
        },
        "type": "object",
        "memo": "Provides Fuel Factors for Emissions as well as Source=>Site conversions. OtherFuel1, OtherFuel2 provide options for users who want to create and use fuels that may not be mainstream (biomass, wood, pellets)."
    }
}
```
