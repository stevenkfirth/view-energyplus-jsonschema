```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "option_type": {
                    "type": "string",
                    "enum": [
                        "Simple",
                        "SimpleAndTabular"
                    ]
                },
                "unit_conversion_for_tabular_data": {
                    "type": "string",
                    "note": "Unit conversion option used when writing SQLite Tabular Data This option applies to TabularData and TabularDatawithString in the SQLite file",
                    "enum": [
                        "",
                        "InchPound",
                        "JtoGJ",
                        "JtoKWH",
                        "JtoMJ",
                        "None",
                        "UseOutputControlTableStyle"
                    ],
                    "default": "UseOutputControlTableStyle"
                }
            }
        }
    },
    "group": "Output Reporting",
    "legacy_idd": {
        "field_info": {
            "option_type": {
                "field_name": "Option Type",
                "field_type": "a"
            },
            "unit_conversion_for_tabular_data": {
                "field_name": "Unit Conversion for Tabular Data",
                "field_type": "a"
            }
        },
        "fields": [
            "option_type",
            "unit_conversion_for_tabular_data"
        ],
        "alphas": {
            "fields": [
                "option_type",
                "unit_conversion_for_tabular_data"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "maxProperties": 1,
    "memo": "Output from EnergyPlus can be written to an SQLite format file."
}
```
