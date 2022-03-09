```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "construction_object_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ConstructionNames"
                    ]
                }
            },
            "required": [
                "construction_object_name"
            ]
        }
    },
    "group": "Energy Management System (EMS)",
    "name": {
        "type": "string",
        "is_required": true,
        "note": "This name becomes a variable for use in Erl programs no spaces allowed in name"
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "construction_object_name": {
                "field_name": "Construction Object Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "construction_object_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "construction_object_name"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "Declares EMS variable that identifies a construction",
    "min_fields": 2.0
}
```
