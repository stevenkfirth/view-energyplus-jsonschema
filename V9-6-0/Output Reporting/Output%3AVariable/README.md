```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "key_value": {
                    "type": "string",
                    "retaincase": true,
                    "default": "*",
                    "note": "use '*' (without quotes) to apply this variable to all keys"
                },
                "variable_name": {
                    "type": "string",
                    "data_type": "external_list",
                    "external_list": [
                        "autoRDDvariable"
                    ]
                },
                "reporting_frequency": {
                    "type": "string",
                    "enum": [
                        "",
                        "Annual",
                        "Daily",
                        "Detailed",
                        "Environment",
                        "Hourly",
                        "Monthly",
                        "RunPeriod",
                        "Timestep"
                    ],
                    "note": "Detailed lists every instance (i.e. HVAC variable timesteps) Timestep refers to the zone Timestep/Number of Timesteps in hour value RunPeriod and Environment are the same",
                    "default": "Hourly"
                },
                "schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                }
            },
            "required": [
                "variable_name"
            ]
        }
    },
    "group": "Output Reporting",
    "legacy_idd": {
        "field_info": {
            "key_value": {
                "field_name": "Key Value",
                "field_type": "a"
            },
            "variable_name": {
                "field_name": "Variable Name",
                "field_type": "a"
            },
            "reporting_frequency": {
                "field_name": "Reporting Frequency",
                "field_type": "a"
            },
            "schedule_name": {
                "field_name": "Schedule Name",
                "field_type": "a"
            }
        },
        "fields": [
            "key_value",
            "variable_name",
            "reporting_frequency",
            "schedule_name"
        ],
        "alphas": {
            "fields": [
                "key_value",
                "variable_name",
                "reporting_frequency",
                "schedule_name"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "each Output:Variable command picks variables to be put onto the standard output file (.eso) some variables may not be reported for every simulation. a list of variables that can be reported are available after a run on the report dictionary file (.rdd) if the Output:VariableDictionary has been requested.",
    "format": "singleLine"
}
```
