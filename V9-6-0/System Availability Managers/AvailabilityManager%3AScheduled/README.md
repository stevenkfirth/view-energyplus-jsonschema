```
{
    "AvailabilityManager:Scheduled": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    }
                },
                "required": [
                    "schedule_name"
                ]
            }
        },
        "group": "System Availability Managers",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "SystemAvailabilityManagers"
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
                }
            },
            "fields": [
                "name",
                "schedule_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "schedule_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "Determines the availability of a loop or system: whether it is on or off. Schedule overrides fan/pump schedule.",
        "min_fields": 2.0
    }
}
```
