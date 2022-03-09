```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "humidistat_name": {
                    "type": "string",
                    "note": "Enter the name of a ZoneControl:Humidistat object.",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneControlHumidistatNames"
                    ]
                },
                "humidistat_offset_type": {
                    "type": "string",
                    "note": "Two types are available: Type ThermostatOffsetIndependent Type ThermostatOffsetDependent",
                    "enum": [
                        "",
                        "ThermostatOffsetDependent",
                        "ThermostatOffsetIndependent"
                    ],
                    "default": "ThermostatOffsetIndependent"
                },
                "availability_schedule_name": {
                    "type": "string",
                    "note": "This field is applicable for Type ThermostatOffsetIndependent",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "severity_schedule_name": {
                    "type": "string",
                    "note": "This field is applicable for Type ThermostatOffsetIndependent",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "reference_humidistat_offset": {
                    "type": "number",
                    "note": "Required field for Type ThermostatOffsetIndependent",
                    "exclusiveMinimum": -20.0,
                    "exclusiveMaximum": 20.0,
                    "default": 5.0,
                    "units": "percent"
                },
                "related_thermostat_offset_fault_name": {
                    "type": "string",
                    "note": "Enter the name of a FaultModel:ThermostatOffset object Required field for Type ThermostatOffsetDependent",
                    "data_type": "object_list",
                    "object_list": [
                        "ThermostatOffsetFaults"
                    ]
                }
            },
            "required": [
                "humidistat_name"
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
            "humidistat_name": {
                "field_name": "Humidistat Name",
                "field_type": "a"
            },
            "humidistat_offset_type": {
                "field_name": "Humidistat Offset Type",
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
            "reference_humidistat_offset": {
                "field_name": "Reference Humidistat Offset",
                "field_type": "n"
            },
            "related_thermostat_offset_fault_name": {
                "field_name": "Related Thermostat Offset Fault Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "humidistat_name",
            "humidistat_offset_type",
            "availability_schedule_name",
            "severity_schedule_name",
            "reference_humidistat_offset",
            "related_thermostat_offset_fault_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "humidistat_name",
                "humidistat_offset_type",
                "availability_schedule_name",
                "severity_schedule_name",
                "related_thermostat_offset_fault_name"
            ]
        },
        "numerics": {
            "fields": [
                "reference_humidistat_offset"
            ]
        }
    },
    "type": "object",
    "memo": "This object describes fault of humidistat offset",
    "min_fields": 6.0
}
```
