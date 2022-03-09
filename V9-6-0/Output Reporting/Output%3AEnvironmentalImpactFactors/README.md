```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "reporting_frequency": {
                    "type": "string",
                    "note": "Timestep refers to the zone Timestep/Number of Timesteps in hour value RunPeriod and Environment are the same. Detailed is not a valid choice.",
                    "enum": [
                        "Annual",
                        "Daily",
                        "Environment",
                        "Hourly",
                        "Monthly",
                        "RunPeriod",
                        "Timestep"
                    ]
                }
            }
        }
    },
    "group": "Output Reporting",
    "legacy_idd": {
        "field_info": {
            "reporting_frequency": {
                "field_name": "Reporting Frequency",
                "field_type": "a"
            }
        },
        "fields": [
            "reporting_frequency"
        ],
        "alphas": {
            "fields": [
                "reporting_frequency"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "This is used to Automatically report the facility meters and turn on the Environmental Impact Report calculations for all of the Environmental Factors."
}
```
