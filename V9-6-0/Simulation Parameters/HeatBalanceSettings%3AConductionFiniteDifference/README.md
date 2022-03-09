```
{
    "HeatBalanceSettings:ConductionFiniteDifference": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "difference_scheme": {
                        "type": "string",
                        "enum": [
                            "",
                            "CrankNicholsonSecondOrder",
                            "FullyImplicitFirstOrder"
                        ],
                        "default": "FullyImplicitFirstOrder"
                    },
                    "space_discretization_constant": {
                        "type": "number",
                        "note": "increase or decrease number of nodes",
                        "default": 3.0
                    },
                    "relaxation_factor": {
                        "type": "number",
                        "default": 1.0,
                        "minimum": 0.01,
                        "maximum": 1.0
                    },
                    "inside_face_surface_temperature_convergence_criteria": {
                        "type": "number",
                        "default": 0.002,
                        "minimum": 1e-07,
                        "maximum": 0.01
                    }
                }
            }
        },
        "group": "Simulation Parameters",
        "legacy_idd": {
            "field_info": {
                "difference_scheme": {
                    "field_name": "Difference Scheme",
                    "field_type": "a"
                },
                "space_discretization_constant": {
                    "field_name": "Space Discretization Constant",
                    "field_type": "n"
                },
                "relaxation_factor": {
                    "field_name": "Relaxation Factor",
                    "field_type": "n"
                },
                "inside_face_surface_temperature_convergence_criteria": {
                    "field_name": "Inside Face Surface Temperature Convergence Criteria",
                    "field_type": "n"
                }
            },
            "fields": [
                "difference_scheme",
                "space_discretization_constant",
                "relaxation_factor",
                "inside_face_surface_temperature_convergence_criteria"
            ],
            "alphas": {
                "fields": [
                    "difference_scheme"
                ]
            },
            "numerics": {
                "fields": [
                    "space_discretization_constant",
                    "relaxation_factor",
                    "inside_face_surface_temperature_convergence_criteria"
                ]
            }
        },
        "type": "object",
        "maxProperties": 1,
        "memo": "Determines settings for the Conduction Finite Difference algorithm for surface heat transfer modeling."
    }
}
```
