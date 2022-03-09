```
{
    "ZoneTerminalUnitList": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "zone_terminal_unit_list_name": {
                        "type": "string",
                        "reference": [
                            "ZoneTerminalUnitListNames"
                        ]
                    },
                    "terminal_units": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "zone_terminal_unit_name": {
                                    "type": "string",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "ZoneTerminalUnitNames"
                                    ]
                                }
                            },
                            "type": "object",
                            "required": [
                                "zone_terminal_unit_name"
                            ]
                        }
                    }
                },
                "required": [
                    "zone_terminal_unit_list_name"
                ]
            }
        },
        "group": "Variable Refrigerant Flow Equipment",
        "legacy_idd": {
            "field_info": {
                "zone_terminal_unit_list_name": {
                    "field_name": "Zone Terminal Unit List Name",
                    "field_type": "a"
                },
                "zone_terminal_unit_name": {
                    "field_name": "Zone Terminal Unit Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "zone_terminal_unit_list_name"
            ],
            "alphas": {
                "fields": [
                    "zone_terminal_unit_list_name"
                ],
                "extensions": [
                    "zone_terminal_unit_name"
                ]
            },
            "numerics": {
                "fields": []
            },
            "extensibles": [
                "zone_terminal_unit_name"
            ],
            "extension": "terminal_units"
        },
        "type": "object",
        "memo": "List of variable refrigerant flow (VRF) terminal units served by a given VRF condensing unit. See ZoneHVAC:TerminalUnit:VariableRefrigerantFlow and AirConditioner:VariableRefrigerantFlow.",
        "min_fields": 2.0,
        "extensible_size": 1.0
    }
}
```
