```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "equipment_list_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "PlantAndCondenserEquipmentLists"
                    ]
                }
            },
            "required": [
                "equipment_list_name"
            ]
        }
    },
    "group": "Plant-Condenser Control",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "ControlSchemeList"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "equipment_list_name": {
                "field_name": "Equipment List Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "equipment_list_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "equipment_list_name"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "Plant equipment operation scheme for uncontrolled operation. Specifies a group of equipment that runs if the loop is active, unless turned off by the loop flow resolver to maintain continuity in the fluid loop.",
    "min_fields": 2.0
}
```
