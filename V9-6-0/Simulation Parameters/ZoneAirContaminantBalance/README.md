```
{
    "ZoneAirContaminantBalance": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "carbon_dioxide_concentration": {
                        "type": "string",
                        "note": "If Yes, CO2 simulation will be performed.",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No"
                    },
                    "outdoor_carbon_dioxide_schedule_name": {
                        "type": "string",
                        "note": "Schedule values should be in parts per million (ppm)",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "generic_contaminant_concentration": {
                        "type": "string",
                        "note": "If Yes, generic contaminant simulation will be performed.",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No"
                    },
                    "outdoor_generic_contaminant_schedule_name": {
                        "type": "string",
                        "note": "Schedule values should be generic contaminant concentration in parts per million (ppm)",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    }
                }
            }
        },
        "group": "Simulation Parameters",
        "legacy_idd": {
            "field_info": {
                "carbon_dioxide_concentration": {
                    "field_name": "Carbon Dioxide Concentration",
                    "field_type": "a"
                },
                "outdoor_carbon_dioxide_schedule_name": {
                    "field_name": "Outdoor Carbon Dioxide Schedule Name",
                    "field_type": "a"
                },
                "generic_contaminant_concentration": {
                    "field_name": "Generic Contaminant Concentration",
                    "field_type": "a"
                },
                "outdoor_generic_contaminant_schedule_name": {
                    "field_name": "Outdoor Generic Contaminant Schedule Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "carbon_dioxide_concentration",
                "outdoor_carbon_dioxide_schedule_name",
                "generic_contaminant_concentration",
                "outdoor_generic_contaminant_schedule_name"
            ],
            "alphas": {
                "fields": [
                    "carbon_dioxide_concentration",
                    "outdoor_carbon_dioxide_schedule_name",
                    "generic_contaminant_concentration",
                    "outdoor_generic_contaminant_schedule_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "maxProperties": 1,
        "memo": "Determines which contaminant concentration will be simulates.",
        "format": "singleLine"
    }
}
```
