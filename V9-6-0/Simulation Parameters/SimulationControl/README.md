```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "do_zone_sizing_calculation": {
                    "type": "string",
                    "note": "If Yes, Zone sizing is accomplished from corresponding Sizing:Zone objects and autosize fields.",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "No"
                },
                "do_system_sizing_calculation": {
                    "type": "string",
                    "note": "If Yes, System sizing is accomplished from corresponding Sizing:System objects and autosize fields. If Yes, Zone sizing (previous field) must also be Yes.",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "No"
                },
                "do_plant_sizing_calculation": {
                    "type": "string",
                    "note": "If Yes, Plant sizing is accomplished from corresponding Sizing:Plant objects and autosize fields.",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "No"
                },
                "run_simulation_for_sizing_periods": {
                    "type": "string",
                    "note": "If Yes, SizingPeriod:* objects are executed and results from those may be displayed..",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "Yes"
                },
                "run_simulation_for_weather_file_run_periods": {
                    "type": "string",
                    "note": "If Yes, RunPeriod:* objects are executed and results from those may be displayed..",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "Yes"
                },
                "do_hvac_sizing_simulation_for_sizing_periods": {
                    "type": "string",
                    "note": "If Yes, SizingPeriod:* objects are exectuted additional times for advanced sizing. Currently limited to use with coincident plant sizing, see Sizing:Plant object",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "No"
                },
                "maximum_number_of_hvac_sizing_simulation_passes": {
                    "type": "number",
                    "note": "the entire set of SizingPeriod:* objects may be repeated to fine tune size results this input sets a limit on the number of passes that the sizing algorithms can repeate the set",
                    "minimum": 1.0,
                    "default": 1.0
                }
            }
        }
    },
    "group": "Simulation Parameters",
    "legacy_idd": {
        "field_info": {
            "do_zone_sizing_calculation": {
                "field_name": "Do Zone Sizing Calculation",
                "field_type": "a"
            },
            "do_system_sizing_calculation": {
                "field_name": "Do System Sizing Calculation",
                "field_type": "a"
            },
            "do_plant_sizing_calculation": {
                "field_name": "Do Plant Sizing Calculation",
                "field_type": "a"
            },
            "run_simulation_for_sizing_periods": {
                "field_name": "Run Simulation for Sizing Periods",
                "field_type": "a"
            },
            "run_simulation_for_weather_file_run_periods": {
                "field_name": "Run Simulation for Weather File Run Periods",
                "field_type": "a"
            },
            "do_hvac_sizing_simulation_for_sizing_periods": {
                "field_name": "Do HVAC Sizing Simulation for Sizing Periods",
                "field_type": "a"
            },
            "maximum_number_of_hvac_sizing_simulation_passes": {
                "field_name": "Maximum Number of HVAC Sizing Simulation Passes",
                "field_type": "n"
            }
        },
        "fields": [
            "do_zone_sizing_calculation",
            "do_system_sizing_calculation",
            "do_plant_sizing_calculation",
            "run_simulation_for_sizing_periods",
            "run_simulation_for_weather_file_run_periods",
            "do_hvac_sizing_simulation_for_sizing_periods",
            "maximum_number_of_hvac_sizing_simulation_passes"
        ],
        "alphas": {
            "fields": [
                "do_zone_sizing_calculation",
                "do_system_sizing_calculation",
                "do_plant_sizing_calculation",
                "run_simulation_for_sizing_periods",
                "run_simulation_for_weather_file_run_periods",
                "do_hvac_sizing_simulation_for_sizing_periods"
            ]
        },
        "numerics": {
            "fields": [
                "maximum_number_of_hvac_sizing_simulation_passes"
            ]
        }
    },
    "type": "object",
    "maxProperties": 1,
    "memo": "Note that the following 3 fields are related to the Sizing:Zone, Sizing:System, and Sizing:Plant objects. Having these fields set to Yes but no corresponding Sizing object will not cause the sizing to be done. However, having any of these fields set to No, the corresponding Sizing object is ignored. Note also, if you want to do system sizing, you must also do zone sizing in the same run or an error will result.",
    "min_fields": 7.0
}
```
