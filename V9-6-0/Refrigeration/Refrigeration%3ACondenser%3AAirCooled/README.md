```
{
    "Refrigeration:Condenser:AirCooled": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "rated_effective_total_heat_rejection_rate_curve_name": {
                        "type": "string",
                        "note": "Rating as per ARI 460 Be sure the rating corresponds to the correct refrigerant HeatRejection(W)=C1 +C2(Condensing Temp - Entering Air Temp, deg C) Will be adjusted for elevation automatically",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    },
                    "rated_subcooling_temperature_difference": {
                        "type": "number",
                        "units": "deltaC",
                        "default": 0.0,
                        "minimum": 0.0,
                        "note": "must correspond to rating given for total heat rejection effect"
                    },
                    "condenser_fan_speed_control_type": {
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
                        "note": "Power for condenser fan(s) corresponding to rated total heat rejection effect.",
                        "units": "W",
                        "minimum": 0.0,
                        "default": 250.0
                    },
                    "minimum_fan_air_flow_ratio": {
                        "type": "number",
                        "note": "Minimum air flow fraction through condenser fan",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "default": 0.2
                    },
                    "air_inlet_node_name_or_zone_name": {
                        "type": "string",
                        "note": "If field is left blank, then the model assumes that the inlet air conditions are the outdoor air conditions for the current timestep (e.g., no adjustment for height above ground). If the condenser rejects heat to a conditioned zone, enter the zone name here."
                    },
                    "end_use_subcategory": {
                        "type": "string",
                        "note": "Any text may be used here to categorize the end-uses in the ABUPS End Uses by Subcategory table.",
                        "retaincase": true,
                        "default": "General"
                    },
                    "condenser_refrigerant_operating_charge_inventory": {
                        "type": "number",
                        "units": "kg",
                        "default": 0.0,
                        "note": "optional input"
                    },
                    "condensate_receiver_refrigerant_inventory": {
                        "type": "number",
                        "units": "kg",
                        "default": 0.0,
                        "note": "optional input"
                    },
                    "condensate_piping_refrigerant_inventory": {
                        "type": "number",
                        "units": "kg",
                        "default": 0.0,
                        "note": "optional input"
                    }
                }
            }
        },
        "group": "Refrigeration",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "DesuperHeatingCoilSources",
                "RefrigerationAllTypesCondenserNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "rated_effective_total_heat_rejection_rate_curve_name": {
                    "field_name": "Rated Effective Total Heat Rejection Rate Curve Name",
                    "field_type": "a"
                },
                "rated_subcooling_temperature_difference": {
                    "field_name": "Rated Subcooling Temperature Difference",
                    "field_type": "n"
                },
                "condenser_fan_speed_control_type": {
                    "field_name": "Condenser Fan Speed Control Type",
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
                "air_inlet_node_name_or_zone_name": {
                    "field_name": "Air Inlet Node Name or Zone Name",
                    "field_type": "a"
                },
                "end_use_subcategory": {
                    "field_name": "End-Use Subcategory",
                    "field_type": "a"
                },
                "condenser_refrigerant_operating_charge_inventory": {
                    "field_name": "Condenser Refrigerant Operating Charge Inventory",
                    "field_type": "n"
                },
                "condensate_receiver_refrigerant_inventory": {
                    "field_name": "Condensate Receiver Refrigerant Inventory",
                    "field_type": "n"
                },
                "condensate_piping_refrigerant_inventory": {
                    "field_name": "Condensate Piping Refrigerant Inventory",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "rated_effective_total_heat_rejection_rate_curve_name",
                "rated_subcooling_temperature_difference",
                "condenser_fan_speed_control_type",
                "rated_fan_power",
                "minimum_fan_air_flow_ratio",
                "air_inlet_node_name_or_zone_name",
                "end_use_subcategory",
                "condenser_refrigerant_operating_charge_inventory",
                "condensate_receiver_refrigerant_inventory",
                "condensate_piping_refrigerant_inventory"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "rated_effective_total_heat_rejection_rate_curve_name",
                    "condenser_fan_speed_control_type",
                    "air_inlet_node_name_or_zone_name",
                    "end_use_subcategory"
                ]
            },
            "numerics": {
                "fields": [
                    "rated_subcooling_temperature_difference",
                    "rated_fan_power",
                    "minimum_fan_air_flow_ratio",
                    "condenser_refrigerant_operating_charge_inventory",
                    "condensate_receiver_refrigerant_inventory",
                    "condensate_piping_refrigerant_inventory"
                ]
            }
        },
        "type": "object",
        "memo": "Air cooled condenser for a refrigeration system (Refrigeration:System).",
        "min_fields": 5.0
    }
}
```
