```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "zone_1_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "zone_2_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "schedule_name": {
                    "type": "string",
                    "note": "This schedule defines the fraction of the time the refrigeration door is open For example, if the warehouse is closed at night and there are no door openings between two zones, the value for that time period would be 0. If doors were propped open, the value  over that time period would be 1.0 If the doors were open about 20% of the time, the value over that period would be 0.2 Schedule values must lie between 0 and 1.0",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "door_height": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0,
                    "maximum": 50.0,
                    "default": 3.0
                },
                "door_area": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 400.0,
                    "default": 9.0,
                    "units": "m2"
                },
                "door_protection_type": {
                    "type": "string",
                    "note": "Door protection can reduce the air flow through a refrigeration door The default value is \"None\" Choices: \"None\", \"AirCurtain\", and \"StripCurtain\" A strip curtain reduces the air flow more than an air curtain",
                    "enum": [
                        "",
                        "AirCurtain",
                        "None",
                        "StripCurtain"
                    ],
                    "default": "None"
                }
            },
            "required": [
                "zone_1_name",
                "zone_2_name",
                "schedule_name"
            ]
        }
    },
    "group": "Zone Airflow",
    "name": {
        "type": "string",
        "is_required": true
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "zone_1_name": {
                "field_name": "Zone 1 Name",
                "field_type": "a"
            },
            "zone_2_name": {
                "field_name": "Zone 2 Name",
                "field_type": "a"
            },
            "schedule_name": {
                "field_name": "Schedule Name",
                "field_type": "a"
            },
            "door_height": {
                "field_name": "Door Height",
                "field_type": "n"
            },
            "door_area": {
                "field_name": "Door Area",
                "field_type": "n"
            },
            "door_protection_type": {
                "field_name": "Door Protection Type",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "zone_1_name",
            "zone_2_name",
            "schedule_name",
            "door_height",
            "door_area",
            "door_protection_type"
        ],
        "alphas": {
            "fields": [
                "name",
                "zone_1_name",
                "zone_2_name",
                "schedule_name",
                "door_protection_type"
            ]
        },
        "numerics": {
            "fields": [
                "door_height",
                "door_area"
            ]
        }
    },
    "type": "object",
    "memo": "Refrigeration Door Mixing is used for an opening between two zones that are at the same elevation but have different air temperatures. In this case, the mixing air flow between the two zones is determined by the density difference between the two zones. This would typically be used between two zones in a refrigerated warehouse that are controlled at different temperatures. It could also be used to model a door to a walk-in refrigerated space if that space were modeled as a zone instead of using the object Refrigeration:WalkIn.",
    "min_fields": 4.0
}
```
