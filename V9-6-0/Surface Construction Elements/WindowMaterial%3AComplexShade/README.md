```
{
    "WindowMaterial:ComplexShade": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "layer_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "BSDF",
                            "OtherShadingType",
                            "Perforated",
                            "VenetianHorizontal",
                            "VenetianVertical",
                            "Woven"
                        ],
                        "default": "OtherShadingType"
                    },
                    "thickness": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "default": 0.002
                    },
                    "conductivity": {
                        "type": "number",
                        "units": "W/m-K",
                        "exclusiveMinimum": 0.0,
                        "default": 1.0
                    },
                    "ir_transmittance": {
                        "type": "number",
                        "maximum": 1.0,
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "front_emissivity": {
                        "type": "number",
                        "maximum": 1.0,
                        "exclusiveMinimum": 0.0,
                        "default": 0.84
                    },
                    "back_emissivity": {
                        "type": "number",
                        "maximum": 1.0,
                        "exclusiveMinimum": 0.0,
                        "default": 0.84
                    },
                    "top_opening_multiplier": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "bottom_opening_multiplier": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "left_side_opening_multiplier": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "right_side_opening_multiplier": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "front_opening_multiplier": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.05
                    },
                    "slat_width": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "default": 0.016
                    },
                    "slat_spacing": {
                        "type": "number",
                        "note": "Distance between adjacent slat faces",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "default": 0.012
                    },
                    "slat_thickness": {
                        "type": "number",
                        "note": "Distance between top and bottom surfaces of slat Slat is assumed to be rectangular in cross section and flat",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "default": 0.0006
                    },
                    "slat_angle": {
                        "type": "number",
                        "units": "deg",
                        "default": 90.0,
                        "minimum": -90.0,
                        "maximum": 90.0
                    },
                    "slat_conductivity": {
                        "type": "number",
                        "units": "W/m-K",
                        "exclusiveMinimum": 0.0,
                        "default": 160.0
                    },
                    "slat_curve": {
                        "type": "number",
                        "note": "this value represents curvature radius of the slat. if the slat is flat use zero. if this value is not zero, then it must be > SlatWidth/2.",
                        "units": "m",
                        "minimum": 0.0,
                        "default": 0.0
                    }
                }
            }
        },
        "group": "Surface Construction Elements",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "WindowComplexShades"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "layer_type": {
                    "field_name": "Layer Type",
                    "field_type": "a"
                },
                "thickness": {
                    "field_name": "Thickness",
                    "field_type": "n"
                },
                "conductivity": {
                    "field_name": "Conductivity",
                    "field_type": "n"
                },
                "ir_transmittance": {
                    "field_name": "IR Transmittance",
                    "field_type": "n"
                },
                "front_emissivity": {
                    "field_name": "Front Emissivity",
                    "field_type": "n"
                },
                "back_emissivity": {
                    "field_name": "Back Emissivity",
                    "field_type": "n"
                },
                "top_opening_multiplier": {
                    "field_name": "Top Opening Multiplier",
                    "field_type": "n"
                },
                "bottom_opening_multiplier": {
                    "field_name": "Bottom Opening Multiplier",
                    "field_type": "n"
                },
                "left_side_opening_multiplier": {
                    "field_name": "Left Side Opening Multiplier",
                    "field_type": "n"
                },
                "right_side_opening_multiplier": {
                    "field_name": "Right Side Opening Multiplier",
                    "field_type": "n"
                },
                "front_opening_multiplier": {
                    "field_name": "Front Opening Multiplier",
                    "field_type": "n"
                },
                "slat_width": {
                    "field_name": "Slat Width",
                    "field_type": "n"
                },
                "slat_spacing": {
                    "field_name": "Slat Spacing",
                    "field_type": "n"
                },
                "slat_thickness": {
                    "field_name": "Slat Thickness",
                    "field_type": "n"
                },
                "slat_angle": {
                    "field_name": "Slat Angle",
                    "field_type": "n"
                },
                "slat_conductivity": {
                    "field_name": "Slat Conductivity",
                    "field_type": "n"
                },
                "slat_curve": {
                    "field_name": "Slat Curve",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "layer_type",
                "thickness",
                "conductivity",
                "ir_transmittance",
                "front_emissivity",
                "back_emissivity",
                "top_opening_multiplier",
                "bottom_opening_multiplier",
                "left_side_opening_multiplier",
                "right_side_opening_multiplier",
                "front_opening_multiplier",
                "slat_width",
                "slat_spacing",
                "slat_thickness",
                "slat_angle",
                "slat_conductivity",
                "slat_curve"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "layer_type"
                ]
            },
            "numerics": {
                "fields": [
                    "thickness",
                    "conductivity",
                    "ir_transmittance",
                    "front_emissivity",
                    "back_emissivity",
                    "top_opening_multiplier",
                    "bottom_opening_multiplier",
                    "left_side_opening_multiplier",
                    "right_side_opening_multiplier",
                    "front_opening_multiplier",
                    "slat_width",
                    "slat_spacing",
                    "slat_thickness",
                    "slat_angle",
                    "slat_conductivity",
                    "slat_curve"
                ]
            }
        },
        "type": "object",
        "memo": "Complex window shading layer thermal properties",
        "min_fields": 12.0
    }
}
```
