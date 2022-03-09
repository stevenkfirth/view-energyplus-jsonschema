```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "cooling_tower_object_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "CoolingTower:SingleSpeed",
                        "CoolingTower:TwoSpeed",
                        "CoolingTower:VariableSpeed"
                    ],
                    "default": "CoolingTower:SingleSpeed"
                },
                "cooling_tower_name": {
                    "type": "string",
                    "note": "The name of the detailed cooling tower object.",
                    "data_type": "object_list",
                    "object_list": [
                        "CoolingTowers"
                    ]
                },
                "priority": {
                    "type": "number",
                    "note": "If Condenser Plant Operation Scheme Type=Default in HVACTemplate:Plant:ChilledWaterLoop or MixedWaterLoop, then equipment operates in Priority order, 1, 2, 3, etc."
                },
                "template_plant_loop_type": {
                    "type": "string",
                    "note": "Specifies if this tower serves a template chilled water loop or mixed water loop If left blank, will serve a chilled water loop if present, or a mixed water loop (if no chilled water loop is present).",
                    "enum": [
                        "ChilledWater",
                        "MixedWater"
                    ]
                }
            },
            "required": [
                "cooling_tower_name"
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
            "cooling_tower_object_type": {
                "field_name": "Cooling Tower Object Type",
                "field_type": "a"
            },
            "cooling_tower_name": {
                "field_name": "Cooling Tower Name",
                "field_type": "a"
            },
            "priority": {
                "field_name": "Priority",
                "field_type": "n"
            },
            "template_plant_loop_type": {
                "field_name": "Template Plant Loop Type",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "cooling_tower_object_type",
            "cooling_tower_name",
            "priority",
            "template_plant_loop_type"
        ],
        "alphas": {
            "fields": [
                "name",
                "cooling_tower_object_type",
                "cooling_tower_name",
                "template_plant_loop_type"
            ]
        },
        "numerics": {
            "fields": [
                "priority"
            ]
        }
    },
    "type": "object",
    "memo": "This object references a detailed cooling tower object and adds it to an HVACTemplate:Plant:ChilledWaterLoop or MixedWaterLoop. The user must create a complete detailed cooling tower object with all required curve or performance objects.",
    "min_fields": 4.0
}
```
