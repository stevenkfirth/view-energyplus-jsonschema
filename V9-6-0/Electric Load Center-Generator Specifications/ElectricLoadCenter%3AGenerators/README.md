```
{
    "ElectricLoadCenter:Generators": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "generator_outputs": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "generator_name": {
                                    "type": "string",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "GeneratorNames"
                                    ]
                                },
                                "generator_object_type": {
                                    "type": "string",
                                    "enum": [
                                        "Generator:CombustionTurbine",
                                        "Generator:FuelCell",
                                        "Generator:InternalCombustionEngine",
                                        "Generator:MicroCHP",
                                        "Generator:MicroTurbine",
                                        "Generator:PVWatts",
                                        "Generator:Photovoltaic",
                                        "Generator:WindTurbine"
                                    ]
                                },
                                "generator_rated_electric_power_output": {
                                    "type": "number",
                                    "units": "W"
                                },
                                "generator_availability_schedule_name": {
                                    "type": "string",
                                    "note": "Availability schedule name for this generator. Schedule value > 0 means the generator is available. If this field is blank, the generator is always available.",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "ScheduleNames"
                                    ]
                                },
                                "generator_rated_thermal_to_electrical_power_ratio": {
                                    "type": "number",
                                    "note": "Required field when generator is used by an ElectricLoadCenter:Distribution object with Generator Operation Scheme set to FollowThermal or FollowThermalLimitElectrical"
                                }
                            },
                            "type": "object",
                            "required": [
                                "generator_name",
                                "generator_object_type"
                            ]
                        }
                    }
                }
            }
        },
        "group": "Electric Load Center-Generator Specifications",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "GeneratorLists"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "generator_name": {
                    "field_name": "Generator Name",
                    "field_type": "a"
                },
                "generator_object_type": {
                    "field_name": "Generator Object Type",
                    "field_type": "a"
                },
                "generator_rated_electric_power_output": {
                    "field_name": "Generator Rated Electric Power Output",
                    "field_type": "n"
                },
                "generator_availability_schedule_name": {
                    "field_name": "Generator Availability Schedule Name",
                    "field_type": "a"
                },
                "generator_rated_thermal_to_electrical_power_ratio": {
                    "field_name": "Generator Rated Thermal to Electrical Power Ratio",
                    "field_type": "n"
                }
            },
            "fields": [
                "name"
            ],
            "alphas": {
                "fields": [
                    "name"
                ],
                "extensions": [
                    "generator_name",
                    "generator_object_type",
                    "generator_availability_schedule_name"
                ]
            },
            "numerics": {
                "fields": [],
                "extensions": [
                    "generator_rated_electric_power_output",
                    "generator_rated_thermal_to_electrical_power_ratio"
                ]
            },
            "extensibles": [
                "generator_name",
                "generator_object_type",
                "generator_rated_electric_power_output",
                "generator_availability_schedule_name",
                "generator_rated_thermal_to_electrical_power_ratio"
            ],
            "extension": "generator_outputs"
        },
        "type": "object",
        "memo": "List of electric power generators to include in the simulation including the name and type of each generators along with availability schedule, rated power output, and thermal-to-electrical power ratio.",
        "min_fields": 6.0,
        "extensible_size": 5.0
    }
}
```
