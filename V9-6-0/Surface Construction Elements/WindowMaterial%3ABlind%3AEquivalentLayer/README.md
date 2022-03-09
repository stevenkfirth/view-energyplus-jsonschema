```
{
    "WindowMaterial:Blind:EquivalentLayer": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "slat_orientation": {
                        "type": "string",
                        "enum": [
                            "",
                            "Horizontal",
                            "Vertical"
                        ],
                        "default": "Horizontal"
                    },
                    "slat_width": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "maximum": 0.025,
                        "ip-units": "in"
                    },
                    "slat_separation": {
                        "type": "number",
                        "note": "Distance between adjacent slat faces",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "maximum": 0.025,
                        "ip-units": "in"
                    },
                    "slat_crown": {
                        "type": "number",
                        "note": "Perpendicular length between the cord and the curve. Slat is assumed to be rectangular in cross section and flat. Crown=0.0625x\"Slat width\"",
                        "units": "m",
                        "minimum": 0.0,
                        "maximum": 0.00156,
                        "default": 0.0015,
                        "ip-units": "in"
                    },
                    "slat_angle": {
                        "type": "number",
                        "units": "deg",
                        "minimum": -90.0,
                        "maximum": 90.0,
                        "default": 45.0,
                        "note": "Slat angle is +ve if the tip of the slat front face is tilted upward, else the slat angle is -ve if the tip of the slat front face is tilted downward. The slat angle varies between -90 to +90. The default value is 45 degrees."
                    },
                    "front_side_slat_beam_diffuse_solar_transmittance": {
                        "type": "number",
                        "note": "The front side beam-diffuse solar transmittance of the slat at normal incidence averaged over the entire spectrum of solar radiation.",
                        "exclusiveMaximum": 1.0,
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "back_side_slat_beam_diffuse_solar_transmittance": {
                        "type": "number",
                        "note": "The back side beam-diffuse solar transmittance of the slat at normal incidence averaged over the entire spectrum of solar radiation.",
                        "units": "dimensionless",
                        "exclusiveMaximum": 1.0,
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "front_side_slat_beam_diffuse_solar_reflectance": {
                        "type": "number",
                        "note": "The front side beam-diffuse solar reflectance of the slat at normal incidence averaged over the entire spectrum of solar radiation.",
                        "units": "dimensionless",
                        "exclusiveMaximum": 1.0,
                        "minimum": 0.0
                    },
                    "back_side_slat_beam_diffuse_solar_reflectance": {
                        "type": "number",
                        "note": "The back side beam-diffuse solar reflectance of the slat at normal incidence averaged over the entire spectrum of solar radiation.",
                        "units": "dimensionless",
                        "exclusiveMaximum": 1.0,
                        "minimum": 0.0
                    },
                    "front_side_slat_beam_diffuse_visible_transmittance": {
                        "type": "number",
                        "note": "The front side beam-diffuse visible transmittance of the slat at normal incidence averaged over the visible spectrum range of solar radiation.",
                        "units": "dimensionless",
                        "exclusiveMaximum": 1.0,
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "back_side_slat_beam_diffuse_visible_transmittance": {
                        "type": "number",
                        "note": "The back side beam-diffuse visible transmittance of the slat at normal incidence averaged over the visible spectrum range of solar radiation.",
                        "units": "dimensionless",
                        "exclusiveMaximum": 1.0,
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "front_side_slat_beam_diffuse_visible_reflectance": {
                        "type": "number",
                        "note": "The front side beam-diffuse visible reflectance of the slat at normal incidence averaged over the visible spectrum range of solar radiation.",
                        "units": "dimensionless",
                        "exclusiveMaximum": 1.0,
                        "minimum": 0.0
                    },
                    "back_side_slat_beam_diffuse_visible_reflectance": {
                        "type": "number",
                        "note": "The back side beam-diffuse visible reflectance of the slat at normal incidence averaged over the visible spectrum range of solar radiation.",
                        "units": "dimensionless",
                        "exclusiveMaximum": 1.0,
                        "minimum": 0.0
                    },
                    "slat_diffuse_diffuse_solar_transmittance": {
                        "type": "number",
                        "note": "The beam-diffuse solar transmittance of the slat averaged over the entire solar spectrum of solar radiation.",
                        "units": "dimensionless",
                        "exclusiveMaximum": 1.0,
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "front_side_slat_diffuse_diffuse_solar_reflectance": {
                        "type": "number",
                        "note": "The front side beam-diffuse solar reflectance of the slat averaged over the entire solar spectrum of solar radiation.",
                        "units": "dimensionless",
                        "exclusiveMaximum": 1.0,
                        "minimum": 0.0
                    },
                    "back_side_slat_diffuse_diffuse_solar_reflectance": {
                        "type": "number",
                        "note": "The back side beam-diffuse solar reflectance of the slat averaged over the entire solar spectrum of solar radiation.",
                        "units": "dimensionless",
                        "exclusiveMaximum": 1.0,
                        "minimum": 0.0
                    },
                    "slat_diffuse_diffuse_visible_transmittance": {
                        "type": "number",
                        "note": "The beam-diffuse visible transmittance of the slat averaged over the visible spectrum range of solar radiation.",
                        "exclusiveMaximum": 1.0,
                        "minimum": 0.0
                    },
                    "front_side_slat_diffuse_diffuse_visible_reflectance": {
                        "type": "number",
                        "note": "The front side beam-diffuse visible reflectance of the slat averaged over the visible spectrum range of solar radiation.",
                        "units": "dimensionless",
                        "exclusiveMaximum": 1.0,
                        "minimum": 0.0
                    },
                    "back_side_slat_diffuse_diffuse_visible_reflectance": {
                        "type": "number",
                        "note": "The back side beam-diffuse visible reflectance of the slat averaged over the visible spectrum range of solar radiation.",
                        "units": "dimensionless",
                        "exclusiveMaximum": 1.0,
                        "minimum": 0.0
                    },
                    "slat_infrared_transmittance": {
                        "type": "number",
                        "note": "Long-wave hemispherical transmittance of the slat material. Assumed to be the same for both sides of the slat.",
                        "exclusiveMaximum": 1.0,
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "front_side_slat_infrared_emissivity": {
                        "type": "number",
                        "note": "Front side long-wave hemispherical emissivity of the slat material.",
                        "units": "dimensionless",
                        "exclusiveMaximum": 1.0,
                        "minimum": 0.0,
                        "default": 0.9
                    },
                    "back_side_slat_infrared_emissivity": {
                        "type": "number",
                        "note": "Back side long-wave hemispherical emissivity of the slat material.",
                        "units": "dimensionless",
                        "exclusiveMaximum": 1.0,
                        "minimum": 0.0,
                        "default": 0.9
                    },
                    "slat_angle_control": {
                        "type": "string",
                        "note": "Used only if slat angle control is desired to either maximize solar gain (MaximizeSolar), maximize visibility while eliminating beam solar radiation (BlockBeamSolar), or fixed slate angle (FixedSlatAngle). If FixedSlatAngle is selected, the slat angle entered above is used.",
                        "enum": [
                            "",
                            "BlockBeamSolar",
                            "FixedSlatAngle",
                            "MaximizeSolar"
                        ],
                        "default": "FixedSlatAngle"
                    }
                },
                "required": [
                    "slat_width",
                    "slat_separation",
                    "front_side_slat_beam_diffuse_solar_reflectance",
                    "back_side_slat_beam_diffuse_solar_reflectance",
                    "front_side_slat_diffuse_diffuse_solar_reflectance",
                    "back_side_slat_diffuse_diffuse_solar_reflectance"
                ]
            }
        },
        "group": "Surface Construction Elements",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "WindowEquivalentLayerMaterialNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "slat_orientation": {
                    "field_name": "Slat Orientation",
                    "field_type": "a"
                },
                "slat_width": {
                    "field_name": "Slat Width",
                    "field_type": "n"
                },
                "slat_separation": {
                    "field_name": "Slat Separation",
                    "field_type": "n"
                },
                "slat_crown": {
                    "field_name": "Slat Crown",
                    "field_type": "n"
                },
                "slat_angle": {
                    "field_name": "Slat Angle",
                    "field_type": "n"
                },
                "front_side_slat_beam_diffuse_solar_transmittance": {
                    "field_name": "Front Side Slat Beam-Diffuse Solar Transmittance",
                    "field_type": "n"
                },
                "back_side_slat_beam_diffuse_solar_transmittance": {
                    "field_name": "Back Side Slat Beam-Diffuse Solar Transmittance",
                    "field_type": "n"
                },
                "front_side_slat_beam_diffuse_solar_reflectance": {
                    "field_name": "Front Side Slat Beam-Diffuse Solar Reflectance",
                    "field_type": "n"
                },
                "back_side_slat_beam_diffuse_solar_reflectance": {
                    "field_name": "Back Side Slat Beam-Diffuse Solar Reflectance",
                    "field_type": "n"
                },
                "front_side_slat_beam_diffuse_visible_transmittance": {
                    "field_name": "Front Side Slat Beam-Diffuse Visible Transmittance",
                    "field_type": "n"
                },
                "back_side_slat_beam_diffuse_visible_transmittance": {
                    "field_name": "Back Side Slat Beam-Diffuse Visible Transmittance",
                    "field_type": "n"
                },
                "front_side_slat_beam_diffuse_visible_reflectance": {
                    "field_name": "Front Side Slat Beam-Diffuse Visible Reflectance",
                    "field_type": "n"
                },
                "back_side_slat_beam_diffuse_visible_reflectance": {
                    "field_name": "Back Side Slat Beam-Diffuse Visible Reflectance",
                    "field_type": "n"
                },
                "slat_diffuse_diffuse_solar_transmittance": {
                    "field_name": "Slat Diffuse-Diffuse Solar Transmittance",
                    "field_type": "n"
                },
                "front_side_slat_diffuse_diffuse_solar_reflectance": {
                    "field_name": "Front Side Slat Diffuse-Diffuse Solar Reflectance",
                    "field_type": "n"
                },
                "back_side_slat_diffuse_diffuse_solar_reflectance": {
                    "field_name": "Back Side Slat Diffuse-Diffuse Solar Reflectance",
                    "field_type": "n"
                },
                "slat_diffuse_diffuse_visible_transmittance": {
                    "field_name": "Slat Diffuse-Diffuse Visible Transmittance",
                    "field_type": "n"
                },
                "front_side_slat_diffuse_diffuse_visible_reflectance": {
                    "field_name": "Front Side Slat Diffuse-Diffuse Visible Reflectance",
                    "field_type": "n"
                },
                "back_side_slat_diffuse_diffuse_visible_reflectance": {
                    "field_name": "Back Side Slat Diffuse-Diffuse Visible Reflectance",
                    "field_type": "n"
                },
                "slat_infrared_transmittance": {
                    "field_name": "Slat Infrared Transmittance",
                    "field_type": "n"
                },
                "front_side_slat_infrared_emissivity": {
                    "field_name": "Front Side Slat Infrared Emissivity",
                    "field_type": "n"
                },
                "back_side_slat_infrared_emissivity": {
                    "field_name": "Back Side Slat Infrared Emissivity",
                    "field_type": "n"
                },
                "slat_angle_control": {
                    "field_name": "Slat Angle Control",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "slat_orientation",
                "slat_width",
                "slat_separation",
                "slat_crown",
                "slat_angle",
                "front_side_slat_beam_diffuse_solar_transmittance",
                "back_side_slat_beam_diffuse_solar_transmittance",
                "front_side_slat_beam_diffuse_solar_reflectance",
                "back_side_slat_beam_diffuse_solar_reflectance",
                "front_side_slat_beam_diffuse_visible_transmittance",
                "back_side_slat_beam_diffuse_visible_transmittance",
                "front_side_slat_beam_diffuse_visible_reflectance",
                "back_side_slat_beam_diffuse_visible_reflectance",
                "slat_diffuse_diffuse_solar_transmittance",
                "front_side_slat_diffuse_diffuse_solar_reflectance",
                "back_side_slat_diffuse_diffuse_solar_reflectance",
                "slat_diffuse_diffuse_visible_transmittance",
                "front_side_slat_diffuse_diffuse_visible_reflectance",
                "back_side_slat_diffuse_diffuse_visible_reflectance",
                "slat_infrared_transmittance",
                "front_side_slat_infrared_emissivity",
                "back_side_slat_infrared_emissivity",
                "slat_angle_control"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "slat_orientation",
                    "slat_angle_control"
                ]
            },
            "numerics": {
                "fields": [
                    "slat_width",
                    "slat_separation",
                    "slat_crown",
                    "slat_angle",
                    "front_side_slat_beam_diffuse_solar_transmittance",
                    "back_side_slat_beam_diffuse_solar_transmittance",
                    "front_side_slat_beam_diffuse_solar_reflectance",
                    "back_side_slat_beam_diffuse_solar_reflectance",
                    "front_side_slat_beam_diffuse_visible_transmittance",
                    "back_side_slat_beam_diffuse_visible_transmittance",
                    "front_side_slat_beam_diffuse_visible_reflectance",
                    "back_side_slat_beam_diffuse_visible_reflectance",
                    "slat_diffuse_diffuse_solar_transmittance",
                    "front_side_slat_diffuse_diffuse_solar_reflectance",
                    "back_side_slat_diffuse_diffuse_solar_reflectance",
                    "slat_diffuse_diffuse_visible_transmittance",
                    "front_side_slat_diffuse_diffuse_visible_reflectance",
                    "back_side_slat_diffuse_diffuse_visible_reflectance",
                    "slat_infrared_transmittance",
                    "front_side_slat_infrared_emissivity",
                    "back_side_slat_infrared_emissivity"
                ]
            }
        },
        "type": "object",
        "memo": "Window equivalent layer blind slat optical and thermal properties. The model assumes that slats are thin and flat, applies correction empirical correlation to account for curvature effect. Slats are assumed to transmit and reflect diffusely.",
        "min_fields": 10.0
    }
}
```
