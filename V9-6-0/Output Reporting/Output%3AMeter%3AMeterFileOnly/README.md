```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "key_name": {
                    "type": "string",
                    "data_type": "external_list",
                    "external_list": [
                        "autoRDDmeter"
                    ],
                    "note": "Form is EnergyUseType:..., e.g. Electricity:* for all Electricity meters or EndUse:..., e.g. GeneralLights:* for all General Lights Output:Meter:MeterFileOnly puts results on the eplusout.mtr file only"
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
                    "note": "Timestep refers to the zone Timestep/Number of Timesteps in hour value RunPeriod and Environment are the same",
                    "default": "Hourly"
                }
            },
            "required": [
                "key_name"
            ]
        }
    },
    "group": "Output Reporting",
    "legacy_idd": {
        "field_info": {
            "key_name": {
                "field_name": "Key Name",
                "field_type": "a"
            },
            "reporting_frequency": {
                "field_name": "Reporting Frequency",
                "field_type": "a"
            }
        },
        "fields": [
            "key_name",
            "reporting_frequency"
        ],
        "alphas": {
            "fields": [
                "key_name",
                "reporting_frequency"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "Each Output:Meter:MeterFileOnly command picks meters to be put only onto meter file (.mtr). Not all meters are reported in every simulation. A list of meters that can be reported a list of meters that can be reported are available after a run on the meter dictionary file (.mdd) if the Output:VariableDictionary has been requested.",
    "format": "singleLine"
}
```
