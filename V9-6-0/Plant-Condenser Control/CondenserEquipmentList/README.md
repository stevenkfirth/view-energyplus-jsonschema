```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "equipment": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "equipment_object_type": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "validCondenserEquipmentTypes"
                                ]
                            },
                            "equipment_name": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "validCondenserEquipmentNames"
                                ]
                            }
                        },
                        "type": "object"
                    }
                }
            }
        }
    },
    "group": "Plant-Condenser Control",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "CondenserEquipmentLists",
            "PlantAndCondenserEquipmentLists"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "equipment_object_type": {
                "field_name": "Equipment Object Type",
                "field_type": "a"
            },
            "equipment_name": {
                "field_name": "Equipment Name",
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
                "equipment_object_type",
                "equipment_name"
            ]
        },
        "numerics": {
            "fields": []
        },
        "extensibles": [
            "equipment_object_type",
            "equipment_name"
        ],
        "extension": "equipment"
    },
    "type": "object",
    "memo": "List condenser equipment in order of operating priority, 1st in list will be used 1st, etc Use only condenser equipment in this list. If no equipment object types and equipment names are specified, then the corresponding PlantEquipmentOperation:* object will assume all available condenser equipment for the loop should be OFF (not operate) within the specified lower/upper limit.",
    "min_fields": 1.0,
    "extensible_size": 2.0
}
```
