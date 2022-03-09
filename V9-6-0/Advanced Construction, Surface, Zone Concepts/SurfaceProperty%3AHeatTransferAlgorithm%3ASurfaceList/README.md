```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
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
                },
                "surface": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "surface_name": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "SurfaceNames"
                                ]
                            }
                        },
                        "type": "object",
                        "required": [
                            "surface_name"
                        ]
                    }
                }
            }
        }
    },
    "group": "Advanced Construction, Surface, Zone Concepts",
    "name": {
        "type": "string",
        "is_required": true
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "algorithm": {
                "field_name": "Algorithm",
                "field_type": "a"
            },
            "surface_name": {
                "field_name": "Surface Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "algorithm"
        ],
        "alphas": {
            "fields": [
                "name",
                "algorithm"
            ],
            "extensions": [
                "surface_name"
            ]
        },
        "numerics": {
            "fields": []
        },
        "extensibles": [
            "surface_name"
        ],
        "extension": "surface"
    },
    "type": "object",
    "memo": "Determines which Heat Balance Algorithm will be used for a list of surfaces Allows selectively overriding the global setting in HeatBalanceAlgorithm CTF (Conduction Transfer Functions), EMPD (Effective Moisture Penetration Depth with Conduction Transfer Functions). Advanced/Research Usage: CondFD (Conduction Finite Difference) Advanced/Research Usage: HAMT (Combined Heat And Moisture Finite Element)",
    "min_fields": 3.0,
    "extensible_size": 1.0
}
```
