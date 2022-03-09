```
{
    "SurfaceProperty:HeatTransferAlgorithm:Construction": {
        "patternProperties": {
            ".*": {
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
                    "construction_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ConstructionNames"
                        ]
                    }
                },
                "required": [
                    "construction_name"
                ]
            }
        },
        "group": "Advanced Construction, Surface, Zone Concepts",
        "name": {
            "type": "string"
        },
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
                "construction_name": {
                    "field_name": "Construction Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "algorithm",
                "construction_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "algorithm",
                    "construction_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "Determines which Heat Balance Algorithm will be used for surfaces that have a specific type of construction Allows selectively overriding the global setting in HeatBalanceAlgorithm CTF (Conduction Transfer Functions), EMPD (Effective Moisture Penetration Depth with Conduction Transfer Functions). Advanced/Research Usage: CondFD (Conduction Finite Difference) Advanced/Research Usage: HAMT (Combined Heat And Moisture Finite Element)",
        "min_fields": 3.0
    }
}
```
