```
{
    "GroundHeatTransfer:Basement:Interior": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "cond_flag_is_the_basement_conditioned_": {
                        "type": "string",
                        "enum": [
                            "",
                            "FALSE",
                            "TRUE"
                        ],
                        "default": "TRUE",
                        "note": "for EnergyPlus this should be TRUE"
                    },
                    "hin_downward_convection_only_heat_transfer_coefficient": {
                        "type": "number",
                        "units": "W/m2-K",
                        "exclusiveMinimum": 0.0,
                        "default": 0.92
                    },
                    "hin_upward_convection_only_heat_transfer_coefficient": {
                        "type": "number",
                        "units": "W/m2-K",
                        "exclusiveMinimum": 0.0,
                        "default": 4.04
                    },
                    "hin_horizontal_convection_only_heat_transfer_coefficient": {
                        "type": "number",
                        "units": "W/m2-K",
                        "exclusiveMinimum": 0.0,
                        "default": 3.08
                    },
                    "hin_downward_combined_convection_and_radiation_heat_transfer_coefficient": {
                        "type": "number",
                        "units": "W/m2-K",
                        "exclusiveMinimum": 0.0,
                        "default": 6.13
                    },
                    "hin_upward_combined_convection_and_radiation_heat_transfer_coefficient": {
                        "type": "number",
                        "units": "W/m2-K",
                        "exclusiveMinimum": 0.0,
                        "default": 9.26
                    },
                    "hin_horizontal_combined_convection_and_radiation_heat_transfer_coefficient": {
                        "type": "number",
                        "units": "W/m2-K",
                        "exclusiveMinimum": 0.0,
                        "default": 8.29
                    }
                }
            }
        },
        "group": "Detailed Ground Heat Transfer",
        "legacy_idd": {
            "field_info": {
                "cond_flag_is_the_basement_conditioned_": {
                    "field_name": "COND: Flag: Is the basement conditioned?",
                    "field_type": "a"
                },
                "hin_downward_convection_only_heat_transfer_coefficient": {
                    "field_name": "HIN: Downward convection only heat transfer coefficient",
                    "field_type": "n"
                },
                "hin_upward_convection_only_heat_transfer_coefficient": {
                    "field_name": "HIN: Upward convection only heat transfer coefficient",
                    "field_type": "n"
                },
                "hin_horizontal_convection_only_heat_transfer_coefficient": {
                    "field_name": "HIN: Horizontal convection only heat transfer coefficient",
                    "field_type": "n"
                },
                "hin_downward_combined_convection_and_radiation_heat_transfer_coefficient": {
                    "field_name": "HIN: Downward combined (convection and radiation) heat transfer coefficient",
                    "field_type": "n"
                },
                "hin_upward_combined_convection_and_radiation_heat_transfer_coefficient": {
                    "field_name": "HIN: Upward combined (convection and radiation) heat transfer coefficient",
                    "field_type": "n"
                },
                "hin_horizontal_combined_convection_and_radiation_heat_transfer_coefficient": {
                    "field_name": "HIN: Horizontal combined (convection and radiation) heat transfer coefficient",
                    "field_type": "n"
                }
            },
            "fields": [
                "cond_flag_is_the_basement_conditioned_",
                "hin_downward_convection_only_heat_transfer_coefficient",
                "hin_upward_convection_only_heat_transfer_coefficient",
                "hin_horizontal_convection_only_heat_transfer_coefficient",
                "hin_downward_combined_convection_and_radiation_heat_transfer_coefficient",
                "hin_upward_combined_convection_and_radiation_heat_transfer_coefficient",
                "hin_horizontal_combined_convection_and_radiation_heat_transfer_coefficient"
            ],
            "alphas": {
                "fields": [
                    "cond_flag_is_the_basement_conditioned_"
                ]
            },
            "numerics": {
                "fields": [
                    "hin_downward_convection_only_heat_transfer_coefficient",
                    "hin_upward_convection_only_heat_transfer_coefficient",
                    "hin_horizontal_convection_only_heat_transfer_coefficient",
                    "hin_downward_combined_convection_and_radiation_heat_transfer_coefficient",
                    "hin_upward_combined_convection_and_radiation_heat_transfer_coefficient",
                    "hin_horizontal_combined_convection_and_radiation_heat_transfer_coefficient"
                ]
            }
        },
        "type": "object",
        "memo": "Provides the information needed to simulate the inside boundary conditions for the Basement preprocessor ground heat transfer simulation.",
        "min_fields": 7.0
    }
}
```
