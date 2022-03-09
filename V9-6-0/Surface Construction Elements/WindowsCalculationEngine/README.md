```
{
    "WindowsCalculationEngine": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "windows_engine": {
                        "type": "string",
                        "enum": [
                            "",
                            "BuiltInWindowsModel",
                            "ExternalWindowsModel"
                        ],
                        "default": "BuiltInWindowsModel"
                    }
                }
            }
        },
        "group": "Surface Construction Elements",
        "legacy_idd": {
            "field_info": {
                "windows_engine": {
                    "field_name": "Windows engine",
                    "field_type": "a"
                }
            },
            "fields": [
                "windows_engine"
            ],
            "alphas": {
                "fields": [
                    "windows_engine"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "Describes which window model will be used in calculations. Built in windows model will use algorithms that are part of EnergyPlus, while ExternalWindowsModel will use Windows-CalcEngine library to perform optical and thermal performances of windows and doors."
    }
}
```
