```
{
    "WindowMaterial:Shade:EquivalentLayer": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "shade_beam_beam_solar_transmittance": {
                        "type": "number",
                        "note": "The beam-beam solar transmittance at normal incidence. This value is the same as the openness area fraction of the shade material. Assumed to be the same for front and back sides.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 0.8,
                        "default": 0.0
                    },
                    "front_side_shade_beam_diffuse_solar_transmittance": {
                        "type": "number",
                        "note": "The front side beam-diffuse solar transmittance at normal incidence averaged over the entire spectrum of solar radiation.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "exclusiveMaximum": 1.0
                    },
                    "back_side_shade_beam_diffuse_solar_transmittance": {
                        "type": "number",
                        "note": "The back side beam-diffuse solar transmittance at normal incidence averaged over the entire spectrum of solar radiation.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "exclusiveMaximum": 1.0
                    },
                    "front_side_shade_beam_diffuse_solar_reflectance": {
                        "type": "number",
                        "note": "The front side beam-diffuse solar reflectance at normal incidence averaged over the entire spectrum of solar radiation.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "exclusiveMaximum": 1.0
                    },
                    "back_side_shade_beam_diffuse_solar_reflectance": {
                        "type": "number",
                        "note": "The back side beam-diffuse solar reflectance at normal incidence averaged over the entire spectrum of solar radiation.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "exclusiveMaximum": 1.0
                    },
                    "shade_beam_beam_visible_transmittance_at_normal_incidence": {
                        "type": "number",
                        "note": "The beam-beam visible transmittance at normal incidence averaged over the visible spectrum range of solar radiation. Assumed to be the same for front and back sides of the shade.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "exclusiveMaximum": 1.0
                    },
                    "shade_beam_diffuse_visible_transmittance_at_normal_incidence": {
                        "type": "number",
                        "note": "The beam-diffuse visible transmittance at normal incidence averaged over the visible spectrum range of solar radiation. Assumed to be the same for front and back sides of the shade.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "exclusiveMaximum": 1.0
                    },
                    "shade_beam_diffuse_visible_reflectance_at_normal_incidence": {
                        "type": "number",
                        "note": "The beam-diffuse visible reflectance at normal incidence averaged over the visible spectrum range of solar radiation. Assumed to be the same for front and back sides of the shade.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "exclusiveMaximum": 1.0
                    },
                    "shade_material_infrared_transmittance": {
                        "type": "number",
                        "note": "The long-wave transmittance of the shade material at zero shade openness. Assumed to be the same for front and back sides of the shade.",
                        "units": "dimensionless",
                        "exclusiveMaximum": 1.0,
                        "minimum": 0.0,
                        "default": 0.05
                    },
                    "front_side_shade_material_infrared_emissivity": {
                        "type": "number",
                        "note": "The front side long-wave emissivity of the shade material at zero shade openness. Openness fraction is used to calculate the effective emissivity value.",
                        "units": "dimensionless",
                        "exclusiveMaximum": 1.0,
                        "exclusiveMinimum": 0.0,
                        "default": 0.91
                    },
                    "back_side_shade_material_infrared_emissivity": {
                        "type": "number",
                        "note": "The back side long-wave emissivity of the shade material at zero shade openness. Openness fraction is used to calculate the effective emissivity value.",
                        "units": "dimensionless",
                        "exclusiveMaximum": 1.0,
                        "exclusiveMinimum": 0.0,
                        "default": 0.91
                    }
                },
                "required": [
                    "front_side_shade_beam_diffuse_solar_transmittance",
                    "back_side_shade_beam_diffuse_solar_transmittance",
                    "front_side_shade_beam_diffuse_solar_reflectance",
                    "back_side_shade_beam_diffuse_solar_reflectance"
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
                "shade_beam_beam_solar_transmittance": {
                    "field_name": "Shade Beam-Beam Solar Transmittance",
                    "field_type": "n"
                },
                "front_side_shade_beam_diffuse_solar_transmittance": {
                    "field_name": "Front Side Shade Beam-Diffuse Solar Transmittance",
                    "field_type": "n"
                },
                "back_side_shade_beam_diffuse_solar_transmittance": {
                    "field_name": "Back Side Shade Beam-Diffuse Solar Transmittance",
                    "field_type": "n"
                },
                "front_side_shade_beam_diffuse_solar_reflectance": {
                    "field_name": "Front Side Shade Beam-Diffuse Solar Reflectance",
                    "field_type": "n"
                },
                "back_side_shade_beam_diffuse_solar_reflectance": {
                    "field_name": "Back Side Shade Beam-Diffuse Solar Reflectance",
                    "field_type": "n"
                },
                "shade_beam_beam_visible_transmittance_at_normal_incidence": {
                    "field_name": "Shade Beam-Beam Visible Transmittance at Normal Incidence",
                    "field_type": "n"
                },
                "shade_beam_diffuse_visible_transmittance_at_normal_incidence": {
                    "field_name": "Shade Beam-Diffuse Visible Transmittance at Normal Incidence",
                    "field_type": "n"
                },
                "shade_beam_diffuse_visible_reflectance_at_normal_incidence": {
                    "field_name": "Shade Beam-Diffuse Visible Reflectance at Normal Incidence",
                    "field_type": "n"
                },
                "shade_material_infrared_transmittance": {
                    "field_name": "Shade Material Infrared Transmittance",
                    "field_type": "n"
                },
                "front_side_shade_material_infrared_emissivity": {
                    "field_name": "Front Side Shade Material Infrared Emissivity",
                    "field_type": "n"
                },
                "back_side_shade_material_infrared_emissivity": {
                    "field_name": "Back Side Shade Material Infrared Emissivity",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "shade_beam_beam_solar_transmittance",
                "front_side_shade_beam_diffuse_solar_transmittance",
                "back_side_shade_beam_diffuse_solar_transmittance",
                "front_side_shade_beam_diffuse_solar_reflectance",
                "back_side_shade_beam_diffuse_solar_reflectance",
                "shade_beam_beam_visible_transmittance_at_normal_incidence",
                "shade_beam_diffuse_visible_transmittance_at_normal_incidence",
                "shade_beam_diffuse_visible_reflectance_at_normal_incidence",
                "shade_material_infrared_transmittance",
                "front_side_shade_material_infrared_emissivity",
                "back_side_shade_material_infrared_emissivity"
            ],
            "alphas": {
                "fields": [
                    "name"
                ]
            },
            "numerics": {
                "fields": [
                    "shade_beam_beam_solar_transmittance",
                    "front_side_shade_beam_diffuse_solar_transmittance",
                    "back_side_shade_beam_diffuse_solar_transmittance",
                    "front_side_shade_beam_diffuse_solar_reflectance",
                    "back_side_shade_beam_diffuse_solar_reflectance",
                    "shade_beam_beam_visible_transmittance_at_normal_incidence",
                    "shade_beam_diffuse_visible_transmittance_at_normal_incidence",
                    "shade_beam_diffuse_visible_reflectance_at_normal_incidence",
                    "shade_material_infrared_transmittance",
                    "front_side_shade_material_infrared_emissivity",
                    "back_side_shade_material_infrared_emissivity"
                ]
            }
        },
        "type": "object",
        "memo": "Specifies the properties of equivalent layer window shade material Shades are considered to be perfect diffusers (all transmitted and reflected radiation is hemispherically-diffuse) independent of angle of incidence. Shade represents roller blinds.",
        "min_fields": 6.0
    }
}
```
