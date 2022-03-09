```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "fuel_type": {
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
                "maximum_operating_pressure": {
                    "type": "number",
                    "units": "Pa",
                    "default": 160000.0
                },
                "theoretical_efficiency": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.8
                },
                "design_outlet_steam_temperature": {
                    "type": "number",
                    "units": "C",
                    "default": 100.0
                },
                "nominal_capacity": {
                    "units": "W",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "minimum_part_load_ratio": {
                    "type": "number",
                    "minimum": 0.0
                },
                "maximum_part_load_ratio": {
                    "type": "number",
                    "minimum": 0.0
                },
                "optimum_part_load_ratio": {
                    "type": "number",
                    "minimum": 0.0
                },
                "coefficient_1_of_fuel_use_function_of_part_load_ratio_curve": {
                    "type": "number"
                },
                "coefficient_2_of_fuel_use_function_of_part_load_ratio_curve": {
                    "type": "number"
                },
                "coefficient_3_of_fuel_use_function_of_part_load_ratio_curve": {
                    "type": "number"
                },
                "water_inlet_node_name": {
                    "type": "string"
                },
                "steam_outlet_node_name": {
                    "type": "string"
                },
                "sizing_factor": {
                    "type": "number",
                    "note": "Multiplies the autosized capacity and flow rates",
                    "exclusiveMinimum": 0.0,
                    "default": 1.0
                },
                "end_use_subcategory": {
                    "type": "string",
                    "note": "Any text may be used here to categorize the end-uses in the ABUPS End Uses by Subcategory table.",
                    "retaincase": true,
                    "default": "General"
                }
            },
            "required": [
                "fuel_type"
            ]
        }
    },
    "group": "Plant Heating and Cooling Equipment",
    "name": {
        "type": "string",
        "is_required": true,
        "reference-class-name": [
            "validBranchEquipmentTypes",
            "validPlantEquipmentTypes"
        ],
        "reference": [
            "validBranchEquipmentNames",
            "validPlantEquipmentNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "fuel_type": {
                "field_name": "Fuel Type",
                "field_type": "a"
            },
            "maximum_operating_pressure": {
                "field_name": "Maximum Operating Pressure",
                "field_type": "n"
            },
            "theoretical_efficiency": {
                "field_name": "Theoretical Efficiency",
                "field_type": "n"
            },
            "design_outlet_steam_temperature": {
                "field_name": "Design Outlet Steam Temperature",
                "field_type": "n"
            },
            "nominal_capacity": {
                "field_name": "Nominal Capacity",
                "field_type": "n"
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
            "coefficient_1_of_fuel_use_function_of_part_load_ratio_curve": {
                "field_name": "Coefficient 1 of Fuel Use Function of Part Load Ratio Curve",
                "field_type": "n"
            },
            "coefficient_2_of_fuel_use_function_of_part_load_ratio_curve": {
                "field_name": "Coefficient 2 of Fuel Use Function of Part Load Ratio Curve",
                "field_type": "n"
            },
            "coefficient_3_of_fuel_use_function_of_part_load_ratio_curve": {
                "field_name": "Coefficient 3 of Fuel Use Function of Part Load Ratio Curve",
                "field_type": "n"
            },
            "water_inlet_node_name": {
                "field_name": "Water Inlet Node Name",
                "field_type": "a"
            },
            "steam_outlet_node_name": {
                "field_name": "Steam Outlet Node Name",
                "field_type": "a"
            },
            "sizing_factor": {
                "field_name": "Sizing Factor",
                "field_type": "n"
            },
            "end_use_subcategory": {
                "field_name": "End-Use Subcategory",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "fuel_type",
            "maximum_operating_pressure",
            "theoretical_efficiency",
            "design_outlet_steam_temperature",
            "nominal_capacity",
            "minimum_part_load_ratio",
            "maximum_part_load_ratio",
            "optimum_part_load_ratio",
            "coefficient_1_of_fuel_use_function_of_part_load_ratio_curve",
            "coefficient_2_of_fuel_use_function_of_part_load_ratio_curve",
            "coefficient_3_of_fuel_use_function_of_part_load_ratio_curve",
            "water_inlet_node_name",
            "steam_outlet_node_name",
            "sizing_factor",
            "end_use_subcategory"
        ],
        "alphas": {
            "fields": [
                "name",
                "fuel_type",
                "water_inlet_node_name",
                "steam_outlet_node_name",
                "end_use_subcategory"
            ]
        },
        "numerics": {
            "fields": [
                "maximum_operating_pressure",
                "theoretical_efficiency",
                "design_outlet_steam_temperature",
                "nominal_capacity",
                "minimum_part_load_ratio",
                "maximum_part_load_ratio",
                "optimum_part_load_ratio",
                "coefficient_1_of_fuel_use_function_of_part_load_ratio_curve",
                "coefficient_2_of_fuel_use_function_of_part_load_ratio_curve",
                "coefficient_3_of_fuel_use_function_of_part_load_ratio_curve",
                "sizing_factor"
            ]
        }
    },
    "type": "object",
    "memo": "This boiler model is an adaptation of the empirical model from the Building Loads and System Thermodynamics (BLAST) program. Boiler performance curves are generated by fitting catalog data to third order polynomial equations. A constant efficiency boiler is modeled by setting the fuel use coefficients as follows: N9=1, N10=0, N11=0"
}
```
