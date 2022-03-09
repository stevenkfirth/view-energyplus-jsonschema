```
{
    "Generator:InternalCombustionEngine": {
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
                    "shaft_power_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "curve = a + b*PLR + c*PLR**2 PLR = Ratio of Generator Load to Rated Power Output"
                    },
                    "jacket_heat_recovery_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "curve = a + b*PLR + c*PLR**2 PLR = Ratio of Generator Load to Rated Power Output"
                    },
                    "lube_heat_recovery_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "curve = a + b*PLR + c*PLR**2 PLR = Ratio of Generator Load to Rated Power Output"
                    },
                    "total_exhaust_energy_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "curve = a + b*PLR + c*PLR**2 PLR = Ratio of Generator Load to Rated Power Output"
                    },
                    "exhaust_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "curve = a + b*PLR + c*PLR**2 PLR = Ratio of Generator Load to Rated Power Output"
                    },
                    "coefficient_1_of_u_factor_times_area_curve": {
                        "type": "number",
                        "note": "curve = C1 * Generator Rated Power Output**C2"
                    },
                    "coefficient_2_of_u_factor_times_area_curve": {
                        "type": "number",
                        "note": "curve = C1 * Generator Rated Power Output**C2 typical value .9",
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
                            "Diesel",
                            "FuelOilNo1",
                            "FuelOilNo2",
                            "Gasoline",
                            "NaturalGas",
                            "OtherFuel1",
                            "OtherFuel2",
                            "Propane"
                        ],
                        "default": "Diesel"
                    },
                    "heat_recovery_maximum_temperature": {
                        "type": "number",
                        "units": "C",
                        "maximum": 100.0,
                        "minimum": 0.0,
                        "default": 80.0
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
                "shaft_power_curve_name": {
                    "field_name": "Shaft Power Curve Name",
                    "field_type": "a"
                },
                "jacket_heat_recovery_curve_name": {
                    "field_name": "Jacket Heat Recovery Curve Name",
                    "field_type": "a"
                },
                "lube_heat_recovery_curve_name": {
                    "field_name": "Lube Heat Recovery Curve Name",
                    "field_type": "a"
                },
                "total_exhaust_energy_curve_name": {
                    "field_name": "Total Exhaust Energy Curve Name",
                    "field_type": "a"
                },
                "exhaust_temperature_curve_name": {
                    "field_name": "Exhaust Temperature Curve Name",
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
                }
            },
            "fields": [
                "name",
                "rated_power_output",
                "electric_circuit_node_name",
                "minimum_part_load_ratio",
                "maximum_part_load_ratio",
                "optimum_part_load_ratio",
                "shaft_power_curve_name",
                "jacket_heat_recovery_curve_name",
                "lube_heat_recovery_curve_name",
                "total_exhaust_energy_curve_name",
                "exhaust_temperature_curve_name",
                "coefficient_1_of_u_factor_times_area_curve",
                "coefficient_2_of_u_factor_times_area_curve",
                "maximum_exhaust_flow_per_unit_of_power_output",
                "design_minimum_exhaust_temperature",
                "fuel_higher_heating_value",
                "design_heat_recovery_water_flow_rate",
                "heat_recovery_inlet_node_name",
                "heat_recovery_outlet_node_name",
                "fuel_type",
                "heat_recovery_maximum_temperature"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "electric_circuit_node_name",
                    "shaft_power_curve_name",
                    "jacket_heat_recovery_curve_name",
                    "lube_heat_recovery_curve_name",
                    "total_exhaust_energy_curve_name",
                    "exhaust_temperature_curve_name",
                    "heat_recovery_inlet_node_name",
                    "heat_recovery_outlet_node_name",
                    "fuel_type"
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
                    "fuel_higher_heating_value",
                    "design_heat_recovery_water_flow_rate",
                    "heat_recovery_maximum_temperature"
                ]
            }
        },
        "type": "object",
        "memo": "This generator model is the empirical model from the Building Loads and System Thermodynamics (BLAST) program. Engine performance curves are generated by fitting catalog data to second order polynomial equations. Three sets of coefficients are required.",
        "min_fields": 20.0
    }
}
```
