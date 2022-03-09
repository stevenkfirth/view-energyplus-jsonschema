```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "zone_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "calculate_zone_internal_thermal_mass": {
                    "type": "string",
                    "note": "Use measured zone air temperature to calculate zone internal thermal mass. If set to Yes, the measured zone air temperature should be provided to calculate the thermal mass. If set to No, the inverse calculation of thermal mass will not be activated.",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "No"
                },
                "calculate_zone_air_infiltration_rate": {
                    "type": "string",
                    "note": "Use measured temperature data (temperature, humidity ratio, or CO2 concentration) to calculate zone air infiltration air flow rate. Only one of field Calculate Zone Internal Thermal Mass, Calculate Zone Air Infiltration Rate, and Calculate Zone People Count can be set to YES at a time. By default, this field is set to NO. When set to NO, the inverse calculation of the zone air infiltration rate will not be activated. If this field is set to YES, one of the following fields (combinations) should be provided: 1. Measurements were conducted when HVAC is free-floating: 1.1 Zone Measured Air Temperature Schedule Name 1.2 Zone Measured Air Humidity Ratio Schedule Name 1.3 Zone Measured Air CO2 Concentration Schedule Name 2. Measurements were conducted when HVAC is on: 2.1 Zone Measured Air Temperature Schedule Name, Zone Input Supply Air Temperature Schedule Name, and Zone Input Supply Air Mass Flow Rate Schedule Name 2.2 Zone Measured Air Humidity Ratio Schedule Name, Zone Input Supply Air Temperature Schedule Name, Zone Input Supply Air Mass Flow Rate Schedule Name, and Zone Input Supply Air Humidity Ratio Schedule Name 2.3 Zone Measured Air CO2 Concentration Schedule Name, Zone Input Supply Air Mass Flow Rate Schedule Name, and Zone Input Supply Air CO2 Concentration Schedule Name",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "No"
                },
                "calculate_zone_people_count": {
                    "type": "string",
                    "note": "Use measured humidity ratio data (temperature, humidity ratio, or CO2 concentration) to calculate zone people count. Only one of field Calculate Zone Internal Thermal Mass, Calculate Zone Air Infiltration Rate, and Calculate Zone People Count can be set to YES at a time. By default, this field is set to NO. When set to NO, the inverse calculation of the zone people count will not be activated. If this field is set to YES, one of the following fields (combinations) should be provided: 1. Measurements were conducted when HVAC is free-floating: 1.1 Zone Measured Air Temperature Schedule Name 1.2 Zone Measured Air Humidity Ratio Schedule Name 1.3 Zone Measured Air CO2 Concentration Schedule Name 2. Measurements were conducted when HVAC is on: 2.1 Zone Measured Air Temperature Schedule Name, Zone Input Supply Air Temperature Schedule Name, and Zone Input Supply Air Mass Flow Rate Schedule Name 2.2 Zone Measured Air Humidity Ratio Schedule Name, Zone Input Supply Air Temperature Schedule Name, Zone Input Supply Air Mass Flow Rate Schedule Name, and Zone Input Supply Air Humidity Ratio Schedule Name 2.3 Zone Measured Air CO2 Concentration Schedule Name, Zone Input Supply Air Mass Flow Rate Schedule Name, and Zone Input Supply Air CO2 Concentration Schedule Name Field Zone Input People Activity Schedule Name, Zone Input People Sensible Heat Fraction Schedule Name, Zone Input People Radiant Heat Fraction Schedule Name, Zone Input People CO2 Generation Rate Schedule Name are optional. If provided, the default people activity level (130W), sensible heat generation rate (78W), latent heat generation (52W) rate, and CO2 generation rate (0.0000000382 [m3/(s*W)]) will be overwritten correspondingly.",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "No"
                },
                "zone_measured_air_temperature_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "from Schedule:File"
                },
                "zone_measured_air_humidity_ratio_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "from Schedule:File"
                },
                "zone_measured_air_co2_concentration_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "from Schedule:File"
                },
                "zone_input_people_activity_schedule_name": {
                    "type": "string",
                    "note": "When this field is provided and valid, the default people activity level (used to calculate people count) will be overwritten. from Schedule:File",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "zone_input_people_sensible_heat_fraction_schedule_name": {
                    "type": "string",
                    "note": "When this field is provided and valid, the default sensible heat fraction from people (used to calculate people count) will be overwritten. from Schedule:File",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "zone_input_people_radiant_heat_fraction_schedule_name": {
                    "type": "string",
                    "note": "When this field is provided and valid, the default radiant heat portion of the sensible heat from people (used to calculate people count) will be overwritten. from Schedule:File",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "zone_input_people_co2_generation_rate_schedule_name": {
                    "type": "string",
                    "note": "When this field is provided and valid, the default people CO2 generation rate (used to calculate people count) will be overwritten. from Schedule:File",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "zone_input_supply_air_temperature_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "from Schedule:File"
                },
                "zone_input_supply_air_mass_flow_rate_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "from Schedule:File"
                },
                "zone_input_supply_air_humidity_ratio_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "from Schedule:File"
                },
                "zone_input_supply_air_co2_concentration_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "from Schedule:File"
                },
                "begin_month": {
                    "type": "number",
                    "minimum": 1.0,
                    "maximum": 12.0
                },
                "begin_day_of_month": {
                    "type": "number",
                    "minimum": 1.0,
                    "maximum": 31.0
                },
                "end_month": {
                    "type": "number",
                    "minimum": 1.0,
                    "maximum": 12.0
                },
                "end_day_of_month": {
                    "type": "number",
                    "minimum": 1.0,
                    "maximum": 31.0
                }
            },
            "required": [
                "zone_name",
                "begin_month",
                "begin_day_of_month",
                "end_month",
                "end_day_of_month"
            ]
        }
    },
    "group": "Hybrid Model",
    "name": {
        "type": "string",
        "is_required": true
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "zone_name": {
                "field_name": "Zone Name",
                "field_type": "a"
            },
            "calculate_zone_internal_thermal_mass": {
                "field_name": "Calculate Zone Internal Thermal Mass",
                "field_type": "a"
            },
            "calculate_zone_air_infiltration_rate": {
                "field_name": "Calculate Zone Air Infiltration Rate",
                "field_type": "a"
            },
            "calculate_zone_people_count": {
                "field_name": "Calculate Zone People Count",
                "field_type": "a"
            },
            "zone_measured_air_temperature_schedule_name": {
                "field_name": "Zone Measured Air Temperature Schedule Name",
                "field_type": "a"
            },
            "zone_measured_air_humidity_ratio_schedule_name": {
                "field_name": "Zone Measured Air Humidity Ratio Schedule Name",
                "field_type": "a"
            },
            "zone_measured_air_co2_concentration_schedule_name": {
                "field_name": "Zone Measured Air CO2 Concentration Schedule Name",
                "field_type": "a"
            },
            "zone_input_people_activity_schedule_name": {
                "field_name": "Zone Input People Activity Schedule Name",
                "field_type": "a"
            },
            "zone_input_people_sensible_heat_fraction_schedule_name": {
                "field_name": "Zone Input People Sensible Heat Fraction Schedule Name",
                "field_type": "a"
            },
            "zone_input_people_radiant_heat_fraction_schedule_name": {
                "field_name": "Zone Input People Radiant Heat Fraction Schedule Name",
                "field_type": "a"
            },
            "zone_input_people_co2_generation_rate_schedule_name": {
                "field_name": "Zone Input People CO2 Generation Rate Schedule Name",
                "field_type": "a"
            },
            "zone_input_supply_air_temperature_schedule_name": {
                "field_name": "Zone Input Supply Air Temperature Schedule Name",
                "field_type": "a"
            },
            "zone_input_supply_air_mass_flow_rate_schedule_name": {
                "field_name": "Zone Input Supply Air Mass Flow Rate Schedule Name",
                "field_type": "a"
            },
            "zone_input_supply_air_humidity_ratio_schedule_name": {
                "field_name": "Zone Input Supply Air Humidity Ratio Schedule Name",
                "field_type": "a"
            },
            "zone_input_supply_air_co2_concentration_schedule_name": {
                "field_name": "Zone Input Supply Air CO2 Concentration Schedule Name",
                "field_type": "a"
            },
            "begin_month": {
                "field_name": "Begin Month",
                "field_type": "n"
            },
            "begin_day_of_month": {
                "field_name": "Begin Day of Month",
                "field_type": "n"
            },
            "end_month": {
                "field_name": "End Month",
                "field_type": "n"
            },
            "end_day_of_month": {
                "field_name": "End Day of Month",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "zone_name",
            "calculate_zone_internal_thermal_mass",
            "calculate_zone_air_infiltration_rate",
            "calculate_zone_people_count",
            "zone_measured_air_temperature_schedule_name",
            "zone_measured_air_humidity_ratio_schedule_name",
            "zone_measured_air_co2_concentration_schedule_name",
            "zone_input_people_activity_schedule_name",
            "zone_input_people_sensible_heat_fraction_schedule_name",
            "zone_input_people_radiant_heat_fraction_schedule_name",
            "zone_input_people_co2_generation_rate_schedule_name",
            "zone_input_supply_air_temperature_schedule_name",
            "zone_input_supply_air_mass_flow_rate_schedule_name",
            "zone_input_supply_air_humidity_ratio_schedule_name",
            "zone_input_supply_air_co2_concentration_schedule_name",
            "begin_month",
            "begin_day_of_month",
            "end_month",
            "end_day_of_month"
        ],
        "alphas": {
            "fields": [
                "name",
                "zone_name",
                "calculate_zone_internal_thermal_mass",
                "calculate_zone_air_infiltration_rate",
                "calculate_zone_people_count",
                "zone_measured_air_temperature_schedule_name",
                "zone_measured_air_humidity_ratio_schedule_name",
                "zone_measured_air_co2_concentration_schedule_name",
                "zone_input_people_activity_schedule_name",
                "zone_input_people_sensible_heat_fraction_schedule_name",
                "zone_input_people_radiant_heat_fraction_schedule_name",
                "zone_input_people_co2_generation_rate_schedule_name",
                "zone_input_supply_air_temperature_schedule_name",
                "zone_input_supply_air_mass_flow_rate_schedule_name",
                "zone_input_supply_air_humidity_ratio_schedule_name",
                "zone_input_supply_air_co2_concentration_schedule_name"
            ]
        },
        "numerics": {
            "fields": [
                "begin_month",
                "begin_day_of_month",
                "end_month",
                "end_day_of_month"
            ]
        }
    },
    "type": "object",
    "memo": "Zones with measured air temperature data and a range of dates. If the range of temperature measurement dates includes a leap day, the weather data should include a leap day."
}
```
