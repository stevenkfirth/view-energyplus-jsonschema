```
{
    "WindowMaterial:Screen": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "reflected_beam_transmittance_accounting_method": {
                        "type": "string",
                        "note": "Select the method used to account for the beam solar reflected off the material surface.",
                        "enum": [
                            "",
                            "DoNotModel",
                            "ModelAsDiffuse",
                            "ModelAsDirectBeam"
                        ],
                        "default": "ModelAsDiffuse"
                    },
                    "diffuse_solar_reflectance": {
                        "type": "number",
                        "note": "Diffuse reflectance of the screen material over the entire solar radiation spectrum. Assumed to be the same for both sides of the screen.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "exclusiveMaximum": 1.0
                    },
                    "diffuse_visible_reflectance": {
                        "type": "number",
                        "note": "Diffuse visible reflectance of the screen material averaged over the solar spectrum and weighted by the response of the human eye. Assumed to be the same for both sides of the screen.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "exclusiveMaximum": 1.0
                    },
                    "thermal_hemispherical_emissivity": {
                        "type": "number",
                        "note": "Long-wave emissivity of the screen material. Assumed to be the same for both sides of the screen.",
                        "units": "dimensionless",
                        "exclusiveMaximum": 1.0,
                        "exclusiveMinimum": 0.0,
                        "default": 0.9
                    },
                    "conductivity": {
                        "type": "number",
                        "note": "Thermal conductivity of the screen material. Default is for aluminum.",
                        "units": "W/m-K",
                        "exclusiveMinimum": 0.0,
                        "default": 221.0
                    },
                    "screen_material_spacing": {
                        "type": "number",
                        "note": "Spacing assumed to be the same in both directions.",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "ip-units": "in"
                    },
                    "screen_material_diameter": {
                        "type": "number",
                        "note": "Diameter assumed to be the same in both directions.",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "ip-units": "in"
                    },
                    "screen_to_glass_distance": {
                        "type": "number",
                        "note": "Distance from the window screen to the adjacent glass surface.",
                        "units": "m",
                        "minimum": 0.001,
                        "maximum": 1.0,
                        "default": 0.025,
                        "ip-units": "in"
                    },
                    "top_opening_multiplier": {
                        "type": "number",
                        "note": "Effective area for air flow at the top of the screen divided by the perpendicular area between the glass and the top of the screen.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "bottom_opening_multiplier": {
                        "type": "number",
                        "note": "Effective area for air flow at the bottom of the screen divided by the perpendicular area between the glass and the bottom of the screen.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "left_side_opening_multiplier": {
                        "type": "number",
                        "note": "Effective area for air flow at the left side of the screen divided by the perpendicular area between the glass and the left side of the screen.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "right_side_opening_multiplier": {
                        "type": "number",
                        "note": "Effective area for air flow at the right side of the screen divided by the perpendicular area between the glass and the right side of the screen.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "angle_of_resolution_for_screen_transmittance_output_map": {
                        "note": "Select the resolution of azimuth and altitude angles for the screen transmittance map. A value of 0 means no transmittance map will be generated. Valid values for this field are 0, 1, 2, 3 and 5.",
                        "units": "deg",
                        "default": 0.0,
                        "anyOf": [
                            {
                                "type": "number",
                                "enum": [
                                    0,
                                    1,
                                    2,
                                    3,
                                    5
                                ]
                            },
                            {
                                "type": "string",
                                "enum": [
                                    ""
                                ]
                            }
                        ]
                    }
                },
                "required": [
                    "diffuse_solar_reflectance",
                    "diffuse_visible_reflectance",
                    "screen_material_spacing",
                    "screen_material_diameter"
                ]
            }
        },
        "group": "Surface Construction Elements",
        "name": {
            "type": "string",
            "note": "Enter a unique name for this window screen material.",
            "is_required": true,
            "reference": [
                "MaterialName",
                "WindowShadesScreensAndBlinds"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "reflected_beam_transmittance_accounting_method": {
                    "field_name": "Reflected Beam Transmittance Accounting Method",
                    "field_type": "a"
                },
                "diffuse_solar_reflectance": {
                    "field_name": "Diffuse Solar Reflectance",
                    "field_type": "n"
                },
                "diffuse_visible_reflectance": {
                    "field_name": "Diffuse Visible Reflectance",
                    "field_type": "n"
                },
                "thermal_hemispherical_emissivity": {
                    "field_name": "Thermal Hemispherical Emissivity",
                    "field_type": "n"
                },
                "conductivity": {
                    "field_name": "Conductivity",
                    "field_type": "n"
                },
                "screen_material_spacing": {
                    "field_name": "Screen Material Spacing",
                    "field_type": "n"
                },
                "screen_material_diameter": {
                    "field_name": "Screen Material Diameter",
                    "field_type": "n"
                },
                "screen_to_glass_distance": {
                    "field_name": "Screen to Glass Distance",
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
                "angle_of_resolution_for_screen_transmittance_output_map": {
                    "field_name": "Angle of Resolution for Screen Transmittance Output Map",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "reflected_beam_transmittance_accounting_method",
                "diffuse_solar_reflectance",
                "diffuse_visible_reflectance",
                "thermal_hemispherical_emissivity",
                "conductivity",
                "screen_material_spacing",
                "screen_material_diameter",
                "screen_to_glass_distance",
                "top_opening_multiplier",
                "bottom_opening_multiplier",
                "left_side_opening_multiplier",
                "right_side_opening_multiplier",
                "angle_of_resolution_for_screen_transmittance_output_map"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "reflected_beam_transmittance_accounting_method"
                ]
            },
            "numerics": {
                "fields": [
                    "diffuse_solar_reflectance",
                    "diffuse_visible_reflectance",
                    "thermal_hemispherical_emissivity",
                    "conductivity",
                    "screen_material_spacing",
                    "screen_material_diameter",
                    "screen_to_glass_distance",
                    "top_opening_multiplier",
                    "bottom_opening_multiplier",
                    "left_side_opening_multiplier",
                    "right_side_opening_multiplier",
                    "angle_of_resolution_for_screen_transmittance_output_map"
                ]
            }
        },
        "type": "object",
        "memo": "Window screen physical properties. Can only be located on the exterior side of a window construction.",
        "min_fields": 9.0
    }
}
```
