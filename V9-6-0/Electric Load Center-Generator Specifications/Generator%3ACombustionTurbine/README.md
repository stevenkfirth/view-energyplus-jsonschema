```
{
    "Generator:CombustionTurbine": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "rated_power_output": {
                        "type": "number",
                        "units": "W"
                    },
                    "electric_circuit_node_name": {
                        "type": "string"
                    },
                    "minimum_part_load_ratio": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "maximum_part_load_ratio": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0
                    },
                    "optimum_part_load_ratio": {
                        "type": "number"
                    },
                    "part_load_based_fuel_input_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "curve = a + b*PLR + c*PLR**2 PLR = Ratio of Generator Load to Rated Power Output this curve is multiplied to the Temperature Based Fuel Input Curve to determine Fuel Energy In"
                    },
                    "temperature_based_fuel_input_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "curve = a + b*AT + c*AT**2 AT = Ambient Delta T this curve is multiplied to the Part Load Based Fuel Input Curve to determine Fuel Energy In"
                    },
                    "exhaust_flow_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "curve = a + b*AT + c*AT**2 AT = Ambient Delta T"
                    },
                    "part_load_based_exhaust_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "curve = a + b*PLR + c*PLR**2 PLR = Ratio of Generator Load to Rated Power Output this curve is multiplied to the Temperature Based Exhaust Temperature Curve to determine Exhaust Temperature"
                    },
                    "temperature_based_exhaust_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "curve = a + b*AT + c*AT**2 AT = Ambient Delta T this curve is multiplied to the Part Load Based Exhaust Temperature Curve to determine Exhaust Temperature"
                    },
                    "heat_recovery_lube_energy_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "curve = a + b*PLR + c*PLR**2 PLR = Ratio of Generator Load to Rated Power Output"
                    },
                    "coefficient_1_of_u_factor_times_area_curve": {
                        "type": "number",
                        "note": "curve = C1 * Rated Power Output**C2"
                    },
                    "coefficient_2_of_u_factor_times_area_curve": {
                        "type": "number",
                        "note": "curve = C1 * Rated Power Output**C2 typical value .9",
                        "maximum": 2.0
                    },
                    "maximum_exhaust_flow_per_unit_of_power_output": {
                        "type": "number",
                        "units": "(kg/s)/W"
                    },
                    "design_minimum_exhaust_temperature": {
                        "type": "number",
                        "units": "C"
                    },
                    "design_air_inlet_temperature": {
                        "type": "number",
                        "units": "C"
                    },
                    "fuel_higher_heating_value": {
                        "type": "number",
                        "units": "kJ/kg"
                    },
                    "design_heat_recovery_water_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0,
                        "default": 0.0,
                        "note": "if non-zero, then inlet, outlet nodes must be entered.",
                        "ip-units": "gal/min"
                    },
                    "heat_recovery_inlet_node_name": {
                        "type": "string"
                    },
                    "heat_recovery_outlet_node_name": {
                        "type": "string"
                    },
                    "fuel_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Coal",
                            "Diesel",
                            "FuelOilNo1",
                            "FuelOilNo2",
                            "Gasoline",
                            "NaturalGas",
                            "OtherFuel1",
                            "OtherFuel2",
                            "Propane"
                        ],
                        "default": "NaturalGas"
                    },
                    "heat_recovery_maximum_temperature": {
                        "type": "number",
                        "units": "C",
                        "maximum": 100.0,
                        "minimum": 0.0,
                        "default": 80.0
                    },
                    "outdoor_air_inlet_node_name": {
                        "type": "string",
                        "note": "Enter the name of an outdoor air node"
                    }
                }
            }
        },
        "group": "Electric Load Center-Generator Specifications",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "GeneratorNames",
                "validBranchEquipmentNames"
            ],
            "reference-class-name": [
                "validBranchEquipmentTypes"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "rated_power_output": {
                    "field_name": "Rated Power Output",
                    "field_type": "n"
                },
                "electric_circuit_node_name": {
                    "field_name": "Electric Circuit Node Name",
                    "field_type": "a"
                },
                "minimum_part_load_ratio": {
                    "field_name": "Minimum Part Load Ratio",
                    "field_type": "n"
                },
                "maximum_part_load_ratio": {
                    "field_name": "Maximum Part Load Ratio",
                    "field_type": "n"
                },
                "optimum_part_load_ratio": {
                    "field_name": "Optimum Part Load Ratio",
                    "field_type": "n"
                },
                "part_load_based_fuel_input_curve_name": {
                    "field_name": "Part Load Based Fuel Input Curve Name",
                    "field_type": "a"
                },
                "temperature_based_fuel_input_curve_name": {
                    "field_name": "Temperature Based Fuel Input Curve Name",
                    "field_type": "a"
                },
                "exhaust_flow_curve_name": {
                    "field_name": "Exhaust Flow Curve Name",
                    "field_type": "a"
                },
                "part_load_based_exhaust_temperature_curve_name": {
                    "field_name": "Part Load Based Exhaust Temperature Curve Name",
                    "field_type": "a"
                },
                "temperature_based_exhaust_temperature_curve_name": {
                    "field_name": "Temperature Based Exhaust Temperature Curve Name",
                    "field_type": "a"
                },
                "heat_recovery_lube_energy_curve_name": {
                    "field_name": "Heat Recovery Lube Energy Curve Name",
                    "field_type": "a"
                },
                "coefficient_1_of_u_factor_times_area_curve": {
                    "field_name": "Coefficient 1 of U-Factor Times Area Curve",
                    "field_type": "n"
                },
                "coefficient_2_of_u_factor_times_area_curve": {
                    "field_name": "Coefficient 2 of U-Factor Times Area Curve",
                    "field_type": "n"
                },
                "maximum_exhaust_flow_per_unit_of_power_output": {
                    "field_name": "Maximum Exhaust Flow per Unit of Power Output",
                    "field_type": "n"
                },
                "design_minimum_exhaust_temperature": {
                    "field_name": "Design Minimum Exhaust Temperature",
                    "field_type": "n"
                },
                "design_air_inlet_temperature": {
                    "field_name": "Design Air Inlet Temperature",
                    "field_type": "n"
                },
                "fuel_higher_heating_value": {
                    "field_name": "Fuel Higher Heating Value",
                    "field_type": "n"
                },
                "design_heat_recovery_water_flow_rate": {
                    "field_name": "Design Heat Recovery Water Flow Rate",
                    "field_type": "n"
                },
                "heat_recovery_inlet_node_name": {
                    "field_name": "Heat Recovery Inlet Node Name",
                    "field_type": "a"
                },
                "heat_recovery_outlet_node_name": {
                    "field_name": "Heat Recovery Outlet Node Name",
                    "field_type": "a"
                },
                "fuel_type": {
                    "field_name": "Fuel Type",
                    "field_type": "a"
                },
                "heat_recovery_maximum_temperature": {
                    "field_name": "Heat Recovery Maximum Temperature",
                    "field_type": "n"
                },
                "outdoor_air_inlet_node_name": {
                    "field_name": "Outdoor Air Inlet Node Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "rated_power_output",
                "electric_circuit_node_name",
                "minimum_part_load_ratio",
                "maximum_part_load_ratio",
                "optimum_part_load_ratio",
                "part_load_based_fuel_input_curve_name",
                "temperature_based_fuel_input_curve_name",
                "exhaust_flow_curve_name",
                "part_load_based_exhaust_temperature_curve_name",
                "temperature_based_exhaust_temperature_curve_name",
                "heat_recovery_lube_energy_curve_name",
                "coefficient_1_of_u_factor_times_area_curve",
                "coefficient_2_of_u_factor_times_area_curve",
                "maximum_exhaust_flow_per_unit_of_power_output",
                "design_minimum_exhaust_temperature",
                "design_air_inlet_temperature",
                "fuel_higher_heating_value",
                "design_heat_recovery_water_flow_rate",
                "heat_recovery_inlet_node_name",
                "heat_recovery_outlet_node_name",
                "fuel_type",
                "heat_recovery_maximum_temperature",
                "outdoor_air_inlet_node_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "electric_circuit_node_name",
                    "part_load_based_fuel_input_curve_name",
                    "temperature_based_fuel_input_curve_name",
                    "exhaust_flow_curve_name",
                    "part_load_based_exhaust_temperature_curve_name",
                    "temperature_based_exhaust_temperature_curve_name",
                    "heat_recovery_lube_energy_curve_name",
                    "heat_recovery_inlet_node_name",
                    "heat_recovery_outlet_node_name",
                    "fuel_type",
                    "outdoor_air_inlet_node_name"
                ]
            },
            "numerics": {
                "fields": [
                    "rated_power_output",
                    "minimum_part_load_ratio",
                    "maximum_part_load_ratio",
                    "optimum_part_load_ratio",
                    "coefficient_1_of_u_factor_times_area_curve",
                    "coefficient_2_of_u_factor_times_area_curve",
                    "maximum_exhaust_flow_per_unit_of_power_output",
                    "design_minimum_exhaust_temperature",
                    "design_air_inlet_temperature",
                    "fuel_higher_heating_value",
                    "design_heat_recovery_water_flow_rate",
                    "heat_recovery_maximum_temperature"
                ]
            }
        },
        "type": "object",
        "memo": "This generator model is the empirical model from the Building Loads and System Thermodynamics (BLAST) program. Generator performance curves are generated by fitting catalog data to second order polynomial equations. Three sets of coefficients are required.",
        "min_fields": 22.0
    }
}
```
