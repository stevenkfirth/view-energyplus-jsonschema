```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "units in schedule should be fraction applied to capacity of the exterior lights equipment, generally (0.0 - 1.0)"
                },
                "design_level": {
                    "type": "number",
                    "units": "W",
                    "minimum": 0.0,
                    "ip-units": "W"
                },
                "control_option": {
                    "type": "string",
                    "note": "Astronomical Clock option overrides schedule to turn lights off when sun is up",
                    "enum": [
                        "AstronomicalClock",
                        "ScheduleNameOnly"
                    ]
                },
                "end_use_subcategory": {
                    "type": "string",
                    "note": "Any text may be used here to categorize the end-uses in the ABUPS End Uses by Subcategory table.",
                    "retaincase": true,
                    "default": "General"
                }
            },
            "required": [
                "schedule_name",
                "design_level"
            ]
        }
    },
    "group": "Exterior Equipment",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "ExteriorLightsNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "schedule_name": {
                "field_name": "Schedule Name",
                "field_type": "a"
            },
            "design_level": {
                "field_name": "Design Level",
                "field_type": "n"
            },
            "control_option": {
                "field_name": "Control Option",
                "field_type": "a"
            },
            "end_use_subcategory": {
                "field_name": "End-Use Subcategory",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "schedule_name",
            "design_level",
            "control_option",
            "end_use_subcategory"
        ],
        "alphas": {
            "fields": [
                "name",
                "schedule_name",
                "control_option",
                "end_use_subcategory"
            ]
        },
        "numerics": {
            "fields": [
                "design_level"
            ]
        }
    },
    "type": "object",
    "memo": "only used for Meter type reporting, does not affect building loads"
}
```
