```
{
    "Output:Surfaces:List": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "report_type": {
                        "type": "string",
                        "enum": [
                            "CostInfo",
                            "DecayCurvesFromComponentLoadsSummary",
                            "Details",
                            "DetailsWithVertices",
                            "Lines",
                            "Vertices",
                            "ViewFactorInfo"
                        ]
                    },
                    "report_specifications": {
                        "type": "string",
                        "note": "(IDF, only for Output:Surfaces:List, Lines report -- will print transformed coordinates in IDF style)",
                        "enum": [
                            "IDF"
                        ]
                    }
                },
                "required": [
                    "report_type"
                ]
            }
        },
        "group": "Output Reporting",
        "legacy_idd": {
            "field_info": {
                "report_type": {
                    "field_name": "Report Type",
                    "field_type": "a"
                },
                "report_specifications": {
                    "field_name": "Report Specifications",
                    "field_type": "a"
                }
            },
            "fields": [
                "report_type",
                "report_specifications"
            ],
            "alphas": {
                "fields": [
                    "report_type",
                    "report_specifications"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "Produces a report summarizing the details of surfaces in the eio output file.",
        "format": "singleLine"
    }
}
```
