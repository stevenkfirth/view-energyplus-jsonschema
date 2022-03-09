```
{
    "HeatExchanger:Desiccant:BalancedFlow:PerformanceDataType1": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "nominal_air_flow_rate": {
                        "note": "Air flow rate at nominal conditions (assumed to be the same for both sides of the heat exchanger).",
                        "units": "m3/s",
                        "anyOf": [
                            {
                                "type": "number",
                                "exclusiveMinimum": 0.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "nominal_air_face_velocity": {
                        "units": "m/s",
                        "anyOf": [
                            {
                                "type": "number",
                                "exclusiveMinimum": 0.0,
                                "maximum": 6.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "nominal_electric_power": {
                        "type": "number",
                        "note": "Parasitic electric power (e.g., desiccant wheel motor)",
                        "units": "W",
                        "ip-units": "W",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "temperature_equation_coefficient_1": {
                        "type": "number"
                    },
                    "temperature_equation_coefficient_2": {
                        "type": "number"
                    },
                    "temperature_equation_coefficient_3": {
                        "type": "number"
                    },
                    "temperature_equation_coefficient_4": {
                        "type": "number"
                    },
                    "temperature_equation_coefficient_5": {
                        "type": "number"
                    },
                    "temperature_equation_coefficient_6": {
                        "type": "number"
                    },
                    "temperature_equation_coefficient_7": {
                        "type": "number"
                    },
                    "temperature_equation_coefficient_8": {
                        "type": "number"
                    },
                    "minimum_regeneration_inlet_air_humidity_ratio_for_temperature_equation": {
                        "type": "number",
                        "units": "kgWater/kgDryAir",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "maximum_regeneration_inlet_air_humidity_ratio_for_temperature_equation": {
                        "type": "number",
                        "units": "kgWater/kgDryAir",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "minimum_regeneration_inlet_air_temperature_for_temperature_equation": {
                        "type": "number",
                        "units": "C"
                    },
                    "maximum_regeneration_inlet_air_temperature_for_temperature_equation": {
                        "type": "number",
                        "units": "C"
                    },
                    "minimum_process_inlet_air_humidity_ratio_for_temperature_equation": {
                        "type": "number",
                        "units": "kgWater/kgDryAir",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "maximum_process_inlet_air_humidity_ratio_for_temperature_equation": {
                        "type": "number",
                        "units": "kgWater/kgDryAir",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "minimum_process_inlet_air_temperature_for_temperature_equation": {
                        "type": "number",
                        "units": "C"
                    },
                    "maximum_process_inlet_air_temperature_for_temperature_equation": {
                        "type": "number",
                        "units": "C"
                    },
                    "minimum_regeneration_air_velocity_for_temperature_equation": {
                        "type": "number",
                        "units": "m/s",
                        "exclusiveMinimum": 0.0
                    },
                    "maximum_regeneration_air_velocity_for_temperature_equation": {
                        "type": "number",
                        "units": "m/s",
                        "exclusiveMinimum": 0.0
                    },
                    "minimum_regeneration_outlet_air_temperature_for_temperature_equation": {
                        "type": "number",
                        "units": "C"
                    },
                    "maximum_regeneration_outlet_air_temperature_for_temperature_equation": {
                        "type": "number",
                        "units": "C"
                    },
                    "minimum_regeneration_inlet_air_relative_humidity_for_temperature_equation": {
                        "type": "number",
                        "units": "percent",
                        "minimum": 0.0,
                        "maximum": 100.0
                    },
                    "maximum_regeneration_inlet_air_relative_humidity_for_temperature_equation": {
                        "type": "number",
                        "units": "percent",
                        "minimum": 0.0,
                        "maximum": 100.0
                    },
                    "minimum_process_inlet_air_relative_humidity_for_temperature_equation": {
                        "type": "number",
                        "units": "percent",
                        "minimum": 0.0,
                        "maximum": 100.0
                    },
                    "maximum_process_inlet_air_relative_humidity_for_temperature_equation": {
                        "type": "number",
                        "units": "percent",
                        "minimum": 0.0,
                        "maximum": 100.0
                    },
                    "humidity_ratio_equation_coefficient_1": {
                        "type": "number"
                    },
                    "humidity_ratio_equation_coefficient_2": {
                        "type": "number"
                    },
                    "humidity_ratio_equation_coefficient_3": {
                        "type": "number"
                    },
                    "humidity_ratio_equation_coefficient_4": {
                        "type": "number"
                    },
                    "humidity_ratio_equation_coefficient_5": {
                        "type": "number"
                    },
                    "humidity_ratio_equation_coefficient_6": {
                        "type": "number"
                    },
                    "humidity_ratio_equation_coefficient_7": {
                        "type": "number"
                    },
                    "humidity_ratio_equation_coefficient_8": {
                        "type": "number"
                    },
                    "minimum_regeneration_inlet_air_humidity_ratio_for_humidity_ratio_equation": {
                        "type": "number",
                        "units": "kgWater/kgDryAir",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "maximum_regeneration_inlet_air_humidity_ratio_for_humidity_ratio_equation": {
                        "type": "number",
                        "units": "kgWater/kgDryAir",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "minimum_regeneration_inlet_air_temperature_for_humidity_ratio_equation": {
                        "type": "number",
                        "units": "C"
                    },
                    "maximum_regeneration_inlet_air_temperature_for_humidity_ratio_equation": {
                        "type": "number",
                        "units": "C"
                    },
                    "minimum_process_inlet_air_humidity_ratio_for_humidity_ratio_equation": {
                        "type": "number",
                        "units": "kgWater/kgDryAir",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "maximum_process_inlet_air_humidity_ratio_for_humidity_ratio_equation": {
                        "type": "number",
                        "units": "kgWater/kgDryAir",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "minimum_process_inlet_air_temperature_for_humidity_ratio_equation": {
                        "type": "number",
                        "units": "C"
                    },
                    "maximum_process_inlet_air_temperature_for_humidity_ratio_equation": {
                        "type": "number",
                        "units": "C"
                    },
                    "minimum_regeneration_air_velocity_for_humidity_ratio_equation": {
                        "type": "number",
                        "units": "m/s",
                        "exclusiveMinimum": 0.0
                    },
                    "maximum_regeneration_air_velocity_for_humidity_ratio_equation": {
                        "type": "number",
                        "units": "m/s",
                        "exclusiveMinimum": 0.0
                    },
                    "minimum_regeneration_outlet_air_humidity_ratio_for_humidity_ratio_equation": {
                        "type": "number",
                        "units": "kgWater/kgDryAir",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "maximum_regeneration_outlet_air_humidity_ratio_for_humidity_ratio_equation": {
                        "type": "number",
                        "units": "kgWater/kgDryAir",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "minimum_regeneration_inlet_air_relative_humidity_for_humidity_ratio_equation": {
                        "type": "number",
                        "units": "percent",
                        "minimum": 0.0,
                        "maximum": 100.0
                    },
                    "maximum_regeneration_inlet_air_relative_humidity_for_humidity_ratio_equation": {
                        "type": "number",
                        "units": "percent",
                        "minimum": 0.0,
                        "maximum": 100.0
                    },
                    "minimum_process_inlet_air_relative_humidity_for_humidity_ratio_equation": {
                        "type": "number",
                        "units": "percent",
                        "minimum": 0.0,
                        "maximum": 100.0
                    },
                    "maximum_process_inlet_air_relative_humidity_for_humidity_ratio_equation": {
                        "type": "number",
                        "units": "percent",
                        "minimum": 0.0,
                        "maximum": 100.0
                    }
                },
                "required": [
                    "nominal_air_face_velocity",
                    "temperature_equation_coefficient_1",
                    "temperature_equation_coefficient_2",
                    "temperature_equation_coefficient_3",
                    "temperature_equation_coefficient_4",
                    "temperature_equation_coefficient_5",
                    "temperature_equation_coefficient_6",
                    "temperature_equation_coefficient_7",
                    "temperature_equation_coefficient_8",
                    "minimum_regeneration_inlet_air_humidity_ratio_for_temperature_equation",
                    "maximum_regeneration_inlet_air_humidity_ratio_for_temperature_equation",
                    "minimum_regeneration_inlet_air_temperature_for_temperature_equation",
                    "maximum_regeneration_inlet_air_temperature_for_temperature_equation",
                    "minimum_process_inlet_air_humidity_ratio_for_temperature_equation",
                    "maximum_process_inlet_air_humidity_ratio_for_temperature_equation",
                    "minimum_process_inlet_air_temperature_for_temperature_equation",
                    "maximum_process_inlet_air_temperature_for_temperature_equation",
                    "minimum_regeneration_air_velocity_for_temperature_equation",
                    "maximum_regeneration_air_velocity_for_temperature_equation",
                    "minimum_regeneration_outlet_air_temperature_for_temperature_equation",
                    "maximum_regeneration_outlet_air_temperature_for_temperature_equation",
                    "minimum_regeneration_inlet_air_relative_humidity_for_temperature_equation",
                    "maximum_regeneration_inlet_air_relative_humidity_for_temperature_equation",
                    "minimum_process_inlet_air_relative_humidity_for_temperature_equation",
                    "maximum_process_inlet_air_relative_humidity_for_temperature_equation",
                    "humidity_ratio_equation_coefficient_1",
                    "humidity_ratio_equation_coefficient_2",
                    "humidity_ratio_equation_coefficient_3",
                    "humidity_ratio_equation_coefficient_4",
                    "humidity_ratio_equation_coefficient_5",
                    "humidity_ratio_equation_coefficient_6",
                    "humidity_ratio_equation_coefficient_7",
                    "humidity_ratio_equation_coefficient_8",
                    "minimum_regeneration_inlet_air_humidity_ratio_for_humidity_ratio_equation",
                    "maximum_regeneration_inlet_air_humidity_ratio_for_humidity_ratio_equation",
                    "minimum_regeneration_inlet_air_temperature_for_humidity_ratio_equation",
                    "maximum_regeneration_inlet_air_temperature_for_humidity_ratio_equation",
                    "minimum_process_inlet_air_humidity_ratio_for_humidity_ratio_equation",
                    "maximum_process_inlet_air_humidity_ratio_for_humidity_ratio_equation",
                    "minimum_process_inlet_air_temperature_for_humidity_ratio_equation",
                    "maximum_process_inlet_air_temperature_for_humidity_ratio_equation",
                    "minimum_regeneration_air_velocity_for_humidity_ratio_equation",
                    "maximum_regeneration_air_velocity_for_humidity_ratio_equation",
                    "minimum_regeneration_outlet_air_humidity_ratio_for_humidity_ratio_equation",
                    "maximum_regeneration_outlet_air_humidity_ratio_for_humidity_ratio_equation",
                    "minimum_regeneration_inlet_air_relative_humidity_for_humidity_ratio_equation",
                    "maximum_regeneration_inlet_air_relative_humidity_for_humidity_ratio_equation",
                    "minimum_process_inlet_air_relative_humidity_for_humidity_ratio_equation",
                    "maximum_process_inlet_air_relative_humidity_for_humidity_ratio_equation"
                ]
            }
        },
        "group": "Heat Recovery",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "DesiccantHXPerfData"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "nominal_air_flow_rate": {
                    "field_name": "Nominal Air Flow Rate",
                    "field_type": "n"
                },
                "nominal_air_face_velocity": {
                    "field_name": "Nominal Air Face Velocity",
                    "field_type": "n"
                },
                "nominal_electric_power": {
                    "field_name": "Nominal Electric Power",
                    "field_type": "n"
                },
                "temperature_equation_coefficient_1": {
                    "field_name": "Temperature Equation Coefficient 1",
                    "field_type": "n"
                },
                "temperature_equation_coefficient_2": {
                    "field_name": "Temperature Equation Coefficient 2",
                    "field_type": "n"
                },
                "temperature_equation_coefficient_3": {
                    "field_name": "Temperature Equation Coefficient 3",
                    "field_type": "n"
                },
                "temperature_equation_coefficient_4": {
                    "field_name": "Temperature Equation Coefficient 4",
                    "field_type": "n"
                },
                "temperature_equation_coefficient_5": {
                    "field_name": "Temperature Equation Coefficient 5",
                    "field_type": "n"
                },
                "temperature_equation_coefficient_6": {
                    "field_name": "Temperature Equation Coefficient 6",
                    "field_type": "n"
                },
                "temperature_equation_coefficient_7": {
                    "field_name": "Temperature Equation Coefficient 7",
                    "field_type": "n"
                },
                "temperature_equation_coefficient_8": {
                    "field_name": "Temperature Equation Coefficient 8",
                    "field_type": "n"
                },
                "minimum_regeneration_inlet_air_humidity_ratio_for_temperature_equation": {
                    "field_name": "Minimum Regeneration Inlet Air Humidity Ratio for Temperature Equation",
                    "field_type": "n"
                },
                "maximum_regeneration_inlet_air_humidity_ratio_for_temperature_equation": {
                    "field_name": "Maximum Regeneration Inlet Air Humidity Ratio for Temperature Equation",
                    "field_type": "n"
                },
                "minimum_regeneration_inlet_air_temperature_for_temperature_equation": {
                    "field_name": "Minimum Regeneration Inlet Air Temperature for Temperature Equation",
                    "field_type": "n"
                },
                "maximum_regeneration_inlet_air_temperature_for_temperature_equation": {
                    "field_name": "Maximum Regeneration Inlet Air Temperature for Temperature Equation",
                    "field_type": "n"
                },
                "minimum_process_inlet_air_humidity_ratio_for_temperature_equation": {
                    "field_name": "Minimum Process Inlet Air Humidity Ratio for Temperature Equation",
                    "field_type": "n"
                },
                "maximum_process_inlet_air_humidity_ratio_for_temperature_equation": {
                    "field_name": "Maximum Process Inlet Air Humidity Ratio for Temperature Equation",
                    "field_type": "n"
                },
                "minimum_process_inlet_air_temperature_for_temperature_equation": {
                    "field_name": "Minimum Process Inlet Air Temperature for Temperature Equation",
                    "field_type": "n"
                },
                "maximum_process_inlet_air_temperature_for_temperature_equation": {
                    "field_name": "Maximum Process Inlet Air Temperature for Temperature Equation",
                    "field_type": "n"
                },
                "minimum_regeneration_air_velocity_for_temperature_equation": {
                    "field_name": "Minimum Regeneration Air Velocity for Temperature Equation",
                    "field_type": "n"
                },
                "maximum_regeneration_air_velocity_for_temperature_equation": {
                    "field_name": "Maximum Regeneration Air Velocity for Temperature Equation",
                    "field_type": "n"
                },
                "minimum_regeneration_outlet_air_temperature_for_temperature_equation": {
                    "field_name": "Minimum Regeneration Outlet Air Temperature for Temperature Equation",
                    "field_type": "n"
                },
                "maximum_regeneration_outlet_air_temperature_for_temperature_equation": {
                    "field_name": "Maximum Regeneration Outlet Air Temperature for Temperature Equation",
                    "field_type": "n"
                },
                "minimum_regeneration_inlet_air_relative_humidity_for_temperature_equation": {
                    "field_name": "Minimum Regeneration Inlet Air Relative Humidity for Temperature Equation",
                    "field_type": "n"
                },
                "maximum_regeneration_inlet_air_relative_humidity_for_temperature_equation": {
                    "field_name": "Maximum Regeneration Inlet Air Relative Humidity for Temperature Equation",
                    "field_type": "n"
                },
                "minimum_process_inlet_air_relative_humidity_for_temperature_equation": {
                    "field_name": "Minimum Process Inlet Air Relative Humidity for Temperature Equation",
                    "field_type": "n"
                },
                "maximum_process_inlet_air_relative_humidity_for_temperature_equation": {
                    "field_name": "Maximum Process Inlet Air Relative Humidity for Temperature Equation",
                    "field_type": "n"
                },
                "humidity_ratio_equation_coefficient_1": {
                    "field_name": "Humidity Ratio Equation Coefficient 1",
                    "field_type": "n"
                },
                "humidity_ratio_equation_coefficient_2": {
                    "field_name": "Humidity Ratio Equation Coefficient 2",
                    "field_type": "n"
                },
                "humidity_ratio_equation_coefficient_3": {
                    "field_name": "Humidity Ratio Equation Coefficient 3",
                    "field_type": "n"
                },
                "humidity_ratio_equation_coefficient_4": {
                    "field_name": "Humidity Ratio Equation Coefficient 4",
                    "field_type": "n"
                },
                "humidity_ratio_equation_coefficient_5": {
                    "field_name": "Humidity Ratio Equation Coefficient 5",
                    "field_type": "n"
                },
                "humidity_ratio_equation_coefficient_6": {
                    "field_name": "Humidity Ratio Equation Coefficient 6",
                    "field_type": "n"
                },
                "humidity_ratio_equation_coefficient_7": {
                    "field_name": "Humidity Ratio Equation Coefficient 7",
                    "field_type": "n"
                },
                "humidity_ratio_equation_coefficient_8": {
                    "field_name": "Humidity Ratio Equation Coefficient 8",
                    "field_type": "n"
                },
                "minimum_regeneration_inlet_air_humidity_ratio_for_humidity_ratio_equation": {
                    "field_name": "Minimum Regeneration Inlet Air Humidity Ratio for Humidity Ratio Equation",
                    "field_type": "n"
                },
                "maximum_regeneration_inlet_air_humidity_ratio_for_humidity_ratio_equation": {
                    "field_name": "Maximum Regeneration Inlet Air Humidity Ratio for Humidity Ratio Equation",
                    "field_type": "n"
                },
                "minimum_regeneration_inlet_air_temperature_for_humidity_ratio_equation": {
                    "field_name": "Minimum Regeneration Inlet Air Temperature for Humidity Ratio Equation",
                    "field_type": "n"
                },
                "maximum_regeneration_inlet_air_temperature_for_humidity_ratio_equation": {
                    "field_name": "Maximum Regeneration Inlet Air Temperature for Humidity Ratio Equation",
                    "field_type": "n"
                },
                "minimum_process_inlet_air_humidity_ratio_for_humidity_ratio_equation": {
                    "field_name": "Minimum Process Inlet Air Humidity Ratio for Humidity Ratio Equation",
                    "field_type": "n"
                },
                "maximum_process_inlet_air_humidity_ratio_for_humidity_ratio_equation": {
                    "field_name": "Maximum Process Inlet Air Humidity Ratio for Humidity Ratio Equation",
                    "field_type": "n"
                },
                "minimum_process_inlet_air_temperature_for_humidity_ratio_equation": {
                    "field_name": "Minimum Process Inlet Air Temperature for Humidity Ratio Equation",
                    "field_type": "n"
                },
                "maximum_process_inlet_air_temperature_for_humidity_ratio_equation": {
                    "field_name": "Maximum Process Inlet Air Temperature for Humidity Ratio Equation",
                    "field_type": "n"
                },
                "minimum_regeneration_air_velocity_for_humidity_ratio_equation": {
                    "field_name": "Minimum Regeneration Air Velocity for Humidity Ratio Equation",
                    "field_type": "n"
                },
                "maximum_regeneration_air_velocity_for_humidity_ratio_equation": {
                    "field_name": "Maximum Regeneration Air Velocity for Humidity Ratio Equation",
                    "field_type": "n"
                },
                "minimum_regeneration_outlet_air_humidity_ratio_for_humidity_ratio_equation": {
                    "field_name": "Minimum Regeneration Outlet Air Humidity Ratio for Humidity Ratio Equation",
                    "field_type": "n"
                },
                "maximum_regeneration_outlet_air_humidity_ratio_for_humidity_ratio_equation": {
                    "field_name": "Maximum Regeneration Outlet Air Humidity Ratio for Humidity Ratio Equation",
                    "field_type": "n"
                },
                "minimum_regeneration_inlet_air_relative_humidity_for_humidity_ratio_equation": {
                    "field_name": "Minimum Regeneration Inlet Air Relative Humidity for Humidity Ratio Equation",
                    "field_type": "n"
                },
                "maximum_regeneration_inlet_air_relative_humidity_for_humidity_ratio_equation": {
                    "field_name": "Maximum Regeneration Inlet Air Relative Humidity for Humidity Ratio Equation",
                    "field_type": "n"
                },
                "minimum_process_inlet_air_relative_humidity_for_humidity_ratio_equation": {
                    "field_name": "Minimum Process Inlet Air Relative Humidity for Humidity Ratio Equation",
                    "field_type": "n"
                },
                "maximum_process_inlet_air_relative_humidity_for_humidity_ratio_equation": {
                    "field_name": "Maximum Process Inlet Air Relative Humidity for Humidity Ratio Equation",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "nominal_air_flow_rate",
                "nominal_air_face_velocity",
                "nominal_electric_power",
                "temperature_equation_coefficient_1",
                "temperature_equation_coefficient_2",
                "temperature_equation_coefficient_3",
                "temperature_equation_coefficient_4",
                "temperature_equation_coefficient_5",
                "temperature_equation_coefficient_6",
                "temperature_equation_coefficient_7",
                "temperature_equation_coefficient_8",
                "minimum_regeneration_inlet_air_humidity_ratio_for_temperature_equation",
                "maximum_regeneration_inlet_air_humidity_ratio_for_temperature_equation",
                "minimum_regeneration_inlet_air_temperature_for_temperature_equation",
                "maximum_regeneration_inlet_air_temperature_for_temperature_equation",
                "minimum_process_inlet_air_humidity_ratio_for_temperature_equation",
                "maximum_process_inlet_air_humidity_ratio_for_temperature_equation",
                "minimum_process_inlet_air_temperature_for_temperature_equation",
                "maximum_process_inlet_air_temperature_for_temperature_equation",
                "minimum_regeneration_air_velocity_for_temperature_equation",
                "maximum_regeneration_air_velocity_for_temperature_equation",
                "minimum_regeneration_outlet_air_temperature_for_temperature_equation",
                "maximum_regeneration_outlet_air_temperature_for_temperature_equation",
                "minimum_regeneration_inlet_air_relative_humidity_for_temperature_equation",
                "maximum_regeneration_inlet_air_relative_humidity_for_temperature_equation",
                "minimum_process_inlet_air_relative_humidity_for_temperature_equation",
                "maximum_process_inlet_air_relative_humidity_for_temperature_equation",
                "humidity_ratio_equation_coefficient_1",
                "humidity_ratio_equation_coefficient_2",
                "humidity_ratio_equation_coefficient_3",
                "humidity_ratio_equation_coefficient_4",
                "humidity_ratio_equation_coefficient_5",
                "humidity_ratio_equation_coefficient_6",
                "humidity_ratio_equation_coefficient_7",
                "humidity_ratio_equation_coefficient_8",
                "minimum_regeneration_inlet_air_humidity_ratio_for_humidity_ratio_equation",
                "maximum_regeneration_inlet_air_humidity_ratio_for_humidity_ratio_equation",
                "minimum_regeneration_inlet_air_temperature_for_humidity_ratio_equation",
                "maximum_regeneration_inlet_air_temperature_for_humidity_ratio_equation",
                "minimum_process_inlet_air_humidity_ratio_for_humidity_ratio_equation",
                "maximum_process_inlet_air_humidity_ratio_for_humidity_ratio_equation",
                "minimum_process_inlet_air_temperature_for_humidity_ratio_equation",
                "maximum_process_inlet_air_temperature_for_humidity_ratio_equation",
                "minimum_regeneration_air_velocity_for_humidity_ratio_equation",
                "maximum_regeneration_air_velocity_for_humidity_ratio_equation",
                "minimum_regeneration_outlet_air_humidity_ratio_for_humidity_ratio_equation",
                "maximum_regeneration_outlet_air_humidity_ratio_for_humidity_ratio_equation",
                "minimum_regeneration_inlet_air_relative_humidity_for_humidity_ratio_equation",
                "maximum_regeneration_inlet_air_relative_humidity_for_humidity_ratio_equation",
                "minimum_process_inlet_air_relative_humidity_for_humidity_ratio_equation",
                "maximum_process_inlet_air_relative_humidity_for_humidity_ratio_equation"
            ],
            "alphas": {
                "fields": [
                    "name"
                ]
            },
            "numerics": {
                "fields": [
                    "nominal_air_flow_rate",
                    "nominal_air_face_velocity",
                    "nominal_electric_power",
                    "temperature_equation_coefficient_1",
                    "temperature_equation_coefficient_2",
                    "temperature_equation_coefficient_3",
                    "temperature_equation_coefficient_4",
                    "temperature_equation_coefficient_5",
                    "temperature_equation_coefficient_6",
                    "temperature_equation_coefficient_7",
                    "temperature_equation_coefficient_8",
                    "minimum_regeneration_inlet_air_humidity_ratio_for_temperature_equation",
                    "maximum_regeneration_inlet_air_humidity_ratio_for_temperature_equation",
                    "minimum_regeneration_inlet_air_temperature_for_temperature_equation",
                    "maximum_regeneration_inlet_air_temperature_for_temperature_equation",
                    "minimum_process_inlet_air_humidity_ratio_for_temperature_equation",
                    "maximum_process_inlet_air_humidity_ratio_for_temperature_equation",
                    "minimum_process_inlet_air_temperature_for_temperature_equation",
                    "maximum_process_inlet_air_temperature_for_temperature_equation",
                    "minimum_regeneration_air_velocity_for_temperature_equation",
                    "maximum_regeneration_air_velocity_for_temperature_equation",
                    "minimum_regeneration_outlet_air_temperature_for_temperature_equation",
                    "maximum_regeneration_outlet_air_temperature_for_temperature_equation",
                    "minimum_regeneration_inlet_air_relative_humidity_for_temperature_equation",
                    "maximum_regeneration_inlet_air_relative_humidity_for_temperature_equation",
                    "minimum_process_inlet_air_relative_humidity_for_temperature_equation",
                    "maximum_process_inlet_air_relative_humidity_for_temperature_equation",
                    "humidity_ratio_equation_coefficient_1",
                    "humidity_ratio_equation_coefficient_2",
                    "humidity_ratio_equation_coefficient_3",
                    "humidity_ratio_equation_coefficient_4",
                    "humidity_ratio_equation_coefficient_5",
                    "humidity_ratio_equation_coefficient_6",
                    "humidity_ratio_equation_coefficient_7",
                    "humidity_ratio_equation_coefficient_8",
                    "minimum_regeneration_inlet_air_humidity_ratio_for_humidity_ratio_equation",
                    "maximum_regeneration_inlet_air_humidity_ratio_for_humidity_ratio_equation",
                    "minimum_regeneration_inlet_air_temperature_for_humidity_ratio_equation",
                    "maximum_regeneration_inlet_air_temperature_for_humidity_ratio_equation",
                    "minimum_process_inlet_air_humidity_ratio_for_humidity_ratio_equation",
                    "maximum_process_inlet_air_humidity_ratio_for_humidity_ratio_equation",
                    "minimum_process_inlet_air_temperature_for_humidity_ratio_equation",
                    "maximum_process_inlet_air_temperature_for_humidity_ratio_equation",
                    "minimum_regeneration_air_velocity_for_humidity_ratio_equation",
                    "maximum_regeneration_air_velocity_for_humidity_ratio_equation",
                    "minimum_regeneration_outlet_air_humidity_ratio_for_humidity_ratio_equation",
                    "maximum_regeneration_outlet_air_humidity_ratio_for_humidity_ratio_equation",
                    "minimum_regeneration_inlet_air_relative_humidity_for_humidity_ratio_equation",
                    "maximum_regeneration_inlet_air_relative_humidity_for_humidity_ratio_equation",
                    "minimum_process_inlet_air_relative_humidity_for_humidity_ratio_equation",
                    "maximum_process_inlet_air_relative_humidity_for_humidity_ratio_equation"
                ]
            }
        },
        "type": "object",
        "memo": "RTO = B1 + B2*RWI + B3*RTI + B4*(RWI/RTI) + B5*PWI + B6*PTI + B7*(PWI/PTI) + B8*RFV RWO = C1 + C2*RWI + C3*RTI + C4*(RWI/RTI) + C5*PWI + C6*PTI + C7*(PWI/PTI) + C8*RFV where, RTO = Dry-bulb temperature of the regeneration outlet air (C) RWO = Humidity ratio of the regeneration outlet air (kgWater/kgDryAir) RWI = Humidity ratio of the regeneration inlet air (kgWater/kgDryAir) RTI = Dry-bulb temperature of the regeneration inlet air (C) PWI = Humidity ratio of the process inlet air (kgWater/kgDryAir) PTI = Dry-bulb temperature of the process inlet air (C) RFV = Regeneration Face Velocity (m/s)",
        "min_fields": 52.0
    }
}
```
