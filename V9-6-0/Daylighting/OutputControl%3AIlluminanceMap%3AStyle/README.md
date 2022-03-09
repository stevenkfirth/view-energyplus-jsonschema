```
{
    "OutputControl:IlluminanceMap:Style": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "column_separator": {
                        "type": "string",
                        "enum": [
                            "",
                            "Comma",
                            "Fixed",
                            "Tab"
                        ],
                        "default": "Comma"
                    }
                }
            }
        },
        "group": "Daylighting",
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
        "memo": "default style for the Daylighting Illuminance Map is comma -- this works well for importing into spreadsheet programs such as Excel(tm) but not so well for word processing programs -- there tab may be a better choice. fixed puts spaces between the \"columns\""
    }
}
```
