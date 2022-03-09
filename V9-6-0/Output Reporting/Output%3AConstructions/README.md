```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "details_type_1": {
                    "type": "string",
                    "enum": [
                        "Constructions",
                        "Materials"
                    ]
                },
                "details_type_2": {
                    "type": "string",
                    "enum": [
                        "Constructions",
                        "Materials"
                    ]
                }
            }
        }
    },
    "group": "Output Reporting",
    "legacy_idd": {
        "field_info": {
            "details_type_1": {
                "field_name": "Details Type 1",
                "field_type": "a"
            },
            "details_type_2": {
                "field_name": "Details Type 2",
                "field_type": "a"
            }
        },
        "fields": [
            "details_type_1",
            "details_type_2"
        ],
        "alphas": {
            "fields": [
                "details_type_1",
                "details_type_2"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "Adds a report to the eio output file which shows details for each construction, including overall properties, a list of material layers, and calculated results related to conduction transfer functions.",
    "format": "singleLine"
}
```
