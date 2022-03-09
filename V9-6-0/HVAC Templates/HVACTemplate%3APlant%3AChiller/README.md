```
{
    "HVACTemplate:Plant:Chiller": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "chiller_type": {
                        "type": "string",
                        "enum": [
                            "DistrictChilledWater",
                            "ElectricCentrifugalChiller",
                            "ElectricReciprocatingChiller",
                            "ElectricScrewChiller"
                        ]
                    },
                    "capacity": {
                        "default": "Autosize",
                        "units": "W",
                        "anyOf": [
                            {
                                "type": "number",
                                "exclusiveMinimum": 0.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "",
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "nominal_cop": {
                        "type": "number",
                        "note": "Not applicable if Chiller Type is DistrictChilledWater Electric Reciprocating Chiller",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0
                    },
                    "condenser_type": {
                        "type": "string",
                        "note": "Not applicable if Chiller Type is DistrictChilledWater",
                        "enum": [
                            "",
                            "AirCooled",
                            "EvaporativelyCooled",
                            "WaterCooled"
                        ],
                        "default": "WaterCooled"
                    },
                    "priority": {
                        "type": "string",
                        "note": "If Chiller Plant Operation Scheme Type=Default in HVACTemplate:Plant:ChilledWaterLoop, then equipment operates in Priority order, 1, 2, 3, etc."
                    },
                    "sizing_factor": {
                        "type": "number",
                        "note": "Multiplies the autosized capacity and flow rates",
                        "exclusiveMinimum": 0.0,
                        "default": 1.0
                    },
                    "minimum_part_load_ratio": {
                        "type": "number",
                        "note": "Part load ratio below which the chiller starts cycling on/off to meet the load. Must be less than or equal to Maximum Part Load Ratio.",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "maximum_part_load_ratio": {
                        "type": "number",
                        "note": "Maximum allowable part load ratio. Must be greater than or equal to Minimum Part Load Ratio.",
                        "exclusiveMinimum": 0.0,
                        "default": 1.0
                    },
                    "optimum_part_load_ratio": {
                        "type": "number",
                        "note": "Optimum part load ratio where the chiller is most efficient. Must be greater than or equal to the Minimum Part Load Ratio and less than or equal to the Maximum Part Load Ratio.",
                        "exclusiveMinimum": 0.0,
                        "default": 1.0
                    },
                    "minimum_unloading_ratio": {
                        "type": "number",
                        "note": "Part load ratio where the chiller can no longer unload and false loading begins. Minimum unloading ratio must be greater than or equal to the Minimum Part Load Ratio and less than or equal to the Maximum Part Load Ratio.",
                        "minimum": 0.0,
                        "default": 0.25
                    },
                    "leaving_chilled_water_lower_temperature_limit": {
                        "type": "number",
                        "default": 5.0,
                        "units": "C"
                    }
                },
                "required": [
                    "chiller_type",
                    "nominal_cop"
                ]
            }
        },
        "group": "HVAC Templates",
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
                "chiller_type": {
                    "field_name": "Chiller Type",
                    "field_type": "a"
                },
                "capacity": {
                    "field_name": "Capacity",
                    "field_type": "n"
                },
                "nominal_cop": {
                    "field_name": "Nominal COP",
                    "field_type": "n"
                },
                "condenser_type": {
                    "field_name": "Condenser Type",
                    "field_type": "a"
                },
                "priority": {
                    "field_name": "Priority",
                    "field_type": "a"
                },
                "sizing_factor": {
                    "field_name": "Sizing Factor",
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
                "minimum_unloading_ratio": {
                    "field_name": "Minimum Unloading Ratio",
                    "field_type": "n"
                },
                "leaving_chilled_water_lower_temperature_limit": {
                    "field_name": "Leaving Chilled Water Lower Temperature Limit",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "chiller_type",
                "capacity",
                "nominal_cop",
                "condenser_type",
                "priority",
                "sizing_factor",
                "minimum_part_load_ratio",
                "maximum_part_load_ratio",
                "optimum_part_load_ratio",
                "minimum_unloading_ratio",
                "leaving_chilled_water_lower_temperature_limit"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "chiller_type",
                    "condenser_type",
                    "priority"
                ]
            },
            "numerics": {
                "fields": [
                    "capacity",
                    "nominal_cop",
                    "sizing_factor",
                    "minimum_part_load_ratio",
                    "maximum_part_load_ratio",
                    "optimum_part_load_ratio",
                    "minimum_unloading_ratio",
                    "leaving_chilled_water_lower_temperature_limit"
                ]
            }
        },
        "type": "object",
        "memo": "This object adds a chiller to an HVACTemplate:Plant:ChilledWaterLoop.",
        "min_fields": 7.0
    }
}
```
