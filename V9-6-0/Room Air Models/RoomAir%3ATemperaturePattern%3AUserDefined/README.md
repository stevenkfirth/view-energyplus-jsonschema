```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "zone_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "availability_schedule_name": {
                    "type": "string",
                    "note": "Availability schedule name for this model. Schedule value > 0 means the model is active. Schedule value = 0 means the model is inactive and the zone will be modeled as fully mixed (Mixing). If this field is blank, the model is always active.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "pattern_control_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "The schedule should contain integer values that correspond to unique Control Integer fields in one of the RoomAir:TemperaturePattern:* objects."
                }
            },
            "required": [
                "zone_name",
                "pattern_control_schedule_name"
            ]
        }
    },
    "group": "Room Air Models",
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
            "zone_name": {
                "field_name": "Zone Name",
                "field_type": "a"
            },
            "availability_schedule_name": {
                "field_name": "Availability Schedule Name",
                "field_type": "a"
            },
            "pattern_control_schedule_name": {
                "field_name": "Pattern Control Schedule Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "zone_name",
            "availability_schedule_name",
            "pattern_control_schedule_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "zone_name",
                "availability_schedule_name",
                "pattern_control_schedule_name"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "Used to explicitly define temperature patterns that are to be applied to the mean air temperature within a thermal zone. Used with RoomAirModelType = UserDefined."
}
```
