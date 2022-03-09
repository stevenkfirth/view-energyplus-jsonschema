```
{
    "SurfaceConvectionAlgorithm:Outside": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "algorithm": {
                        "type": "string",
                        "enum": [
                            "",
                            "AdaptiveConvectionAlgorithm",
                            "DOE-2",
                            "MoWiTT",
                            "SimpleCombined",
                            "TARP"
                        ],
                        "default": "DOE-2",
                        "note": "SimpleCombined = Combined radiation and convection coefficient using simple ASHRAE model TARP = correlation from models developed by ASHRAE, Walton, and Sparrow et. al. MoWiTT = correlation from measurements by Klems and Yazdanian for smooth surfaces DOE-2 = correlation from measurements by Klems and Yazdanian for rough surfaces AdaptiveConvectionAlgorithm = dynamic selection of correlations based on conditions"
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
        "memo": "Default outside surface heat transfer convection algorithm to be used for all zones",
        "format": "singleLine"
    }
}
```
