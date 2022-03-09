```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "column_separator": {
                    "type": "string",
                    "enum": [
                        "Comma",
                        "Fixed",
                        "Tab"
                    ]
                }
            },
            "required": [
                "column_separator"
            ]
        }
    },
    "group": "HVAC Design Objects",
    "legacy_idd": {
        "field_info": {
            "column_separator": {
                "field_name": "Column Separator",
                "field_type": "a"
            }
        },
        "fields": [
            "column_separator"
        ],
        "alphas": {
            "fields": [
                "column_separator"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "maxProperties": 1,
    "memo": "Default style for the Sizing output files is comma -- this works well for importing into spreadsheet programs such as Excel(tm) but not so well for word processing programs -- there tab may be a better choice. Fixed puts spaces between the \"columns\""
}
```
