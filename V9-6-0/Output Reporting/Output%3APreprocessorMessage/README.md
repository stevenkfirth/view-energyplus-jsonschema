```
{
    "Output:PreprocessorMessage": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "preprocessor_name": {
                        "type": "string",
                        "retaincase": true
                    },
                    "error_severity": {
                        "type": "string",
                        "note": "Depending on type, InputProcessor may terminate the program.",
                        "enum": [
                            "Fatal",
                            "Information",
                            "Severe",
                            "Warning"
                        ],
                        "retaincase": true
                    },
                    "message_line_1": {
                        "type": "string",
                        "retaincase": true
                    },
                    "message_line_2": {
                        "type": "string",
                        "retaincase": true
                    },
                    "message_line_3": {
                        "type": "string",
                        "retaincase": true
                    },
                    "message_line_4": {
                        "type": "string",
                        "retaincase": true
                    },
                    "message_line_5": {
                        "type": "string",
                        "retaincase": true
                    },
                    "message_line_6": {
                        "type": "string",
                        "retaincase": true
                    },
                    "message_line_7": {
                        "type": "string",
                        "retaincase": true
                    },
                    "message_line_8": {
                        "type": "string",
                        "retaincase": true
                    },
                    "message_line_9": {
                        "type": "string",
                        "retaincase": true
                    },
                    "message_line_10": {
                        "type": "string",
                        "retaincase": true
                    }
                }
            }
        },
        "group": "Output Reporting",
        "legacy_idd": {
            "field_info": {
                "preprocessor_name": {
                    "field_name": "Preprocessor Name",
                    "field_type": "a"
                },
                "error_severity": {
                    "field_name": "Error Severity",
                    "field_type": "a"
                },
                "message_line_1": {
                    "field_name": "Message Line 1",
                    "field_type": "a"
                },
                "message_line_2": {
                    "field_name": "Message Line 2",
                    "field_type": "a"
                },
                "message_line_3": {
                    "field_name": "Message Line 3",
                    "field_type": "a"
                },
                "message_line_4": {
                    "field_name": "Message Line 4",
                    "field_type": "a"
                },
                "message_line_5": {
                    "field_name": "Message Line 5",
                    "field_type": "a"
                },
                "message_line_6": {
                    "field_name": "Message Line 6",
                    "field_type": "a"
                },
                "message_line_7": {
                    "field_name": "Message Line 7",
                    "field_type": "a"
                },
                "message_line_8": {
                    "field_name": "Message Line 8",
                    "field_type": "a"
                },
                "message_line_9": {
                    "field_name": "Message Line 9",
                    "field_type": "a"
                },
                "message_line_10": {
                    "field_name": "Message Line 10",
                    "field_type": "a"
                }
            },
            "fields": [
                "preprocessor_name",
                "error_severity",
                "message_line_1",
                "message_line_2",
                "message_line_3",
                "message_line_4",
                "message_line_5",
                "message_line_6",
                "message_line_7",
                "message_line_8",
                "message_line_9",
                "message_line_10"
            ],
            "alphas": {
                "fields": [
                    "preprocessor_name",
                    "error_severity",
                    "message_line_1",
                    "message_line_2",
                    "message_line_3",
                    "message_line_4",
                    "message_line_5",
                    "message_line_6",
                    "message_line_7",
                    "message_line_8",
                    "message_line_9",
                    "message_line_10"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "This object does not come from a user input. This is generated by a pre-processor so that various conditions can be gracefully passed on by the InputProcessor."
    }
}
```
