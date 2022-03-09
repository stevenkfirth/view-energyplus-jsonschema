```
{
    "ZoneVentilation:DesignFlowRate": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "zone_or_zonelist_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneAndZoneListNames"
                        ]
                    },
                    "schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "design_flow_rate_calculation_method": {
                        "type": "string",
                        "note": "The entered calculation method is used to create the maximum amount of ventilation for this set of attributes Choices: Flow/Zone => Design Flow Rate -- simply enter Design Flow Rate Flow/Area => Flow Rate per Zone Floor Area - Value * Floor Area (zone) = Design Flow Rate Flow/Person => Flow Rate per Person - Value * #people = Design Flow Rate AirChanges/Hour => Air Changes per Hour - Value * Floor Volume (zone) adjusted for m3/s = Design Volume Flow Rate \"Vdesign\" in Equation is the result.",
                        "enum": [
                            "",
                            "AirChanges/Hour",
                            "Flow/Area",
                            "Flow/Person",
                            "Flow/Zone"
                        ],
                        "default": "Flow/Zone"
                    },
                    "design_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0
                    },
                    "flow_rate_per_zone_floor_area": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m3/s-m2"
                    },
                    "flow_rate_per_person": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m3/s-person"
                    },
                    "air_changes_per_hour": {
                        "type": "number",
                        "units": "1/hr",
                        "minimum": 0.0
                    },
                    "ventilation_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Balanced",
                            "Exhaust",
                            "Intake",
                            "Natural"
                        ],
                        "default": "Natural"
                    },
                    "fan_pressure_rise": {
                        "type": "number",
                        "note": "pressure rise across the fan",
                        "units": "Pa",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "fan_total_efficiency": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "default": 1.0
                    },
                    "constant_term_coefficient": {
                        "type": "number",
                        "note": "\"A\" in Equation",
                        "default": 1.0
                    },
                    "temperature_term_coefficient": {
                        "type": "number",
                        "note": "\"B\" in Equation",
                        "default": 0.0
                    },
                    "velocity_term_coefficient": {
                        "type": "number",
                        "note": "\"C\" in Equation",
                        "default": 0.0
                    },
                    "velocity_squared_term_coefficient": {
                        "type": "number",
                        "note": "\"D\" in Equation",
                        "default": 0.0
                    },
                    "minimum_indoor_temperature": {
                        "type": "number",
                        "note": "this is the indoor temperature below which ventilation is shutoff",
                        "units": "C",
                        "minimum": -100.0,
                        "maximum": 100.0,
                        "default": -100.0
                    },
                    "minimum_indoor_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "This schedule contains the indoor temperature versus time below which ventilation is shutoff."
                    },
                    "maximum_indoor_temperature": {
                        "type": "number",
                        "note": "this is the indoor temperature above which ventilation is shutoff",
                        "units": "C",
                        "minimum": -100.0,
                        "maximum": 100.0,
                        "default": 100.0
                    },
                    "maximum_indoor_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "This schedule contains the indoor temperature versus time above which ventilation is shutoff."
                    },
                    "delta_temperature": {
                        "type": "number",
                        "note": "This is the temperature differential between indoor and outdoor below which ventilation is shutoff. If ((IndoorTemp - OutdoorTemp) < DeltaTemperature) then ventilation is not allowed. For example, if delta temperature is 2C, ventilation is assumed to be available if the outside air temperature is at least 2C cooler than the zone air temperature. The values for this field can include negative numbers. This allows ventilation to occur even if the outdoor temperature is above the indoor temperature.",
                        "units": "deltaC",
                        "minimum": -100.0,
                        "default": -100.0
                    },
                    "delta_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "This schedule contains the temperature differential between indoor and outdoor versus time below which ventilation is shutoff."
                    },
                    "minimum_outdoor_temperature": {
                        "type": "number",
                        "note": "this is the outdoor temperature below which ventilation is shutoff",
                        "units": "C",
                        "minimum": -100.0,
                        "maximum": 100.0,
                        "default": -100.0
                    },
                    "minimum_outdoor_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "This schedule contains the outdoor temperature versus time below which ventilation is shutoff."
                    },
                    "maximum_outdoor_temperature": {
                        "type": "number",
                        "note": "this is the outdoor temperature above which ventilation is shutoff",
                        "units": "C",
                        "minimum": -100.0,
                        "maximum": 100.0,
                        "default": 100.0
                    },
                    "maximum_outdoor_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "This schedule contains the outdoor temperature versus time above which ventilation is shutoff."
                    },
                    "maximum_wind_speed": {
                        "type": "number",
                        "note": "this is the outdoor wind speed above which ventilation is shutoff",
                        "units": "m/s",
                        "minimum": 0.0,
                        "maximum": 40.0,
                        "default": 40.0
                    }
                },
                "required": [
                    "zone_or_zonelist_name",
                    "schedule_name"
                ]
            }
        },
        "group": "Zone Airflow",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "VentilationNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "zone_or_zonelist_name": {
                    "field_name": "Zone or ZoneList Name",
                    "field_type": "a"
                },
                "schedule_name": {
                    "field_name": "Schedule Name",
                    "field_type": "a"
                },
                "design_flow_rate_calculation_method": {
                    "field_name": "Design Flow Rate Calculation Method",
                    "field_type": "a"
                },
                "design_flow_rate": {
                    "field_name": "Design Flow Rate",
                    "field_type": "n"
                },
                "flow_rate_per_zone_floor_area": {
                    "field_name": "Flow Rate per Zone Floor Area",
                    "field_type": "n"
                },
                "flow_rate_per_person": {
                    "field_name": "Flow Rate per Person",
                    "field_type": "n"
                },
                "air_changes_per_hour": {
                    "field_name": "Air Changes per Hour",
                    "field_type": "n"
                },
                "ventilation_type": {
                    "field_name": "Ventilation Type",
                    "field_type": "a"
                },
                "fan_pressure_rise": {
                    "field_name": "Fan Pressure Rise",
                    "field_type": "n"
                },
                "fan_total_efficiency": {
                    "field_name": "Fan Total Efficiency",
                    "field_type": "n"
                },
                "constant_term_coefficient": {
                    "field_name": "Constant Term Coefficient",
                    "field_type": "n"
                },
                "temperature_term_coefficient": {
                    "field_name": "Temperature Term Coefficient",
                    "field_type": "n"
                },
                "velocity_term_coefficient": {
                    "field_name": "Velocity Term Coefficient",
                    "field_type": "n"
                },
                "velocity_squared_term_coefficient": {
                    "field_name": "Velocity Squared Term Coefficient",
                    "field_type": "n"
                },
                "minimum_indoor_temperature": {
                    "field_name": "Minimum Indoor Temperature",
                    "field_type": "n"
                },
                "minimum_indoor_temperature_schedule_name": {
                    "field_name": "Minimum Indoor Temperature Schedule Name",
                    "field_type": "a"
                },
                "maximum_indoor_temperature": {
                    "field_name": "Maximum Indoor Temperature",
                    "field_type": "n"
                },
                "maximum_indoor_temperature_schedule_name": {
                    "field_name": "Maximum Indoor Temperature Schedule Name",
                    "field_type": "a"
                },
                "delta_temperature": {
                    "field_name": "Delta Temperature",
                    "field_type": "n"
                },
                "delta_temperature_schedule_name": {
                    "field_name": "Delta Temperature Schedule Name",
                    "field_type": "a"
                },
                "minimum_outdoor_temperature": {
                    "field_name": "Minimum Outdoor Temperature",
                    "field_type": "n"
                },
                "minimum_outdoor_temperature_schedule_name": {
                    "field_name": "Minimum Outdoor Temperature Schedule Name",
                    "field_type": "a"
                },
                "maximum_outdoor_temperature": {
                    "field_name": "Maximum Outdoor Temperature",
                    "field_type": "n"
                },
                "maximum_outdoor_temperature_schedule_name": {
                    "field_name": "Maximum Outdoor Temperature Schedule Name",
                    "field_type": "a"
                },
                "maximum_wind_speed": {
                    "field_name": "Maximum Wind Speed",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "zone_or_zonelist_name",
                "schedule_name",
                "design_flow_rate_calculation_method",
                "design_flow_rate",
                "flow_rate_per_zone_floor_area",
                "flow_rate_per_person",
                "air_changes_per_hour",
                "ventilation_type",
                "fan_pressure_rise",
                "fan_total_efficiency",
                "constant_term_coefficient",
                "temperature_term_coefficient",
                "velocity_term_coefficient",
                "velocity_squared_term_coefficient",
                "minimum_indoor_temperature",
                "minimum_indoor_temperature_schedule_name",
                "maximum_indoor_temperature",
                "maximum_indoor_temperature_schedule_name",
                "delta_temperature",
                "delta_temperature_schedule_name",
                "minimum_outdoor_temperature",
                "minimum_outdoor_temperature_schedule_name",
                "maximum_outdoor_temperature",
                "maximum_outdoor_temperature_schedule_name",
                "maximum_wind_speed"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "zone_or_zonelist_name",
                    "schedule_name",
                    "design_flow_rate_calculation_method",
                    "ventilation_type",
                    "minimum_indoor_temperature_schedule_name",
                    "maximum_indoor_temperature_schedule_name",
                    "delta_temperature_schedule_name",
                    "minimum_outdoor_temperature_schedule_name",
                    "maximum_outdoor_temperature_schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "design_flow_rate",
                    "flow_rate_per_zone_floor_area",
                    "flow_rate_per_person",
                    "air_changes_per_hour",
                    "fan_pressure_rise",
                    "fan_total_efficiency",
                    "constant_term_coefficient",
                    "temperature_term_coefficient",
                    "velocity_term_coefficient",
                    "velocity_squared_term_coefficient",
                    "minimum_indoor_temperature",
                    "maximum_indoor_temperature",
                    "delta_temperature",
                    "minimum_outdoor_temperature",
                    "maximum_outdoor_temperature",
                    "maximum_wind_speed"
                ]
            }
        },
        "type": "object",
        "memo": "Ventilation is specified as a design level which is modified by a schedule fraction, temperature difference and wind speed: Ventilation=Vdesign * Fschedule * (A + B*|(Tzone-Todb)| + C*WindSpd + D * WindSpd**2) If you use a ZoneList in the Zone or ZoneList name field then this definition applies to all the zones in the ZoneList.",
        "min_fields": 15.0
    }
}
```
