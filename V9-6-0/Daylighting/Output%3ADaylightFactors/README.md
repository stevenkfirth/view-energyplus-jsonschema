```
{
    "Output:DaylightFactors": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "reporting_days": {
                        "type": "string",
                        "enum": [
                            "AllShadowCalculationDays",
                            "SizingDays"
                        ]
                    }
                },
                "required": [
                    "reporting_days"
                ]
            }
        },
        "group": "Daylighting",
        "legacy_idd": {
            "field_info": {
                "reporting_days": {
                    "field_name": "Reporting Days",
                    "field_type": "a"
                }
            },
            "fields": [
                "reporting_days"
            ],
            "alphas": {
                "fields": [
                    "reporting_days"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "Reports hourly daylight factors for each exterior window for four sky types (clear, turbid clear, intermediate, and overcast).",
        "format": "singleLine"
    }
}
```
