```
{
    "ZoneAirHeatBalanceAlgorithm": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "algorithm": {
                        "type": "string",
                        "enum": [
                            "",
                            "AnalyticalSolution",
                            "EulerMethod",
                            "ThirdOrderBackwardDifference"
                        ],
                        "default": "ThirdOrderBackwardDifference"
                    }
                }
            }
        },
        "group": "Simulation Parameters",
        "legacy_idd": {
            "field_info": {
                "algorithm": {
                    "field_name": "Algorithm",
                    "field_type": "a"
                }
            },
            "fields": [
                "algorithm"
            ],
            "alphas": {
                "fields": [
                    "algorithm"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "maxProperties": 1,
        "memo": "Determines which algorithm will be used to solve the zone air heat balance.",
        "min_fields": 1.0,
        "format": "singleLine"
    }
}
```
