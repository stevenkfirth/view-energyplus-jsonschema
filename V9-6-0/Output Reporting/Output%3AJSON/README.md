```
{
    "Output:JSON": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "option_type": {
                        "type": "string",
                        "enum": [
                            "TimeSeries",
                            "TimeSeriesAndTabular"
                        ]
                    },
                    "output_json": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_cbor": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No"
                    },
                    "output_messagepack": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No"
                    }
                },
                "required": [
                    "option_type"
                ]
            }
        },
        "group": "Output Reporting",
        "legacy_idd": {
            "field_info": {
                "option_type": {
                    "field_name": "Option Type",
                    "field_type": "a"
                },
                "output_json": {
                    "field_name": "Output JSON",
                    "field_type": "a"
                },
                "output_cbor": {
                    "field_name": "Output CBOR",
                    "field_type": "a"
                },
                "output_messagepack": {
                    "field_name": "Output MessagePack",
                    "field_type": "a"
                }
            },
            "fields": [
                "option_type",
                "output_json",
                "output_cbor",
                "output_messagepack"
            ],
            "alphas": {
                "fields": [
                    "option_type",
                    "output_json",
                    "output_cbor",
                    "output_messagepack"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "maxProperties": 1,
        "memo": "Output from EnergyPlus can be written to JSON format files."
    }
}
```
