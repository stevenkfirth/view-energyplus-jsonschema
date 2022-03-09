```
{
    "Schedule:File": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "schedule_type_limits_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleTypeLimitsNames"
                        ]
                    },
                    "file_name": {
                        "type": "string",
                        "retaincase": true
                    },
                    "column_number": {
                        "type": "number",
                        "minimum": 1.0
                    },
                    "rows_to_skip_at_top": {
                        "type": "number",
                        "minimum": 0.0
                    },
                    "number_of_hours_of_data": {
                        "type": "number",
                        "note": "8760 hours does not account for leap years, 8784 does. should be either 8760 or 8784",
                        "default": 8760.0,
                        "minimum": 8760.0,
                        "maximum": 8784.0
                    },
                    "column_separator": {
                        "type": "string",
                        "enum": [
                            "",
                            "Comma",
                            "Semicolon",
                            "Space",
                            "Tab"
                        ],
                        "default": "Comma"
                    },
                    "interpolate_to_timestep": {
                        "type": "string",
                        "note": "when the interval does not match the user specified timestep a \"Yes\" choice will average between the intervals request (to timestep resolution. a \"No\" choice will use the interval value at the simulation timestep without regard to if it matches the boundary or not.",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No"
                    },
                    "minutes_per_item": {
                        "type": "number",
                        "note": "Must be evenly divisible into 60",
                        "minimum": 1.0,
                        "maximum": 60.0
                    }
                },
                "required": [
                    "file_name",
                    "column_number",
                    "rows_to_skip_at_top"
                ]
            }
        },
        "group": "Schedules",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "ScheduleNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "schedule_type_limits_name": {
                    "field_name": "Schedule Type Limits Name",
                    "field_type": "a"
                },
                "file_name": {
                    "field_name": "File Name",
                    "field_type": "a"
                },
                "column_number": {
                    "field_name": "Column Number",
                    "field_type": "n"
                },
                "rows_to_skip_at_top": {
                    "field_name": "Rows to Skip at Top",
                    "field_type": "n"
                },
                "number_of_hours_of_data": {
                    "field_name": "Number of Hours of Data",
                    "field_type": "n"
                },
                "column_separator": {
                    "field_name": "Column Separator",
                    "field_type": "a"
                },
                "interpolate_to_timestep": {
                    "field_name": "Interpolate to Timestep",
                    "field_type": "a"
                },
                "minutes_per_item": {
                    "field_name": "Minutes per Item",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "schedule_type_limits_name",
                "file_name",
                "column_number",
                "rows_to_skip_at_top",
                "number_of_hours_of_data",
                "column_separator",
                "interpolate_to_timestep",
                "minutes_per_item"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "schedule_type_limits_name",
                    "file_name",
                    "column_separator",
                    "interpolate_to_timestep"
                ]
            },
            "numerics": {
                "fields": [
                    "column_number",
                    "rows_to_skip_at_top",
                    "number_of_hours_of_data",
                    "minutes_per_item"
                ]
            }
        },
        "type": "object",
        "memo": "A Schedule:File points to a text computer file that has 8760-8784 hours of data.",
        "min_fields": 5.0
    }
}
```
