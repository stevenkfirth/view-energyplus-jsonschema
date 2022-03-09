```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "thermostat_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneControlThermostaticNames"
                    ],
                    "note": "Enter the name of a ZoneControl:Thermostat object whose operation is to be modified to effect temperature control based on zone air humidity conditions. If the ZoneControl: Thermostat object references a ZoneList, simply enter the name of the ZoneControl:Thermostat object and this temperature and humidity thermostat control will be applied to all zones in the ZoneList. If the ZoneControl:Thermostat object references a ZoneList but it is desired that only a single zone within the ZoneList be controlled based on temperature and humidity control, then the name to be put here is <Zone Name> <Thermostat Name> where the Thermostat Name is the the name of the ZoneControl:Thermostat object."
                },
                "dehumidifying_relative_humidity_setpoint_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Schedule values should be in Relative Humidity (percent)"
                },
                "dehumidification_control_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "None",
                        "Overcool"
                    ],
                    "default": "Overcool"
                },
                "overcool_range_input_method": {
                    "type": "string",
                    "enum": [
                        "",
                        "Constant",
                        "Scheduled"
                    ],
                    "default": "Constant"
                },
                "overcool_constant_range": {
                    "type": "number",
                    "units": "deltaC",
                    "minimum": 0.0,
                    "maximum": 3.0,
                    "default": 1.7,
                    "note": "Maximum Overcool temperature range for cooling setpoint reduction. Used with Dehumidification Control Type = Overcool. A value of 0.0 indicates no zone temperature overcooling will be provided to gain additional dehumidification."
                },
                "overcool_range_schedule_name": {
                    "type": "string",
                    "note": "Schedule values of 0.0 indicates no zone temperature overcooling will be provided to gain additional dehumidification. Schedule values should be >= 0 and <= 3 (deltaC).",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "overcool_control_ratio": {
                    "type": "number",
                    "units": "percent/K",
                    "minimum": 0.0,
                    "default": 3.6,
                    "note": "The value of this input field is used to adjust the cooling setpoint temperature (established by the associated ZoneControl:Thermostat object) downward based on the difference between the zone air relative humidity level and the dehumidifying relative humidity setpoint."
                }
            },
            "required": [
                "thermostat_name",
                "dehumidifying_relative_humidity_setpoint_schedule_name"
            ]
        }
    },
    "group": "Zone HVAC Controls and Thermostats",
    "legacy_idd": {
        "field_info": {
            "thermostat_name": {
                "field_name": "Thermostat Name",
                "field_type": "a"
            },
            "dehumidifying_relative_humidity_setpoint_schedule_name": {
                "field_name": "Dehumidifying Relative Humidity Setpoint Schedule Name",
                "field_type": "a"
            },
            "dehumidification_control_type": {
                "field_name": "Dehumidification Control Type",
                "field_type": "a"
            },
            "overcool_range_input_method": {
                "field_name": "Overcool Range Input Method",
                "field_type": "a"
            },
            "overcool_constant_range": {
                "field_name": "Overcool Constant Range",
                "field_type": "n"
            },
            "overcool_range_schedule_name": {
                "field_name": "Overcool Range Schedule Name",
                "field_type": "a"
            },
            "overcool_control_ratio": {
                "field_name": "Overcool Control Ratio",
                "field_type": "n"
            }
        },
        "fields": [
            "thermostat_name",
            "dehumidifying_relative_humidity_setpoint_schedule_name",
            "dehumidification_control_type",
            "overcool_range_input_method",
            "overcool_constant_range",
            "overcool_range_schedule_name",
            "overcool_control_ratio"
        ],
        "alphas": {
            "fields": [
                "thermostat_name",
                "dehumidifying_relative_humidity_setpoint_schedule_name",
                "dehumidification_control_type",
                "overcool_range_input_method",
                "overcool_range_schedule_name"
            ]
        },
        "numerics": {
            "fields": [
                "overcool_constant_range",
                "overcool_control_ratio"
            ]
        }
    },
    "type": "object",
    "memo": "This object modifies a ZoneControl:Thermostat object to effect temperature control based on zone air humidity conditions.",
    "min_fields": 2.0
}
```
