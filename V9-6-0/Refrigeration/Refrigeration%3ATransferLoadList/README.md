```
{
    "Refrigeration:TransferLoadList": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "transfer_loads": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "cascade_condenser_name_or_secondary_system_name": {
                                    "type": "string",
                                    "note": "Enter the name of a Refrigeration:Condenser:Cascade object OR the name of a Refrigeration:SecondarySystem object.",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "RefrigerationCascadeCondenserAndSecondarySystemNames"
                                    ]
                                }
                            },
                            "type": "object",
                            "required": [
                                "cascade_condenser_name_or_secondary_system_name"
                            ]
                        }
                    }
                }
            }
        },
        "group": "Refrigeration",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
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
                "cascade_condenser_name_or_secondary_system_name": {
                    "field_name": "Cascade Condenser Name or Secondary System Name",
                    "field_type": "a"
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
                    "cascade_condenser_name_or_secondary_system_name"
                ]
            },
            "numerics": {
                "fields": []
            },
            "extensibles": [
                "cascade_condenser_name_or_secondary_system_name"
            ],
            "extension": "transfer_loads"
        },
        "type": "object",
        "memo": "A refrigeration system may provide cooling to other, secondary, systems through either a secondary loop or a cascade condenser. If multiple transfer loads are served by a single primary system, use this list to group them together for reference by the primary system (see the field \"Refrigeration Transfer Load or TransferLoad List Name\" in the Refrigeration:System object).",
        "extensible_size": 1.0
    }
}
```
