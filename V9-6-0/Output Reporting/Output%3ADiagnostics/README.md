```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "diagnostics": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "key": {
                                "type": "string",
                                "enum": [
                                    "DisplayAdvancedReportVariables",
                                    "DisplayAllWarnings",
                                    "DisplayExtraWarnings",
                                    "DisplayUnusedObjects",
                                    "DisplayUnusedSchedules",
                                    "DisplayWeatherMissingDataWarnings",
                                    "DisplayZoneAirHeatBalanceOffBalance",
                                    "DoNotMirrorAttachedShading",
                                    "DoNotMirrorDetachedShading",
                                    "ReportDetailedWarmupConvergence",
                                    "ReportDuringHVACSizingSimulation",
                                    "ReportDuringWarmup"
                                ]
                            }
                        },
                        "type": "object"
                    }
                }
            }
        }
    },
    "group": "Output Reporting",
    "legacy_idd": {
        "field_info": {
            "key": {
                "field_name": "Key",
                "field_type": "a"
            }
        },
        "fields": [],
        "alphas": {
            "fields": [],
            "extensions": [
                "key"
            ]
        },
        "numerics": {
            "fields": []
        },
        "extensibles": [
            "key"
        ],
        "extension": "diagnostics"
    },
    "type": "object",
    "maxProperties": 1,
    "memo": "Special keys to produce certain warning messages or effect certain simulation characteristics.",
    "extensible_size": 1.0
}
```
