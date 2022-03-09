```
{
    "SurfaceProperty:OtherSideConditionsModel": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "type_of_modeling": {
                        "type": "string",
                        "enum": [
                            "",
                            "ConvectiveUnderwater",
                            "GapConvectionRadiation",
                            "GroundCoupledSurface",
                            "UndergroundPipingSystemSurface"
                        ],
                        "note": "GapConvectionRadiation provides boundary conditions for convection and linearized thermal radiation across a gap or cavity on the other side of the surface that are modeled separately. UndergroundPipingSystemSurface provides boundary conditions for surfaces in contact with PipingSystem:Underground domains GroundCoupledSurface provides boundary conditions for surfaces in contact with GroundDomain objects ConvectiveUnderwater provides a connection between a surface and an underwater boundary condition defined using a SurfaceProperty:Underwater object",
                        "default": "GapConvectionRadiation"
                    }
                }
            }
        },
        "group": "Advanced Construction, Surface, Zone Concepts",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "OSCMNames",
                "OutFaceEnvNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "type_of_modeling": {
                    "field_name": "Type of Modeling",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "type_of_modeling"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "type_of_modeling"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "This object sets up modifying the other side conditions for a surface from other model results."
    }
}
```
