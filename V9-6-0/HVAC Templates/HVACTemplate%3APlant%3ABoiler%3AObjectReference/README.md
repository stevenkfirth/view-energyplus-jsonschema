```
{
    "HVACTemplate:Plant:Boiler:ObjectReference": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "boiler_object_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Boiler:HotWater"
                        ],
                        "default": "Boiler:HotWater"
                    },
                    "boiler_name": {
                        "type": "string",
                        "note": "The name of the detailed boiler object.",
                        "data_type": "object_list",
                        "object_list": [
                            "Boilers"
                        ]
                    },
                    "priority": {
                        "type": "number",
                        "note": "If Hot Water Plant Operation Scheme Type=Default in HVACTemplate:Plant:HotWaterLoop or MixedWaterLoop, then equipment operates in Priority order, 1, 2, 3, etc."
                    },
                    "template_plant_loop_type": {
                        "type": "string",
                        "note": "Specifies if this boiler serves a template hot water loop or mixed water loop If left blank, will serve a hot water loop if present, or a mixed water loop (if no hot water loop is present).",
                        "enum": [
                            "HotWater",
                            "MixedWater"
                        ]
                    }
                },
                "required": [
                    "boiler_name"
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
                "boiler_object_type": {
                    "field_name": "Boiler Object Type",
                    "field_type": "a"
                },
                "boiler_name": {
                    "field_name": "Boiler Name",
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
                "boiler_object_type",
                "boiler_name",
                "priority",
                "template_plant_loop_type"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "boiler_object_type",
                    "boiler_name",
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
        "memo": "This object references a detailed boiler object and adds it to an HVACTemplate:Plant:HotWaterLoop or MixedWaterLoop. The user must create a complete detailed boiler object with all required curve or performance objects.",
        "min_fields": 4.0
    }
}
```
