```
{
    "ZoneGroup": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "zone_list_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneListNames"
                        ]
                    },
                    "zone_list_multiplier": {
                        "type": "number",
                        "default": 1.0,
                        "minimum": 1.0
                    }
                },
                "required": [
                    "zone_list_name"
                ]
            }
        },
        "group": "Thermal Zones and Surfaces",
        "name": {
            "type": "string",
            "note": "Name of the Zone Group",
            "is_required": true
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "zone_list_name": {
                    "field_name": "Zone List Name",
                    "field_type": "a"
                },
                "zone_list_multiplier": {
                    "field_name": "Zone List Multiplier",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "zone_list_name",
                "zone_list_multiplier"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "zone_list_name"
                ]
            },
            "numerics": {
                "fields": [
                    "zone_list_multiplier"
                ]
            }
        },
        "type": "object",
        "memo": "Adds a multiplier to a ZoneList. This can be used to reduce the amount of input necessary for simulating repetitive structures, such as the identical floors of a multi-story building.",
        "min_fields": 2.0
    }
}
```
