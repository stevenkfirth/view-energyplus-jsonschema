```
{
    "ZoneEarthtube": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "zone_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "design_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "note": "\"Edesign\" in Equation",
                        "minimum": 0.0
                    },
                    "minimum_zone_temperature_when_cooling": {
                        "type": "number",
                        "note": "this is the indoor temperature below which the earth tube is shut off",
                        "units": "C",
                        "minimum": -100.0,
                        "maximum": 100.0
                    },
                    "maximum_zone_temperature_when_heating": {
                        "type": "number",
                        "note": "this is the indoor temperature above which the earth tube is shut off",
                        "units": "C",
                        "minimum": -100.0,
                        "maximum": 100.0
                    },
                    "delta_temperature": {
                        "type": "number",
                        "note": "This is the temperature difference between indoor and outdoor below which the earth tube is shut off",
                        "units": "deltaC",
                        "minimum": 0.0
                    },
                    "earthtube_type": {
                        "type": "string",
                        "enum": [
                            "",
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
                    "pipe_radius": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "default": 1.0
                    },
                    "pipe_thickness": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "default": 0.2
                    },
                    "pipe_length": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "default": 15.0
                    },
                    "pipe_thermal_conductivity": {
                        "type": "number",
                        "units": "W/m-K",
                        "exclusiveMinimum": 0.0,
                        "default": 200.0
                    },
                    "pipe_depth_under_ground_surface": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "default": 3.0
                    },
                    "soil_condition": {
                        "type": "string",
                        "enum": [
                            "",
                            "HeavyAndDamp",
                            "HeavyAndDry",
                            "HeavyAndSaturated",
                            "LightAndDry"
                        ],
                        "default": "HeavyAndDamp"
                    },
                    "average_soil_surface_temperature": {
                        "type": "number",
                        "units": "C"
                    },
                    "amplitude_of_soil_surface_temperature": {
                        "type": "number",
                        "units": "deltaC",
                        "minimum": 0.0
                    },
                    "phase_constant_of_soil_surface_temperature": {
                        "type": "number",
                        "units": "days",
                        "minimum": 0.0
                    },
                    "constant_term_flow_coefficient": {
                        "type": "number",
                        "note": "\"A\" in Equation",
                        "default": 1.0
                    },
                    "temperature_term_flow_coefficient": {
                        "type": "number",
                        "note": "\"B\" in Equation",
                        "default": 0.0
                    },
                    "velocity_term_flow_coefficient": {
                        "type": "number",
                        "note": "\"C\" in Equation",
                        "default": 0.0
                    },
                    "velocity_squared_term_flow_coefficient": {
                        "type": "number",
                        "note": "\"D\" in Equation",
                        "default": 0.0
                    }
                },
                "required": [
                    "zone_name",
                    "schedule_name",
                    "design_flow_rate",
                    "minimum_zone_temperature_when_cooling",
                    "maximum_zone_temperature_when_heating",
                    "delta_temperature",
                    "average_soil_surface_temperature",
                    "amplitude_of_soil_surface_temperature",
                    "phase_constant_of_soil_surface_temperature"
                ]
            }
        },
        "group": "Zone Airflow",
        "legacy_idd": {
            "field_info": {
                "zone_name": {
                    "field_name": "Zone Name",
                    "field_type": "a"
                },
                "schedule_name": {
                    "field_name": "Schedule Name",
                    "field_type": "a"
                },
                "design_flow_rate": {
                    "field_name": "Design Flow Rate",
                    "field_type": "n"
                },
                "minimum_zone_temperature_when_cooling": {
                    "field_name": "Minimum Zone Temperature when Cooling",
                    "field_type": "n"
                },
                "maximum_zone_temperature_when_heating": {
                    "field_name": "Maximum Zone Temperature when Heating",
                    "field_type": "n"
                },
                "delta_temperature": {
                    "field_name": "Delta Temperature",
                    "field_type": "n"
                },
                "earthtube_type": {
                    "field_name": "Earthtube Type",
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
                "pipe_radius": {
                    "field_name": "Pipe Radius",
                    "field_type": "n"
                },
                "pipe_thickness": {
                    "field_name": "Pipe Thickness",
                    "field_type": "n"
                },
                "pipe_length": {
                    "field_name": "Pipe Length",
                    "field_type": "n"
                },
                "pipe_thermal_conductivity": {
                    "field_name": "Pipe Thermal Conductivity",
                    "field_type": "n"
                },
                "pipe_depth_under_ground_surface": {
                    "field_name": "Pipe Depth Under Ground Surface",
                    "field_type": "n"
                },
                "soil_condition": {
                    "field_name": "Soil Condition",
                    "field_type": "a"
                },
                "average_soil_surface_temperature": {
                    "field_name": "Average Soil Surface Temperature",
                    "field_type": "n"
                },
                "amplitude_of_soil_surface_temperature": {
                    "field_name": "Amplitude of Soil Surface Temperature",
                    "field_type": "n"
                },
                "phase_constant_of_soil_surface_temperature": {
                    "field_name": "Phase Constant of Soil Surface Temperature",
                    "field_type": "n"
                },
                "constant_term_flow_coefficient": {
                    "field_name": "Constant Term Flow Coefficient",
                    "field_type": "n"
                },
                "temperature_term_flow_coefficient": {
                    "field_name": "Temperature Term Flow Coefficient",
                    "field_type": "n"
                },
                "velocity_term_flow_coefficient": {
                    "field_name": "Velocity Term Flow Coefficient",
                    "field_type": "n"
                },
                "velocity_squared_term_flow_coefficient": {
                    "field_name": "Velocity Squared Term Flow Coefficient",
                    "field_type": "n"
                }
            },
            "fields": [
                "zone_name",
                "schedule_name",
                "design_flow_rate",
                "minimum_zone_temperature_when_cooling",
                "maximum_zone_temperature_when_heating",
                "delta_temperature",
                "earthtube_type",
                "fan_pressure_rise",
                "fan_total_efficiency",
                "pipe_radius",
                "pipe_thickness",
                "pipe_length",
                "pipe_thermal_conductivity",
                "pipe_depth_under_ground_surface",
                "soil_condition",
                "average_soil_surface_temperature",
                "amplitude_of_soil_surface_temperature",
                "phase_constant_of_soil_surface_temperature",
                "constant_term_flow_coefficient",
                "temperature_term_flow_coefficient",
                "velocity_term_flow_coefficient",
                "velocity_squared_term_flow_coefficient"
            ],
            "alphas": {
                "fields": [
                    "zone_name",
                    "schedule_name",
                    "earthtube_type",
                    "soil_condition"
                ]
            },
            "numerics": {
                "fields": [
                    "design_flow_rate",
                    "minimum_zone_temperature_when_cooling",
                    "maximum_zone_temperature_when_heating",
                    "delta_temperature",
                    "fan_pressure_rise",
                    "fan_total_efficiency",
                    "pipe_radius",
                    "pipe_thickness",
                    "pipe_length",
                    "pipe_thermal_conductivity",
                    "pipe_depth_under_ground_surface",
                    "average_soil_surface_temperature",
                    "amplitude_of_soil_surface_temperature",
                    "phase_constant_of_soil_surface_temperature",
                    "constant_term_flow_coefficient",
                    "temperature_term_flow_coefficient",
                    "velocity_term_flow_coefficient",
                    "velocity_squared_term_flow_coefficient"
                ]
            }
        },
        "type": "object",
        "memo": "Earth Tube is specified as a design level which is modified by a Schedule fraction, temperature difference and wind speed: Earthtube=Edesign * Fschedule * (A + B*|(Tzone-Todb)| + C*WindSpd + D * WindSpd**2)",
        "min_fields": 22.0
    }
}
```
