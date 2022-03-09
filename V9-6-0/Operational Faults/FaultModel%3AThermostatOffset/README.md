```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "thermostat_name": {
                    "type": "string",
                    "note": "Enter the name of a ZoneControl:Thermostat object.",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneControlThermostaticNames"
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
                "reference_thermostat_offset": {
                    "type": "number",
                    "exclusiveMinimum": -10.0,
                    "exclusiveMaximum": 10.0,
                    "default": 2.0,
                    "units": "deltaC"
                }
            },
            "required": [
                "thermostat_name"
            ]
        }
    },
    "group": "Operational Faults",
    "name": {
        "type": "string",
        "note": "Enter the name of the fault",
        "is_required": true,
        "reference": [
            "ThermostatOffsetFaults"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "thermostat_name": {
                "field_name": "Thermostat Name",
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
            "reference_thermostat_offset": {
                "field_name": "Reference Thermostat Offset",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "thermostat_name",
            "availability_schedule_name",
            "severity_schedule_name",
            "reference_thermostat_offset"
        ],
        "alphas": {
            "fields": [
                "name",
                "thermostat_name",
                "availability_schedule_name",
                "severity_schedule_name"
            ]
        },
        "numerics": {
            "fields": [
                "reference_thermostat_offset"
            ]
        }
    },
    "type": "object",
    "memo": "This object describes fault of thermostat offset",
    "min_fields": 5.0
}
```
