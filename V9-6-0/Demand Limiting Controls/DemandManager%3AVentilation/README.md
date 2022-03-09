```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "availability_schedule_name": {
                    "type": "string",
                    "note": "Availability schedule name for this demand manager. Schedule value > 0 means the demand manager is available. If this field is blank, the DR is always available.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "limit_control": {
                    "type": "string",
                    "enum": [
                        "FixedRate",
                        "Off",
                        "ReductionRatio"
                    ]
                },
                "minimum_limit_duration": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "units": "minutes",
                    "note": "If blank, duration defaults to the timestep"
                },
                "fixed_rate": {
                    "type": "number",
                    "note": "Used in case when Limit strategy is set to FixedRate",
                    "minimum": 0.0,
                    "units": "m3/s"
                },
                "reduction_ratio": {
                    "type": "number",
                    "note": "Used in case when Limit Control is set to ReductionRatio",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "limit_step_change": {
                    "type": "number",
                    "note": "Not yet implemented"
                },
                "selection_control": {
                    "type": "string",
                    "enum": [
                        "",
                        "All",
                        "RotateMany",
                        "RotateOne"
                    ],
                    "default": "All"
                },
                "rotation_duration": {
                    "type": "number",
                    "minimum": 0.0,
                    "units": "minutes",
                    "note": "If blank, duration defaults to the timestep"
                },
                "controllers": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "controller_outdoor_air_name": {
                                "type": "string",
                                "note": "Enter the name of a Controller:OutdoorAir object.",
                                "data_type": "object_list",
                                "object_list": [
                                    "OAControllerNames"
                                ]
                            }
                        },
                        "type": "object",
                        "required": [
                            "controller_outdoor_air_name"
                        ]
                    }
                }
            },
            "required": [
                "limit_control"
            ]
        }
    },
    "group": "Demand Limiting Controls",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "DemandManagerNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "availability_schedule_name": {
                "field_name": "Availability Schedule Name",
                "field_type": "a"
            },
            "limit_control": {
                "field_name": "Limit Control",
                "field_type": "a"
            },
            "minimum_limit_duration": {
                "field_name": "Minimum Limit Duration",
                "field_type": "n"
            },
            "fixed_rate": {
                "field_name": "Fixed Rate",
                "field_type": "n"
            },
            "reduction_ratio": {
                "field_name": "Reduction Ratio",
                "field_type": "n"
            },
            "limit_step_change": {
                "field_name": "Limit Step Change",
                "field_type": "n"
            },
            "selection_control": {
                "field_name": "Selection Control",
                "field_type": "a"
            },
            "rotation_duration": {
                "field_name": "Rotation Duration",
                "field_type": "n"
            },
            "controller_outdoor_air_name": {
                "field_name": "Controller Outdoor Air Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "limit_control",
            "minimum_limit_duration",
            "fixed_rate",
            "reduction_ratio",
            "limit_step_change",
            "selection_control",
            "rotation_duration"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "limit_control",
                "selection_control"
            ],
            "extensions": [
                "controller_outdoor_air_name"
            ]
        },
        "numerics": {
            "fields": [
                "minimum_limit_duration",
                "fixed_rate",
                "reduction_ratio",
                "limit_step_change",
                "rotation_duration"
            ]
        },
        "extensibles": [
            "controller_outdoor_air_name"
        ],
        "extension": "controllers"
    },
    "type": "object",
    "memo": "used for demand limiting Controller:OutdoorAir objects.",
    "min_fields": 10.0,
    "extensible_size": 1.0
}
```
