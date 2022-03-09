```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "water_vapor_diffusion_resistance_factor": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "note": "Ratio of water vapor permeability of stagnant air to water vapor permeability of material"
                },
                "moisture_equation_coefficient_a": {
                    "type": "number",
                    "units": "dimensionless"
                },
                "moisture_equation_coefficient_b": {
                    "type": "number",
                    "units": "dimensionless"
                },
                "moisture_equation_coefficient_c": {
                    "type": "number",
                    "units": "dimensionless"
                },
                "moisture_equation_coefficient_d": {
                    "type": "number",
                    "units": "dimensionless"
                },
                "surface_layer_penetration_depth": {
                    "units": "m",
                    "ip-units": "in",
                    "default": "Autocalculate",
                    "anyOf": [
                        {
                            "type": "number",
                            "exclusiveMinimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "",
                                "Autocalculate"
                            ]
                        }
                    ]
                },
                "deep_layer_penetration_depth": {
                    "units": "m",
                    "ip-units": "in",
                    "default": "Autocalculate",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "",
                                "Autocalculate"
                            ]
                        }
                    ]
                },
                "coating_layer_thickness": {
                    "type": "number",
                    "units": "m",
                    "ip-units": "in",
                    "minimum": 0.0
                },
                "coating_layer_water_vapor_diffusion_resistance_factor": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "note": "The coating's resistance to water vapor diffusion relative to the resistance to water vapor diffusion in stagnant air (see Water Vapor Diffusion Resistance Factor above)."
                }
            },
            "required": [
                "water_vapor_diffusion_resistance_factor",
                "moisture_equation_coefficient_a",
                "moisture_equation_coefficient_b",
                "moisture_equation_coefficient_c",
                "moisture_equation_coefficient_d",
                "coating_layer_thickness",
                "coating_layer_water_vapor_diffusion_resistance_factor"
            ]
        }
    },
    "group": "Surface Construction Elements",
    "name": {
        "type": "string",
        "is_required": true,
        "data_type": "object_list",
        "object_list": [
            "MaterialName"
        ],
        "note": "Material Name that the moisture properties will be added to. Additional material properties required to perform the EMPD model. Effective Mean Penetration Depth (EMPD)"
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "water_vapor_diffusion_resistance_factor": {
                "field_name": "Water Vapor Diffusion Resistance Factor",
                "field_type": "n"
            },
            "moisture_equation_coefficient_a": {
                "field_name": "Moisture Equation Coefficient a",
                "field_type": "n"
            },
            "moisture_equation_coefficient_b": {
                "field_name": "Moisture Equation Coefficient b",
                "field_type": "n"
            },
            "moisture_equation_coefficient_c": {
                "field_name": "Moisture Equation Coefficient c",
                "field_type": "n"
            },
            "moisture_equation_coefficient_d": {
                "field_name": "Moisture Equation Coefficient d",
                "field_type": "n"
            },
            "surface_layer_penetration_depth": {
                "field_name": "Surface Layer Penetration Depth",
                "field_type": "n"
            },
            "deep_layer_penetration_depth": {
                "field_name": "Deep Layer Penetration Depth",
                "field_type": "n"
            },
            "coating_layer_thickness": {
                "field_name": "Coating Layer Thickness",
                "field_type": "n"
            },
            "coating_layer_water_vapor_diffusion_resistance_factor": {
                "field_name": "Coating Layer Water Vapor Diffusion Resistance Factor",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "water_vapor_diffusion_resistance_factor",
            "moisture_equation_coefficient_a",
            "moisture_equation_coefficient_b",
            "moisture_equation_coefficient_c",
            "moisture_equation_coefficient_d",
            "surface_layer_penetration_depth",
            "deep_layer_penetration_depth",
            "coating_layer_thickness",
            "coating_layer_water_vapor_diffusion_resistance_factor"
        ],
        "alphas": {
            "fields": [
                "name"
            ]
        },
        "numerics": {
            "fields": [
                "water_vapor_diffusion_resistance_factor",
                "moisture_equation_coefficient_a",
                "moisture_equation_coefficient_b",
                "moisture_equation_coefficient_c",
                "moisture_equation_coefficient_d",
                "surface_layer_penetration_depth",
                "deep_layer_penetration_depth",
                "coating_layer_thickness",
                "coating_layer_water_vapor_diffusion_resistance_factor"
            ]
        }
    },
    "type": "object",
    "memo": "Additional properties for moisture using EMPD procedure HeatBalanceAlgorithm choice=MoisturePenetrationDepthConductionTransferFunction only Has no effect with other HeatBalanceAlgorithm solution algorithms",
    "min_fields": 10.0
}
```
