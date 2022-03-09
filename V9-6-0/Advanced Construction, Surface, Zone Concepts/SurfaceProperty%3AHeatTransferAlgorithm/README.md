```
{
    "SurfaceProperty:HeatTransferAlgorithm": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "surface_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "SurfaceNames"
                        ]
                    },
                    "algorithm": {
                        "type": "string",
                        "enum": [
                            "",
                            "CombinedHeatAndMoistureFiniteElement",
                            "ConductionFiniteDifference",
                            "ConductionTransferFunction",
                            "MoisturePenetrationDepthConductionTransferFunction"
                        ],
                        "default": "ConductionTransferFunction"
                    }
                },
                "required": [
                    "surface_name"
                ]
            }
        },
        "group": "Advanced Construction, Surface, Zone Concepts",
        "legacy_idd": {
            "field_info": {
                "surface_name": {
                    "field_name": "Surface Name",
                    "field_type": "a"
                },
                "algorithm": {
                    "field_name": "Algorithm",
                    "field_type": "a"
                }
            },
            "fields": [
                "surface_name",
                "algorithm"
            ],
            "alphas": {
                "fields": [
                    "surface_name",
                    "algorithm"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "Determines which Heat Balance Algorithm will be used for a specific surface Allows selectively overriding the global setting in HeatBalanceAlgorithm CTF (Conduction Transfer Functions), EMPD (Effective Moisture Penetration Depth with Conduction Transfer Functions). Advanced/Research Usage: CondFD (Conduction Finite Difference) Advanced/Research Usage: HAMT (Combined Heat And Moisture Finite Element)",
        "min_fields": 2.0
    }
}
```
