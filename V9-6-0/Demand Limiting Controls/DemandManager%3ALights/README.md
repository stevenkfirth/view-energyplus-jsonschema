```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "availability_schedule_name": {
                    "type": "string",
                    "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "limit_control": {
                    "type": "string",
                    "enum": [
                        "Fixed",
                        "Off"
                    ]
                },
                "minimum_limit_duration": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "units": "minutes",
                    "note": "If blank, duration defaults to the timestep"
                },
                "maximum_limit_fraction": {
                    "type": "number",
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
                        "All",
                        "RotateMany",
                        "RotateOne"
                    ]
                },
                "rotation_duration": {
                    "type": "number",
                    "minimum": 0.0,
                    "units": "minutes",
                    "note": "If blank, duration defaults to the timestep"
                },
                "lights": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "lights_name": {
                                "type": "string",
                                "note": "Enter the name of an Lights object. if ZoneList option is used on the Lights object, a single lights object from that assignment can be selected by entering <Zone Name><space><Global Lights Object Name>.",
                                "data_type": "object_list",
                                "object_list": [
                                    "LightsNames"
                                ]
                            }
                        },
                        "type": "object",
                        "required": [
                            "lights_name"
                        ]
                    }
                }
            },
            "required": [
                "limit_control",
                "selection_control"
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
            "maximum_limit_fraction": {
                "field_name": "Maximum Limit Fraction",
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
            "lights_name": {
                "field_name": "Lights Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "limit_control",
            "minimum_limit_duration",
            "maximum_limit_fraction",
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
                "lights_name"
            ]
        },
        "numerics": {
            "fields": [
                "minimum_limit_duration",
                "maximum_limit_fraction",
                "limit_step_change",
                "rotation_duration"
            ]
        },
        "extensibles": [
            "lights_name"
        ],
        "extension": "lights"
    },
    "type": "object",
    "memo": "used for demand limiting Lights objects.",
    "extensible_size": 1.0
}
```
