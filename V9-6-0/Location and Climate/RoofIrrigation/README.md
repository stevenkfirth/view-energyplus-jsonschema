```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "irrigation_model_type": {
                    "type": "string",
                    "enum": [
                        "Schedule",
                        "SmartSchedule"
                    ],
                    "note": "SmartSchedule will not allow irrigation when soil is already moist. Current threshold set at 30% of saturation."
                },
                "irrigation_rate_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Schedule values in meters of water per hour values should be non-negative"
                },
                "irrigation_maximum_saturation_threshold": {
                    "type": "number",
                    "note": "Used with SmartSchedule to set the saturation level at which no irrigation is allowed.",
                    "units": "percent",
                    "minimum": 0.0,
                    "maximum": 100.0,
                    "default": 40.0
                }
            }
        }
    },
    "group": "Location and Climate",
    "legacy_idd": {
        "field_info": {
            "irrigation_model_type": {
                "field_name": "Irrigation Model Type",
                "field_type": "a"
            },
            "irrigation_rate_schedule_name": {
                "field_name": "Irrigation Rate Schedule Name",
                "field_type": "a"
            },
            "irrigation_maximum_saturation_threshold": {
                "field_name": "Irrigation Maximum Saturation Threshold",
                "field_type": "n"
            }
        },
        "fields": [
            "irrigation_model_type",
            "irrigation_rate_schedule_name",
            "irrigation_maximum_saturation_threshold"
        ],
        "alphas": {
            "fields": [
                "irrigation_model_type",
                "irrigation_rate_schedule_name"
            ]
        },
        "numerics": {
            "fields": [
                "irrigation_maximum_saturation_threshold"
            ]
        }
    },
    "type": "object",
    "memo": "Used to describe the amount of irrigation on the ecoroof surface over the course of the simulation runperiod."
}
```
