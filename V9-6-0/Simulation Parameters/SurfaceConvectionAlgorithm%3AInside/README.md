```
{
    "SurfaceConvectionAlgorithm:Inside": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "algorithm": {
                        "type": "string",
                        "enum": [
                            "",
                            "ASTMC1340",
                            "AdaptiveConvectionAlgorithm",
                            "CeilingDiffuser",
                            "Simple",
                            "TARP"
                        ],
                        "default": "TARP",
                        "note": "Simple = constant value natural convection (ASHRAE) TARP = variable natural convection based on temperature difference (ASHRAE, Walton) CeilingDiffuser = ACH-based forced and mixed convection correlations for ceiling diffuser configuration with simple natural convection limit AdaptiveConvectionAlgorithm = dynamic selection of convection models based on conditions ASTMC1340 = mixed convection correlations based on heat flow direction, surface tilt angle, surface characteristic length, and air speed past the surface."
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
        "memo": "Default indoor surface heat transfer convection algorithm to be used for all zones",
        "format": "singleLine"
    }
}
```
