```
{
    "Sizing:Plant": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "plant_or_condenser_loop_name": {
                        "type": "string",
                        "note": "Enter the name of a PlantLoop or a CondenserLoop object",
                        "data_type": "object_list",
                        "object_list": [
                            "PlantLoops"
                        ]
                    },
                    "loop_type": {
                        "type": "string",
                        "enum": [
                            "Condenser",
                            "Cooling",
                            "Heating",
                            "Steam"
                        ]
                    },
                    "design_loop_exit_temperature": {
                        "type": "number",
                        "units": "C"
                    },
                    "loop_design_temperature_difference": {
                        "type": "number",
                        "units": "deltaC",
                        "exclusiveMinimum": 0.0
                    },
                    "sizing_option": {
                        "type": "string",
                        "note": "if Coincident is chosen, then sizing is based on HVAC Sizing Simulations and the input field called Do HVAC Sizing Simulation for Sizing Periods in SimulationControl must be set to Yes",
                        "enum": [
                            "",
                            "Coincident",
                            "NonCoincident"
                        ],
                        "default": "NonCoincident"
                    },
                    "zone_timesteps_in_averaging_window": {
                        "type": "number",
                        "note": "this is used in the coincident sizing algorithm to apply a running average to peak flow rates that occur during HVAC Sizing Simulations",
                        "minimum": 1.0,
                        "default": 1.0
                    },
                    "coincident_sizing_factor_mode": {
                        "type": "string",
                        "note": "this is used to adjust the result for coincident sizing by applying a sizing factor",
                        "enum": [
                            "GlobalCoolingSizingFactor",
                            "GlobalHeatingSizingFactor",
                            "LoopComponentSizingFactor",
                            "None"
                        ]
                    }
                },
                "required": [
                    "plant_or_condenser_loop_name",
                    "loop_type",
                    "design_loop_exit_temperature",
                    "loop_design_temperature_difference"
                ]
            }
        },
        "group": "HVAC Design Objects",
        "legacy_idd": {
            "field_info": {
                "plant_or_condenser_loop_name": {
                    "field_name": "Plant or Condenser Loop Name",
                    "field_type": "a"
                },
                "loop_type": {
                    "field_name": "Loop Type",
                    "field_type": "a"
                },
                "design_loop_exit_temperature": {
                    "field_name": "Design Loop Exit Temperature",
                    "field_type": "n"
                },
                "loop_design_temperature_difference": {
                    "field_name": "Loop Design Temperature Difference",
                    "field_type": "n"
                },
                "sizing_option": {
                    "field_name": "Sizing Option",
                    "field_type": "a"
                },
                "zone_timesteps_in_averaging_window": {
                    "field_name": "Zone Timesteps in Averaging Window",
                    "field_type": "n"
                },
                "coincident_sizing_factor_mode": {
                    "field_name": "Coincident Sizing Factor Mode",
                    "field_type": "a"
                }
            },
            "fields": [
                "plant_or_condenser_loop_name",
                "loop_type",
                "design_loop_exit_temperature",
                "loop_design_temperature_difference",
                "sizing_option",
                "zone_timesteps_in_averaging_window",
                "coincident_sizing_factor_mode"
            ],
            "alphas": {
                "fields": [
                    "plant_or_condenser_loop_name",
                    "loop_type",
                    "sizing_option",
                    "coincident_sizing_factor_mode"
                ]
            },
            "numerics": {
                "fields": [
                    "design_loop_exit_temperature",
                    "loop_design_temperature_difference",
                    "zone_timesteps_in_averaging_window"
                ]
            }
        },
        "type": "object",
        "memo": "Specifies the input needed to autosize plant loop flow rates and equipment capacities. This information is initially used by components that use water for heating or cooling such as hot or chilled water coils to calculate their maximum water flow rates. These flow rates are then summed for use in calculating the Plant Loop flow rates.",
        "min_fields": 4.0
    }
}
```
