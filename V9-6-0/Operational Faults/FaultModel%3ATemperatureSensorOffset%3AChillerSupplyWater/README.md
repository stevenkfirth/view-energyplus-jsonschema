```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
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
                "chiller_object_type": {
                    "type": "string",
                    "note": "Enter the type of a chiller object",
                    "enum": [
                        "Chiller:Absorption",
                        "Chiller:Absorption:Indirect",
                        "Chiller:CombustionTurbine",
                        "Chiller:ConstantCOP",
                        "Chiller:Electric",
                        "Chiller:Electric:EIR",
                        "Chiller:Electric:ReformulatedEIR",
                        "Chiller:EngineDriven"
                    ]
                },
                "chiller_object_name": {
                    "type": "string",
                    "note": "Enter the name of a chiller object",
                    "data_type": "object_list",
                    "object_list": [
                        "Chillers"
                    ]
                },
                "reference_sensor_offset": {
                    "type": "number",
                    "exclusiveMinimum": -10.0,
                    "exclusiveMaximum": 10.0,
                    "default": 0.0,
                    "units": "deltaC"
                }
            },
            "required": [
                "chiller_object_type",
                "chiller_object_name"
            ]
        }
    },
    "group": "Operational Faults",
    "name": {
        "type": "string",
        "note": "Enter the name of the fault",
        "is_required": true
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
            "severity_schedule_name": {
                "field_name": "Severity Schedule Name",
                "field_type": "a"
            },
            "chiller_object_type": {
                "field_name": "Chiller Object Type",
                "field_type": "a"
            },
            "chiller_object_name": {
                "field_name": "Chiller Object Name",
                "field_type": "a"
            },
            "reference_sensor_offset": {
                "field_name": "Reference Sensor Offset",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "severity_schedule_name",
            "chiller_object_type",
            "chiller_object_name",
            "reference_sensor_offset"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "severity_schedule_name",
                "chiller_object_type",
                "chiller_object_name"
            ]
        },
        "numerics": {
            "fields": [
                "reference_sensor_offset"
            ]
        }
    },
    "type": "object",
    "memo": "This object describes fault of chiller supply water temperature sensor offset",
    "min_fields": 6.0
}
```
