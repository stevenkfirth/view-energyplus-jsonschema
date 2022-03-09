```
{
    "Refrigeration:GasCooler:AirCooled": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "rated_total_heat_rejection_rate_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Be sure the rating corresponds to the correct refrigerant (R744) HeatRejection(W)=C1 +C2(Gas Cooler Outlet Temp - Entering Air Temp, deg C) Will be adjusted for elevation automatically"
                    },
                    "gas_cooler_fan_speed_control_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Fixed",
                            "FixedLinear",
                            "TwoSpeed",
                            "VariableSpeed"
                        ],
                        "default": "Fixed"
                    },
                    "rated_fan_power": {
                        "type": "number",
                        "note": "Power for gas cooler fan(s) corresponding to rated total heat rejection effect.",
                        "units": "W",
                        "minimum": 0.0,
                        "default": 5000.0
                    },
                    "minimum_fan_air_flow_ratio": {
                        "type": "number",
                        "note": "Minimum air flow fraction through gas cooler fan",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "default": 0.2
                    },
                    "transition_temperature": {
                        "type": "number",
                        "note": "Temperature at which system transitions between subcritical and transcritical operation.",
                        "units": "C",
                        "default": 27.0
                    },
                    "transcritical_approach_temperature": {
                        "type": "number",
                        "note": "Temperature difference between the CO2 exiting the gas cooler and the air entering the gas cooler during transcritical operation.",
                        "units": "deltaC",
                        "default": 3.0
                    },
                    "subcritical_temperature_difference": {
                        "type": "number",
                        "note": "Temperature difference between the saturated condensing temperature and the air temperature during subcritical operation.",
                        "units": "deltaC",
                        "default": 10.0
                    },
                    "minimum_condensing_temperature": {
                        "type": "number",
                        "note": "Minimum saturated condensing temperature during subcritical operation.",
                        "units": "C",
                        "default": 10.0
                    },
                    "air_inlet_node_name": {
                        "type": "string",
                        "note": "If field is left blank, then the model assumes that the inlet air conditions are the outdoor air conditions for the current timestep (e.g., no adjustment for height above ground)."
                    },
                    "end_use_subcategory": {
                        "type": "string",
                        "note": "Any text may be used here to categorize the end-uses in the ABUPS End Uses by Subcategory table.",
                        "retaincase": true,
                        "default": "General"
                    },
                    "gas_cooler_refrigerant_operating_charge_inventory": {
                        "type": "number",
                        "units": "kg",
                        "default": 0.0,
                        "note": "optional input"
                    },
                    "gas_cooler_receiver_refrigerant_inventory": {
                        "type": "number",
                        "units": "kg",
                        "default": 0.0,
                        "note": "optional input"
                    },
                    "gas_cooler_outlet_piping_refrigerant_inventory": {
                        "type": "number",
                        "units": "kg",
                        "default": 0.0,
                        "note": "optional input"
                    }
                },
                "required": [
                    "rated_total_heat_rejection_rate_curve_name"
                ]
            }
        },
        "group": "Refrigeration",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "RefrigerationAllTypesGasCoolerNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "rated_total_heat_rejection_rate_curve_name": {
                    "field_name": "Rated Total Heat Rejection Rate Curve Name",
                    "field_type": "a"
                },
                "gas_cooler_fan_speed_control_type": {
                    "field_name": "Gas Cooler Fan Speed Control Type",
                    "field_type": "a"
                },
                "rated_fan_power": {
                    "field_name": "Rated Fan Power",
                    "field_type": "n"
                },
                "minimum_fan_air_flow_ratio": {
                    "field_name": "Minimum Fan Air Flow Ratio",
                    "field_type": "n"
                },
                "transition_temperature": {
                    "field_name": "Transition Temperature",
                    "field_type": "n"
                },
                "transcritical_approach_temperature": {
                    "field_name": "Transcritical Approach Temperature",
                    "field_type": "n"
                },
                "subcritical_temperature_difference": {
                    "field_name": "Subcritical Temperature Difference",
                    "field_type": "n"
                },
                "minimum_condensing_temperature": {
                    "field_name": "Minimum Condensing Temperature",
                    "field_type": "n"
                },
                "air_inlet_node_name": {
                    "field_name": "Air Inlet Node Name",
                    "field_type": "a"
                },
                "end_use_subcategory": {
                    "field_name": "End-Use Subcategory",
                    "field_type": "a"
                },
                "gas_cooler_refrigerant_operating_charge_inventory": {
                    "field_name": "Gas Cooler Refrigerant Operating Charge Inventory",
                    "field_type": "n"
                },
                "gas_cooler_receiver_refrigerant_inventory": {
                    "field_name": "Gas Cooler Receiver Refrigerant Inventory",
                    "field_type": "n"
                },
                "gas_cooler_outlet_piping_refrigerant_inventory": {
                    "field_name": "Gas Cooler Outlet Piping Refrigerant Inventory",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "rated_total_heat_rejection_rate_curve_name",
                "gas_cooler_fan_speed_control_type",
                "rated_fan_power",
                "minimum_fan_air_flow_ratio",
                "transition_temperature",
                "transcritical_approach_temperature",
                "subcritical_temperature_difference",
                "minimum_condensing_temperature",
                "air_inlet_node_name",
                "end_use_subcategory",
                "gas_cooler_refrigerant_operating_charge_inventory",
                "gas_cooler_receiver_refrigerant_inventory",
                "gas_cooler_outlet_piping_refrigerant_inventory"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "rated_total_heat_rejection_rate_curve_name",
                    "gas_cooler_fan_speed_control_type",
                    "air_inlet_node_name",
                    "end_use_subcategory"
                ]
            },
            "numerics": {
                "fields": [
                    "rated_fan_power",
                    "minimum_fan_air_flow_ratio",
                    "transition_temperature",
                    "transcritical_approach_temperature",
                    "subcritical_temperature_difference",
                    "minimum_condensing_temperature",
                    "gas_cooler_refrigerant_operating_charge_inventory",
                    "gas_cooler_receiver_refrigerant_inventory",
                    "gas_cooler_outlet_piping_refrigerant_inventory"
                ]
            }
        },
        "type": "object",
        "memo": "The transcritical refrigeration system requires a single gas cooler to reject the system heat.",
        "min_fields": 4.0
    }
}
```
