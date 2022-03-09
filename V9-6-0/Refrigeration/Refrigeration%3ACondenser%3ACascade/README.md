```
{
    "Refrigeration:Condenser:Cascade": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "rated_condensing_temperature": {
                        "type": "number",
                        "note": "This is the condensing temperature for the lower temperature secondary loop",
                        "units": "C"
                    },
                    "rated_approach_temperature_difference": {
                        "type": "number",
                        "note": "This is the difference between the condensing and evaporating temperatures",
                        "default": 3.0,
                        "exclusiveMinimum": 0.0,
                        "units": "deltaC"
                    },
                    "rated_effective_total_heat_rejection_rate": {
                        "type": "number",
                        "note": "used for identification and rough system size error checking",
                        "exclusiveMinimum": 0.0,
                        "units": "W"
                    },
                    "condensing_temperature_control_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Fixed",
                            "Float"
                        ],
                        "default": "Fixed",
                        "note": "Fixed keeps condensing temperature constant Float sets the condensing temperature according to the other loads on the higher temperature system"
                    },
                    "condenser_refrigerant_operating_charge_inventory": {
                        "type": "number",
                        "units": "kg",
                        "note": "optional input"
                    },
                    "condensate_receiver_refrigerant_inventory": {
                        "type": "number",
                        "units": "kg",
                        "note": "optional input"
                    },
                    "condensate_piping_refrigerant_inventory": {
                        "type": "number",
                        "units": "kg",
                        "note": "optional input"
                    }
                },
                "required": [
                    "rated_condensing_temperature",
                    "rated_effective_total_heat_rejection_rate"
                ]
            }
        },
        "group": "Refrigeration",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "RefrigerationAllTypesCondenserNames",
                "RefrigerationCascadeCondenserAndSecondarySystemNames",
                "RefrigerationSecondarySystemAndCascadeCondenserAndTransferLoadListNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "rated_condensing_temperature": {
                    "field_name": "Rated Condensing Temperature",
                    "field_type": "n"
                },
                "rated_approach_temperature_difference": {
                    "field_name": "Rated Approach Temperature Difference",
                    "field_type": "n"
                },
                "rated_effective_total_heat_rejection_rate": {
                    "field_name": "Rated Effective Total Heat Rejection Rate",
                    "field_type": "n"
                },
                "condensing_temperature_control_type": {
                    "field_name": "Condensing Temperature Control Type",
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
                "rated_condensing_temperature",
                "rated_approach_temperature_difference",
                "rated_effective_total_heat_rejection_rate",
                "condensing_temperature_control_type",
                "condenser_refrigerant_operating_charge_inventory",
                "condensate_receiver_refrigerant_inventory",
                "condensate_piping_refrigerant_inventory"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "condensing_temperature_control_type"
                ]
            },
            "numerics": {
                "fields": [
                    "rated_condensing_temperature",
                    "rated_approach_temperature_difference",
                    "rated_effective_total_heat_rejection_rate",
                    "condenser_refrigerant_operating_charge_inventory",
                    "condensate_receiver_refrigerant_inventory",
                    "condensate_piping_refrigerant_inventory"
                ]
            }
        },
        "type": "object",
        "memo": "Cascade condenser for a refrigeration system (Refrigeration:System). The cascade condenser is unlike the other condenser options because it rejects heat to another, higher-temperature, refrigeration system. That is, the cascade condenser acts as a heat rejection object for one system, but acts as a refrigeration load for another system."
    }
}
```
