```
{
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
                    "maximum": 1.0,
                    "ip-units": "in"
                },
                "slat_separation": {
                    "type": "number",
                    "note": "Distance between adjacent slat faces",
                    "units": "m",
                    "exclusiveMinimum": 0.0,
                    "maximum": 1.0,
                    "ip-units": "in"
                },
                "slat_thickness": {
                    "type": "number",
                    "note": "Distance between top and bottom surfaces of slat Slat is assumed to be rectangular in cross section and flat",
                    "units": "m",
                    "exclusiveMinimum": 0.0,
                    "maximum": 0.1,
                    "default": 0.00025,
                    "ip-units": "in"
                },
                "slat_angle": {
                    "type": "number",
                    "note": "If WindowShadingControl referencing the window that incorporates this blind has Type of Slat Angle Control for Blinds = FixedSlatAngle, then this is the fixed value of the slat angle; If WindowShadingControl referencing the window that incorporates this blind has Type of Slat Angle Control for Blinds = BlockBeamSolar, then this is the slat angle when slat angle control is not in effect (e.g., when there is no beam solar on the blind); Not used if WindowShadingControl referencing the window that incorporates this blind has Type of Slat Angle Control for Blinds = ScheduledSlatAngle.",
                    "units": "deg",
                    "default": 45.0,
                    "minimum": 0.0,
                    "maximum": 180.0
                },
                "slat_conductivity": {
                    "type": "number",
                    "units": "W/m-K",
                    "exclusiveMinimum": 0.0,
                    "default": 221.0,
                    "note": "default is for aluminum"
                },
                "slat_beam_solar_transmittance": {
                    "type": "number",
                    "exclusiveMaximum": 1.0,
                    "minimum": 0.0,
                    "default": 0.0
                },
                "front_side_slat_beam_solar_reflectance": {
                    "type": "number",
                    "exclusiveMaximum": 1.0,
                    "minimum": 0.0
                },
                "back_side_slat_beam_solar_reflectance": {
                    "type": "number",
                    "exclusiveMaximum": 1.0,
                    "minimum": 0.0
                },
                "slat_diffuse_solar_transmittance": {
                    "type": "number",
                    "note": "Must equal \"Slat beam solar transmittance\"",
                    "exclusiveMaximum": 1.0,
                    "minimum": 0.0,
                    "default": 0.0
                },
                "front_side_slat_diffuse_solar_reflectance": {
                    "type": "number",
                    "note": "Must equal \"Front Side Slat Beam Solar Reflectance\"",
                    "exclusiveMaximum": 1.0,
                    "minimum": 0.0
                },
                "back_side_slat_diffuse_solar_reflectance": {
                    "type": "number",
                    "note": "Must equal \"Back Side Slat Beam Solar Reflectance\"",
                    "exclusiveMaximum": 1.0,
                    "minimum": 0.0
                },
                "slat_beam_visible_transmittance": {
                    "type": "number",
                    "note": "Required for detailed daylighting calculation",
                    "exclusiveMaximum": 1.0,
                    "minimum": 0.0
                },
                "front_side_slat_beam_visible_reflectance": {
                    "type": "number",
                    "note": "Required for detailed daylighting calculation",
                    "exclusiveMaximum": 1.0,
                    "minimum": 0.0
                },
                "back_side_slat_beam_visible_reflectance": {
                    "type": "number",
                    "note": "Required for detailed daylighting calculation",
                    "exclusiveMaximum": 1.0,
                    "minimum": 0.0
                },
                "slat_diffuse_visible_transmittance": {
                    "type": "number",
                    "note": "Used only for detailed daylighting calculation Must equal \"Slat Beam Visible Transmittance\"",
                    "exclusiveMaximum": 1.0,
                    "minimum": 0.0,
                    "default": 0.0
                },
                "front_side_slat_diffuse_visible_reflectance": {
                    "type": "number",
                    "note": "Required for detailed daylighting calculation Must equal \"Front Side Slat Beam Visible Reflectance\"",
                    "exclusiveMaximum": 1.0,
                    "minimum": 0.0
                },
                "back_side_slat_diffuse_visible_reflectance": {
                    "type": "number",
                    "note": "Required for detailed daylighting calculation Must equal \"Back Side Slat Beam Visible Reflectance\"",
                    "exclusiveMaximum": 1.0,
                    "minimum": 0.0
                },
                "slat_infrared_hemispherical_transmittance": {
                    "type": "number",
                    "exclusiveMaximum": 1.0,
                    "minimum": 0.0,
                    "default": 0.0
                },
                "front_side_slat_infrared_hemispherical_emissivity": {
                    "type": "number",
                    "exclusiveMaximum": 1.0,
                    "minimum": 0.0,
                    "default": 0.9
                },
                "back_side_slat_infrared_hemispherical_emissivity": {
                    "type": "number",
                    "exclusiveMaximum": 1.0,
                    "minimum": 0.0,
                    "default": 0.9
                },
                "blind_to_glass_distance": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.01,
                    "maximum": 1.0,
                    "default": 0.05,
                    "ip-units": "in"
                },
                "blind_top_opening_multiplier": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.5
                },
                "blind_bottom_opening_multiplier": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0
                },
                "blind_left_side_opening_multiplier": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.5
                },
                "blind_right_side_opening_multiplier": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.5
                },
                "minimum_slat_angle": {
                    "type": "number",
                    "note": "Used only if WindowShadingControl referencing the window that incorporates this blind varies the slat angle (i.e., WindowShadingControl with Type of Slat Angle Control for Blinds = ScheduledSlatAngle or BlockBeamSolar)",
                    "units": "deg",
                    "default": 0.0,
                    "minimum": 0.0,
                    "maximum": 180.0
                },
                "maximum_slat_angle": {
                    "type": "number",
                    "note": "Used only if WindowShadingControl referencing the window that incorporates this blind varies the slat angle (i.e., WindowShadingControl with Type of Slat Angle Control for Blinds = ScheduledSlatAngle or BlockBeamSolar)",
                    "units": "deg",
                    "default": 180.0,
                    "minimum": 0.0,
                    "maximum": 180.0
                }
            },
            "required": [
                "slat_width",
                "slat_separation",
                "front_side_slat_beam_solar_reflectance",
                "back_side_slat_beam_solar_reflectance",
                "front_side_slat_diffuse_solar_reflectance",
                "back_side_slat_diffuse_solar_reflectance",
                "slat_beam_visible_transmittance"
            ]
        }
    },
    "group": "Surface Construction Elements",
    "name": {
        "type": "string",
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
            "slat_beam_solar_transmittance": {
                "field_name": "Slat Beam Solar Transmittance",
                "field_type": "n"
            },
            "front_side_slat_beam_solar_reflectance": {
                "field_name": "Front Side Slat Beam Solar Reflectance",
                "field_type": "n"
            },
            "back_side_slat_beam_solar_reflectance": {
                "field_name": "Back Side Slat Beam Solar Reflectance",
                "field_type": "n"
            },
            "slat_diffuse_solar_transmittance": {
                "field_name": "Slat Diffuse Solar Transmittance",
                "field_type": "n"
            },
            "front_side_slat_diffuse_solar_reflectance": {
                "field_name": "Front Side Slat Diffuse Solar Reflectance",
                "field_type": "n"
            },
            "back_side_slat_diffuse_solar_reflectance": {
                "field_name": "Back Side Slat Diffuse Solar Reflectance",
                "field_type": "n"
            },
            "slat_beam_visible_transmittance": {
                "field_name": "Slat Beam Visible Transmittance",
                "field_type": "n"
            },
            "front_side_slat_beam_visible_reflectance": {
                "field_name": "Front Side Slat Beam Visible Reflectance",
                "field_type": "n"
            },
            "back_side_slat_beam_visible_reflectance": {
                "field_name": "Back Side Slat Beam Visible Reflectance",
                "field_type": "n"
            },
            "slat_diffuse_visible_transmittance": {
                "field_name": "Slat Diffuse Visible Transmittance",
                "field_type": "n"
            },
            "front_side_slat_diffuse_visible_reflectance": {
                "field_name": "Front Side Slat Diffuse Visible Reflectance",
                "field_type": "n"
            },
            "back_side_slat_diffuse_visible_reflectance": {
                "field_name": "Back Side Slat Diffuse Visible Reflectance",
                "field_type": "n"
            },
            "slat_infrared_hemispherical_transmittance": {
                "field_name": "Slat Infrared Hemispherical Transmittance",
                "field_type": "n"
            },
            "front_side_slat_infrared_hemispherical_emissivity": {
                "field_name": "Front Side Slat Infrared Hemispherical Emissivity",
                "field_type": "n"
            },
            "back_side_slat_infrared_hemispherical_emissivity": {
                "field_name": "Back Side Slat Infrared Hemispherical Emissivity",
                "field_type": "n"
            },
            "blind_to_glass_distance": {
                "field_name": "Blind to Glass Distance",
                "field_type": "n"
            },
            "blind_top_opening_multiplier": {
                "field_name": "Blind Top Opening Multiplier",
                "field_type": "n"
            },
            "blind_bottom_opening_multiplier": {
                "field_name": "Blind Bottom Opening Multiplier",
                "field_type": "n"
            },
            "blind_left_side_opening_multiplier": {
                "field_name": "Blind Left Side Opening Multiplier",
                "field_type": "n"
            },
            "blind_right_side_opening_multiplier": {
                "field_name": "Blind Right Side Opening Multiplier",
                "field_type": "n"
            },
            "minimum_slat_angle": {
                "field_name": "Minimum Slat Angle",
                "field_type": "n"
            },
            "maximum_slat_angle": {
                "field_name": "Maximum Slat Angle",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "slat_orientation",
            "slat_width",
            "slat_separation",
            "slat_thickness",
            "slat_angle",
            "slat_conductivity",
            "slat_beam_solar_transmittance",
            "front_side_slat_beam_solar_reflectance",
            "back_side_slat_beam_solar_reflectance",
            "slat_diffuse_solar_transmittance",
            "front_side_slat_diffuse_solar_reflectance",
            "back_side_slat_diffuse_solar_reflectance",
            "slat_beam_visible_transmittance",
            "front_side_slat_beam_visible_reflectance",
            "back_side_slat_beam_visible_reflectance",
            "slat_diffuse_visible_transmittance",
            "front_side_slat_diffuse_visible_reflectance",
            "back_side_slat_diffuse_visible_reflectance",
            "slat_infrared_hemispherical_transmittance",
            "front_side_slat_infrared_hemispherical_emissivity",
            "back_side_slat_infrared_hemispherical_emissivity",
            "blind_to_glass_distance",
            "blind_top_opening_multiplier",
            "blind_bottom_opening_multiplier",
            "blind_left_side_opening_multiplier",
            "blind_right_side_opening_multiplier",
            "minimum_slat_angle",
            "maximum_slat_angle"
        ],
        "alphas": {
            "fields": [
                "name",
                "slat_orientation"
            ]
        },
        "numerics": {
            "fields": [
                "slat_width",
                "slat_separation",
                "slat_thickness",
                "slat_angle",
                "slat_conductivity",
                "slat_beam_solar_transmittance",
                "front_side_slat_beam_solar_reflectance",
                "back_side_slat_beam_solar_reflectance",
                "slat_diffuse_solar_transmittance",
                "front_side_slat_diffuse_solar_reflectance",
                "back_side_slat_diffuse_solar_reflectance",
                "slat_beam_visible_transmittance",
                "front_side_slat_beam_visible_reflectance",
                "back_side_slat_beam_visible_reflectance",
                "slat_diffuse_visible_transmittance",
                "front_side_slat_diffuse_visible_reflectance",
                "back_side_slat_diffuse_visible_reflectance",
                "slat_infrared_hemispherical_transmittance",
                "front_side_slat_infrared_hemispherical_emissivity",
                "back_side_slat_infrared_hemispherical_emissivity",
                "blind_to_glass_distance",
                "blind_top_opening_multiplier",
                "blind_bottom_opening_multiplier",
                "blind_left_side_opening_multiplier",
                "blind_right_side_opening_multiplier",
                "minimum_slat_angle",
                "maximum_slat_angle"
            ]
        }
    },
    "type": "object",
    "memo": "Window blind thermal properties",
    "min_fields": 29.0
}
```
