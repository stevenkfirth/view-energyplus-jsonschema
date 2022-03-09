```
{
    "SurfaceProperty:HeatTransferAlgorithm:MultipleSurface": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "surface_type": {
                        "type": "string",
                        "enum": [
                            "AllExteriorFloors",
                            "AllExteriorRoofs",
                            "AllExteriorSurfaces",
                            "AllExteriorWalls",
                            "AllGroundContactSurfaces",
                            "AllInteriorCeilings",
                            "AllInteriorFloors",
                            "AllInteriorSurfaces",
                            "AllInteriorWalls"
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
                    "surface_type"
                ]
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
                "surface_type": {
                    "field_name": "Surface Type",
                    "field_type": "a"
                },
                "algorithm": {
                    "field_name": "Algorithm",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "surface_type",
                "algorithm"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "surface_type",
                    "algorithm"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "Determines which Heat Balance Algorithm will be used for a group of surface types Allows selectively overriding the global setting in HeatBalanceAlgorithm CTF (Conduction Transfer Functions), EMPD (Effective Moisture Penetration Depth with Conduction Transfer Functions). Advanced/Research Usage: CondFD (Conduction Finite Difference) Advanced/Research Usage: HAMT (Combined Heat And Moisture Finite Element)",
        "min_fields": 3.0
    }
}
```
