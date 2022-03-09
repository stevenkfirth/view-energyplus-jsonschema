```
{
    "Output:DebuggingData": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "report_debugging_data": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No"
                    },
                    "report_during_warmup": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No"
                    }
                }
            }
        },
        "group": "Output Reporting",
        "legacy_idd": {
            "field_info": {
                "report_debugging_data": {
                    "field_name": "Report Debugging Data",
                    "field_type": "a"
                },
                "report_during_warmup": {
                    "field_name": "Report During Warmup",
                    "field_type": "a"
                }
            },
            "fields": [
                "report_debugging_data",
                "report_during_warmup"
            ],
            "alphas": {
                "fields": [
                    "report_debugging_data",
                    "report_during_warmup"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "maxProperties": 1,
        "memo": "switch eplusout.dbg file on or off"
    }
}
```
