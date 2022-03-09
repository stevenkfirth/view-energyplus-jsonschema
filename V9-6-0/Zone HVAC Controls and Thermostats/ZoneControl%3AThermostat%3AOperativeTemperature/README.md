```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "thermostat_name": {
                    "type": "string",
                    "note": "Enter the name of a ZoneControl:Thermostat object. This object modifies a ZoneControl:Thermostat object to add a radiative fraction.",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneControlThermostaticNames"
                    ]
                },
                "radiative_fraction_input_mode": {
                    "type": "string",
                    "enum": [
                        "Constant",
                        "Scheduled"
                    ]
                },
                "fixed_radiative_fraction": {
                    "type": "number",
                    "minimum": 0.0,
                    "exclusiveMaximum": 0.9
                },
                "radiative_fraction_schedule_name": {
                    "type": "string",
                    "note": "Schedule values of 0.0 indicate no operative temperature control",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "adaptive_comfort_model_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "AdaptiveASH5580PercentUpperLine",
                        "AdaptiveASH5590PercentUpperLine",
                        "AdaptiveASH55CentralLine",
                        "AdaptiveCEN15251CategoryIIIUpperLine",
                        "AdaptiveCEN15251CategoryIIUpperLine",
                        "AdaptiveCEN15251CategoryIUpperLine",
                        "AdaptiveCEN15251CentralLine",
                        "None"
                    ],
                    "default": "None",
                    "note": "the cooling setpoint temperature schedule of the referenced thermostat will be adjusted based on the selected adaptive comfort model type"
                }
            },
            "required": [
                "thermostat_name",
                "radiative_fraction_input_mode"
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
            "radiative_fraction_input_mode": {
                "field_name": "Radiative Fraction Input Mode",
                "field_type": "a"
            },
            "fixed_radiative_fraction": {
                "field_name": "Fixed Radiative Fraction",
                "field_type": "n"
            },
            "radiative_fraction_schedule_name": {
                "field_name": "Radiative Fraction Schedule Name",
                "field_type": "a"
            },
            "adaptive_comfort_model_type": {
                "field_name": "Adaptive Comfort Model Type",
                "field_type": "a"
            }
        },
        "fields": [
            "thermostat_name",
            "radiative_fraction_input_mode",
            "fixed_radiative_fraction",
            "radiative_fraction_schedule_name",
            "adaptive_comfort_model_type"
        ],
        "alphas": {
            "fields": [
                "thermostat_name",
                "radiative_fraction_input_mode",
                "radiative_fraction_schedule_name",
                "adaptive_comfort_model_type"
            ]
        },
        "numerics": {
            "fields": [
                "fixed_radiative_fraction"
            ]
        }
    },
    "type": "object",
    "memo": "This object can be used with the ZoneList option on a thermostat or with one of the zones on that list (but you won't be able to use the object list to pick only one of those zones. Thermostat names are <Zone Name> <global Thermostat name> internally."
}
```
