```
{
    "Coil:Heating:Gas:MultiStage": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "availability_schedule_name": {
                        "type": "string",
                        "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "air_inlet_node_name": {
                        "type": "string"
                    },
                    "air_outlet_node_name": {
                        "type": "string"
                    },
                    "temperature_setpoint_node_name": {
                        "type": "string",
                        "note": "optional, used if coil is temperature control and not load-base controlled."
                    },
                    "part_load_fraction_correlation_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve, PLF = a + b*PLR + c*PLR**2 cubic curve, PLF = a + b*PLR + c*PLR**2 + d*PLR**3 PLF = part load fraction PLR = part load ratio (sensible heating load/steady state heating capacity) Coil runtime fraction = Part Load Ratio / PLF This part load degradation is for coil performance & will increase the gas consumption of the coil due to transient coil operation."
                    },
                    "parasitic_gas_load": {
                        "type": "number",
                        "units": "W",
                        "note": "parasitic gas load associated with the gas coil operation (i.e., standing pilot)"
                    },
                    "number_of_stages": {
                        "type": "number",
                        "minimum": 1.0,
                        "maximum": 4.0,
                        "note": "Enter the number of the following sets of data for coil capacity and Gas Burner Efficiency."
                    },
                    "stage_1_gas_burner_efficiency": {
                        "type": "number",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0
                    },
                    "stage_1_nominal_capacity": {
                        "units": "W",
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
                    "stage_1_parasitic_electric_load": {
                        "type": "number",
                        "units": "W",
                        "note": "Stage 1 parasitic electric load associated with the gas coil operation such as an inducer fan, etc. This will be modified by the part load ratio to reflect the time of operation in a timestep.",
                        "ip-units": "W"
                    },
                    "stage_2_gas_burner_efficiency": {
                        "type": "number",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0
                    },
                    "stage_2_nominal_capacity": {
                        "units": "W",
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
                    "stage_2_parasitic_electric_load": {
                        "type": "number",
                        "units": "W",
                        "note": "Stage 2 parasitic electric load associated with the gas coil operation such as an inducer fan, etc. This will be modified by the part load ratio to reflect the time of operation in a timestep.",
                        "ip-units": "W"
                    },
                    "stage_3_gas_burner_efficiency": {
                        "type": "number",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0
                    },
                    "stage_3_nominal_capacity": {
                        "units": "W",
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
                    "stage_3_parasitic_electric_load": {
                        "type": "number",
                        "units": "W",
                        "note": "Stage 3 parasitic electric load associated with the gas coil operation such as an inducer fan, etc. This will be modified by the part load ratio to reflect the time of operation in a timestep.",
                        "ip-units": "W"
                    },
                    "stage_4_gas_burner_efficiency": {
                        "type": "number",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0
                    },
                    "stage_4_nominal_capacity": {
                        "units": "W",
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
                    "stage_4_parasitic_electric_load": {
                        "type": "number",
                        "units": "W",
                        "note": "Stage 4 parasitic electric load associated with the gas coil operation such as an inducer fan, etc. This will be modified by the part load ratio to reflect the time of operation in a timestep.",
                        "ip-units": "W"
                    }
                },
                "required": [
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "number_of_stages",
                    "stage_1_gas_burner_efficiency",
                    "stage_1_nominal_capacity"
                ]
            }
        },
        "group": "Coils",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "HeatingCoilsGasMultiStage"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "availability_schedule_name": {
                    "field_name": "Availability Schedule Name",
                    "field_type": "a"
                },
                "air_inlet_node_name": {
                    "field_name": "Air Inlet Node Name",
                    "field_type": "a"
                },
                "air_outlet_node_name": {
                    "field_name": "Air Outlet Node Name",
                    "field_type": "a"
                },
                "temperature_setpoint_node_name": {
                    "field_name": "Temperature Setpoint Node Name",
                    "field_type": "a"
                },
                "part_load_fraction_correlation_curve_name": {
                    "field_name": "Part Load Fraction Correlation Curve Name",
                    "field_type": "a"
                },
                "parasitic_gas_load": {
                    "field_name": "Parasitic Gas Load",
                    "field_type": "n"
                },
                "number_of_stages": {
                    "field_name": "Number of Stages",
                    "field_type": "n"
                },
                "stage_1_gas_burner_efficiency": {
                    "field_name": "Stage 1 Gas Burner Efficiency",
                    "field_type": "n"
                },
                "stage_1_nominal_capacity": {
                    "field_name": "Stage 1 Nominal Capacity",
                    "field_type": "n"
                },
                "stage_1_parasitic_electric_load": {
                    "field_name": "Stage 1 Parasitic Electric Load",
                    "field_type": "n"
                },
                "stage_2_gas_burner_efficiency": {
                    "field_name": "Stage 2 Gas Burner Efficiency",
                    "field_type": "n"
                },
                "stage_2_nominal_capacity": {
                    "field_name": "Stage 2 Nominal Capacity",
                    "field_type": "n"
                },
                "stage_2_parasitic_electric_load": {
                    "field_name": "Stage 2 Parasitic Electric Load",
                    "field_type": "n"
                },
                "stage_3_gas_burner_efficiency": {
                    "field_name": "Stage 3 Gas Burner Efficiency",
                    "field_type": "n"
                },
                "stage_3_nominal_capacity": {
                    "field_name": "Stage 3 Nominal Capacity",
                    "field_type": "n"
                },
                "stage_3_parasitic_electric_load": {
                    "field_name": "Stage 3 Parasitic Electric Load",
                    "field_type": "n"
                },
                "stage_4_gas_burner_efficiency": {
                    "field_name": "Stage 4 Gas Burner Efficiency",
                    "field_type": "n"
                },
                "stage_4_nominal_capacity": {
                    "field_name": "Stage 4 Nominal Capacity",
                    "field_type": "n"
                },
                "stage_4_parasitic_electric_load": {
                    "field_name": "Stage 4 Parasitic Electric Load",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "temperature_setpoint_node_name",
                "part_load_fraction_correlation_curve_name",
                "parasitic_gas_load",
                "number_of_stages",
                "stage_1_gas_burner_efficiency",
                "stage_1_nominal_capacity",
                "stage_1_parasitic_electric_load",
                "stage_2_gas_burner_efficiency",
                "stage_2_nominal_capacity",
                "stage_2_parasitic_electric_load",
                "stage_3_gas_burner_efficiency",
                "stage_3_nominal_capacity",
                "stage_3_parasitic_electric_load",
                "stage_4_gas_burner_efficiency",
                "stage_4_nominal_capacity",
                "stage_4_parasitic_electric_load"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "temperature_setpoint_node_name",
                    "part_load_fraction_correlation_curve_name"
                ]
            },
            "numerics": {
                "fields": [
                    "parasitic_gas_load",
                    "number_of_stages",
                    "stage_1_gas_burner_efficiency",
                    "stage_1_nominal_capacity",
                    "stage_1_parasitic_electric_load",
                    "stage_2_gas_burner_efficiency",
                    "stage_2_nominal_capacity",
                    "stage_2_parasitic_electric_load",
                    "stage_3_gas_burner_efficiency",
                    "stage_3_nominal_capacity",
                    "stage_3_parasitic_electric_load",
                    "stage_4_gas_burner_efficiency",
                    "stage_4_nominal_capacity",
                    "stage_4_parasitic_electric_load"
                ]
            }
        },
        "type": "object",
        "memo": "Gas heating coil, multi-stage. If the coil is located directly in an air loop branch or outdoor air equipment list, then it is controlled on leaving air temperature and the Temperature Setpoint Node Name must be specified. If the coil is contained within another component such as an air terminal unit, zone HVAC equipment, or unitary system, then the coil is controlled by the parent component and the setpoint node name is not entered.",
        "min_fields": 8.0
    }
}
```
