```
{
    "Schedule:Day:Hourly": {
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
                    "hour_1": {
                        "type": "number",
                        "default": 0.0
                    },
                    "hour_2": {
                        "type": "number",
                        "default": 0.0
                    },
                    "hour_3": {
                        "type": "number",
                        "default": 0.0
                    },
                    "hour_4": {
                        "type": "number",
                        "default": 0.0
                    },
                    "hour_5": {
                        "type": "number",
                        "default": 0.0
                    },
                    "hour_6": {
                        "type": "number",
                        "default": 0.0
                    },
                    "hour_7": {
                        "type": "number",
                        "default": 0.0
                    },
                    "hour_8": {
                        "type": "number",
                        "default": 0.0
                    },
                    "hour_9": {
                        "type": "number",
                        "default": 0.0
                    },
                    "hour_10": {
                        "type": "number",
                        "default": 0.0
                    },
                    "hour_11": {
                        "type": "number",
                        "default": 0.0
                    },
                    "hour_12": {
                        "type": "number",
                        "default": 0.0
                    },
                    "hour_13": {
                        "type": "number",
                        "default": 0.0
                    },
                    "hour_14": {
                        "type": "number",
                        "default": 0.0
                    },
                    "hour_15": {
                        "type": "number",
                        "default": 0.0
                    },
                    "hour_16": {
                        "type": "number",
                        "default": 0.0
                    },
                    "hour_17": {
                        "type": "number",
                        "default": 0.0
                    },
                    "hour_18": {
                        "type": "number",
                        "default": 0.0
                    },
                    "hour_19": {
                        "type": "number",
                        "default": 0.0
                    },
                    "hour_20": {
                        "type": "number",
                        "default": 0.0
                    },
                    "hour_21": {
                        "type": "number",
                        "default": 0.0
                    },
                    "hour_22": {
                        "type": "number",
                        "default": 0.0
                    },
                    "hour_23": {
                        "type": "number",
                        "default": 0.0
                    },
                    "hour_24": {
                        "type": "number",
                        "default": 0.0
                    }
                }
            }
        },
        "group": "Schedules",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "DayScheduleNames"
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
                "hour_1": {
                    "field_name": "Hour 1",
                    "field_type": "n"
                },
                "hour_2": {
                    "field_name": "Hour 2",
                    "field_type": "n"
                },
                "hour_3": {
                    "field_name": "Hour 3",
                    "field_type": "n"
                },
                "hour_4": {
                    "field_name": "Hour 4",
                    "field_type": "n"
                },
                "hour_5": {
                    "field_name": "Hour 5",
                    "field_type": "n"
                },
                "hour_6": {
                    "field_name": "Hour 6",
                    "field_type": "n"
                },
                "hour_7": {
                    "field_name": "Hour 7",
                    "field_type": "n"
                },
                "hour_8": {
                    "field_name": "Hour 8",
                    "field_type": "n"
                },
                "hour_9": {
                    "field_name": "Hour 9",
                    "field_type": "n"
                },
                "hour_10": {
                    "field_name": "Hour 10",
                    "field_type": "n"
                },
                "hour_11": {
                    "field_name": "Hour 11",
                    "field_type": "n"
                },
                "hour_12": {
                    "field_name": "Hour 12",
                    "field_type": "n"
                },
                "hour_13": {
                    "field_name": "Hour 13",
                    "field_type": "n"
                },
                "hour_14": {
                    "field_name": "Hour 14",
                    "field_type": "n"
                },
                "hour_15": {
                    "field_name": "Hour 15",
                    "field_type": "n"
                },
                "hour_16": {
                    "field_name": "Hour 16",
                    "field_type": "n"
                },
                "hour_17": {
                    "field_name": "Hour 17",
                    "field_type": "n"
                },
                "hour_18": {
                    "field_name": "Hour 18",
                    "field_type": "n"
                },
                "hour_19": {
                    "field_name": "Hour 19",
                    "field_type": "n"
                },
                "hour_20": {
                    "field_name": "Hour 20",
                    "field_type": "n"
                },
                "hour_21": {
                    "field_name": "Hour 21",
                    "field_type": "n"
                },
                "hour_22": {
                    "field_name": "Hour 22",
                    "field_type": "n"
                },
                "hour_23": {
                    "field_name": "Hour 23",
                    "field_type": "n"
                },
                "hour_24": {
                    "field_name": "Hour 24",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "schedule_type_limits_name",
                "hour_1",
                "hour_2",
                "hour_3",
                "hour_4",
                "hour_5",
                "hour_6",
                "hour_7",
                "hour_8",
                "hour_9",
                "hour_10",
                "hour_11",
                "hour_12",
                "hour_13",
                "hour_14",
                "hour_15",
                "hour_16",
                "hour_17",
                "hour_18",
                "hour_19",
                "hour_20",
                "hour_21",
                "hour_22",
                "hour_23",
                "hour_24"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "schedule_type_limits_name"
                ]
            },
            "numerics": {
                "fields": [
                    "hour_1",
                    "hour_2",
                    "hour_3",
                    "hour_4",
                    "hour_5",
                    "hour_6",
                    "hour_7",
                    "hour_8",
                    "hour_9",
                    "hour_10",
                    "hour_11",
                    "hour_12",
                    "hour_13",
                    "hour_14",
                    "hour_15",
                    "hour_16",
                    "hour_17",
                    "hour_18",
                    "hour_19",
                    "hour_20",
                    "hour_21",
                    "hour_22",
                    "hour_23",
                    "hour_24"
                ]
            }
        },
        "type": "object",
        "memo": "A Schedule:Day:Hourly contains 24 values for each hour of the day.",
        "min_fields": 26.0
    }
}
```
