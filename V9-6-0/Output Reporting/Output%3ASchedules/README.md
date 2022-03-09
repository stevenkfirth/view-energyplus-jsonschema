```
{
    "Output:Schedules": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "key_field": {
                        "type": "string",
                        "enum": [
                            "Hourly",
                            "Timestep"
                        ]
                    }
                },
                "required": [
                    "key_field"
                ]
            }
        },
        "group": "Output Reporting",
        "legacy_idd": {
            "field_info": {
                "key_field": {
                    "field_name": "Key Field",
                    "field_type": "a"
                }
            },
            "fields": [
                "key_field"
            ],
            "alphas": {
                "fields": [
                    "key_field"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "Produces a condensed reporting that illustrates the full range of schedule values in the eio output file. In the style of input: DaySchedule,  WeekSchedule, and Annual Schedule.",
        "format": "singleLine"
    }
}
```
