```
{
    "FaultModel:Fouling:Coil": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "coil_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "SimpleCoils"
                        ]
                    },
                    "availability_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "severity_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "fouling_input_method": {
                        "type": "string",
                        "enum": [
                            "",
                            "FouledUARated",
                            "FoulingFactor"
                        ],
                        "default": "FouledUARated"
                    },
                    "uafouled": {
                        "type": "number",
                        "note": "Fouling coil UA value under rating conditions For Fouling Input Method: FouledUARated",
                        "units": "W/K",
                        "exclusiveMinimum": 0.0
                    },
                    "water_side_fouling_factor": {
                        "type": "number",
                        "note": "For Fouling Input Method: FoulingFactor",
                        "units": "m2-K/W",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "air_side_fouling_factor": {
                        "type": "number",
                        "note": "For Fouling Input Method: FoulingFactor",
                        "units": "m2-K/W",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "outside_coil_surface_area": {
                        "type": "number",
                        "note": "For Fouling Input Method: FoulingFactor",
                        "units": "m2",
                        "exclusiveMinimum": 0.0
                    },
                    "inside_to_outside_coil_surface_area_ratio": {
                        "type": "number",
                        "note": "For Fouling Input Method: FoulingFactor",
                        "units": "dimensionless",
                        "exclusiveMinimum": 0.0,
                        "default": 0.07
                    }
                },
                "required": [
                    "coil_name"
                ]
            }
        },
        "group": "Operational Faults",
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
                "coil_name": {
                    "field_name": "Coil Name",
                    "field_type": "a"
                },
                "availability_schedule_name": {
                    "field_name": "Availability Schedule Name",
                    "field_type": "a"
                },
                "severity_schedule_name": {
                    "field_name": "Severity Schedule Name",
                    "field_type": "a"
                },
                "fouling_input_method": {
                    "field_name": "Fouling Input Method",
                    "field_type": "a"
                },
                "uafouled": {
                    "field_name": "UAFouled",
                    "field_type": "n"
                },
                "water_side_fouling_factor": {
                    "field_name": "Water Side Fouling Factor",
                    "field_type": "n"
                },
                "air_side_fouling_factor": {
                    "field_name": "Air Side Fouling Factor",
                    "field_type": "n"
                },
                "outside_coil_surface_area": {
                    "field_name": "Outside Coil Surface Area",
                    "field_type": "n"
                },
                "inside_to_outside_coil_surface_area_ratio": {
                    "field_name": "Inside to Outside Coil Surface Area Ratio",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "coil_name",
                "availability_schedule_name",
                "severity_schedule_name",
                "fouling_input_method",
                "uafouled",
                "water_side_fouling_factor",
                "air_side_fouling_factor",
                "outside_coil_surface_area",
                "inside_to_outside_coil_surface_area_ratio"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "coil_name",
                    "availability_schedule_name",
                    "severity_schedule_name",
                    "fouling_input_method"
                ]
            },
            "numerics": {
                "fields": [
                    "uafouled",
                    "water_side_fouling_factor",
                    "air_side_fouling_factor",
                    "outside_coil_surface_area",
                    "inside_to_outside_coil_surface_area_ratio"
                ]
            }
        },
        "type": "object",
        "memo": "This object describes fouling water heating or cooling coils",
        "min_fields": 6.0
    }
}
```
