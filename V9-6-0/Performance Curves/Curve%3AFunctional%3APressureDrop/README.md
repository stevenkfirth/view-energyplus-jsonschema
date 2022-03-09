```
{
    "Curve:Functional:PressureDrop": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "diameter": {
                        "type": "number",
                        "units": "m",
                        "note": "\"D\" in above expression, used to also calculate local velocity",
                        "exclusiveMinimum": 0.0
                    },
                    "minor_loss_coefficient": {
                        "type": "number",
                        "units": "dimensionless",
                        "note": "\"K\" in above expression",
                        "exclusiveMinimum": 0.0
                    },
                    "length": {
                        "type": "number",
                        "units": "m",
                        "note": "\"L\" in above expression",
                        "exclusiveMinimum": 0.0
                    },
                    "roughness": {
                        "type": "number",
                        "units": "m",
                        "note": "This will be used to calculate \"f\" from Moody-chart approximations",
                        "exclusiveMinimum": 0.0
                    },
                    "fixed_friction_factor": {
                        "type": "number",
                        "note": "Optional way to set a constant value for \"f\", instead of using internal Moody-chart approximations",
                        "exclusiveMinimum": 0.0
                    }
                },
                "required": [
                    "diameter"
                ]
            }
        },
        "group": "Performance Curves",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "UnivariateFunctions"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "diameter": {
                    "field_name": "Diameter",
                    "field_type": "n"
                },
                "minor_loss_coefficient": {
                    "field_name": "Minor Loss Coefficient",
                    "field_type": "n"
                },
                "length": {
                    "field_name": "Length",
                    "field_type": "n"
                },
                "roughness": {
                    "field_name": "Roughness",
                    "field_type": "n"
                },
                "fixed_friction_factor": {
                    "field_name": "Fixed Friction Factor",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "diameter",
                "minor_loss_coefficient",
                "length",
                "roughness",
                "fixed_friction_factor"
            ],
            "alphas": {
                "fields": [
                    "name"
                ]
            },
            "numerics": {
                "fields": [
                    "diameter",
                    "minor_loss_coefficient",
                    "length",
                    "roughness",
                    "fixed_friction_factor"
                ]
            }
        },
        "type": "object",
        "memo": "Sets up curve information for minor loss and/or friction calculations in plant pressure simulations Expression: DeltaP = {K + f*(L/D)} * (rho * V^2) / 2",
        "min_fields": 5.0
    }
}
```
