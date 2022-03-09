```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "column_separator": {
                    "type": "string",
                    "enum": [
                        "",
                        "All",
                        "Comma",
                        "CommaAndHTML",
                        "CommaAndXML",
                        "Fixed",
                        "HTML",
                        "Tab",
                        "TabAndHTML",
                        "XML",
                        "XMLandHTML"
                    ],
                    "default": "Comma"
                },
                "unit_conversion": {
                    "type": "string",
                    "enum": [
                        "",
                        "InchPound",
                        "JtoGJ",
                        "JtoKWH",
                        "JtoMJ",
                        "None"
                    ],
                    "default": "None"
                }
            }
        }
    },
    "group": "Output Reporting",
    "legacy_idd": {
        "field_info": {
            "column_separator": {
                "field_name": "Column Separator",
                "field_type": "a"
            },
            "unit_conversion": {
                "field_name": "Unit Conversion",
                "field_type": "a"
            }
        },
        "fields": [
            "column_separator",
            "unit_conversion"
        ],
        "alphas": {
            "fields": [
                "column_separator",
                "unit_conversion"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "maxProperties": 1,
    "memo": "default style for the OutputControl:Table:Style is comma -- this works well for importing into spreadsheet programs such as Excel(tm) but not so well for word processing programs -- there tab may be a better choice. fixed puts spaces between the \"columns\". HTML produces tables in HTML. XML produces an XML file. note - if no OutputControl:Table:Style is included, the defaults are comma and None."
}
```
