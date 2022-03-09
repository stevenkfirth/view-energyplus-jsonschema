```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "chiller_object_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "Chiller:Electric:EIR",
                        "Chiller:Electric:ReformulatedEIR"
                    ],
                    "default": "Chiller:Electric:EIR"
                },
                "chiller_name": {
                    "type": "string",
                    "note": "The name of the detailed chiller object.",
                    "data_type": "object_list",
                    "object_list": [
                        "Chillers"
                    ]
                },
                "priority": {
                    "type": "number",
                    "note": "If Chiller Plant Operation Scheme Type=Default in HVACTemplate:Plant:ChilledWaterLoop, then equipment operates in Priority order, 1, 2, 3, etc."
                }
            },
            "required": [
                "chiller_name"
            ]
        }
    },
    "group": "HVAC Templates",
    "name": {
        "type": "string",
        "note": "The name of this object.",
        "is_required": true
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "chiller_object_type": {
                "field_name": "Chiller Object Type",
                "field_type": "a"
            },
            "chiller_name": {
                "field_name": "Chiller Name",
                "field_type": "a"
            },
            "priority": {
                "field_name": "Priority",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "chiller_object_type",
            "chiller_name",
            "priority"
        ],
        "alphas": {
            "fields": [
                "name",
                "chiller_object_type",
                "chiller_name"
            ]
        },
        "numerics": {
            "fields": [
                "priority"
            ]
        }
    },
    "type": "object",
    "memo": "This object references a detailed chiller object and adds it to an HVACTemplate:Plant:ChilledWaterLoop. The user must create a complete detailed chiller object with all required curve or performance objects.",
    "min_fields": 4.0
}
```
