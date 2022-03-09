```
{
    "WindowMaterial:Drape:EquivalentLayer": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "drape_beam_beam_solar_transmittance_at_normal_incidence": {
                        "type": "number",
                        "note": "The beam-beam solar transmittance at normal incidence. This value is the same as the openness area fraction of the drape fabric. Assumed to be same for front and back sides.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 0.2,
                        "default": 0.0
                    },
                    "front_side_drape_beam_diffuse_solar_transmittance": {
                        "type": "number",
                        "note": "The front side beam-diffuse solar transmittance at normal incidence averaged over the entire spectrum of solar radiation. Assumed to be the same for front and back sides.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "exclusiveMaximum": 1.0
                    },
                    "back_side_drape_beam_diffuse_solar_transmittance": {
                        "type": "number",
                        "note": "The back side beam-diffuse solar transmittance at normal incidence averaged over the entire spectrum of solar radiation. Assumed to be the same for front and back sides.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "exclusiveMaximum": 1.0
                    },
                    "front_side_drape_beam_diffuse_solar_reflectance": {
                        "type": "number",
                        "note": "The front side beam-diffuse solar reflectance at normal incidence averaged over the entire spectrum of solar radiation.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "exclusiveMaximum": 1.0
                    },
                    "back_side_drape_beam_diffuse_solar_reflectance": {
                        "type": "number",
                        "note": "The back side beam-diffuse solar reflectance at normal incidence averaged over the entire spectrum of solar radiation.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "exclusiveMaximum": 1.0
                    },
                    "drape_beam_beam_visible_transmittance": {
                        "type": "number",
                        "note": "The beam-beam visible transmittance at normal incidence averaged over the visible spectrum of solar radiation. Assumed same for front and back sides.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "exclusiveMaximum": 1.0
                    },
                    "drape_beam_diffuse_visible_transmittance": {
                        "type": "number",
                        "note": "The beam-diffuse visible transmittance at normal incidence averaged over the visible spectrum range of solar radiation. Assumed to be the same for front and back sides.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "exclusiveMaximum": 1.0
                    },
                    "drape_beam_diffuse_visible_reflectance": {
                        "type": "number",
                        "note": "The beam-diffuse visible reflectance at normal incidence average over the visible spectrum range of solar radiation. Assumed to be the same for front and back sides.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "exclusiveMaximum": 1.0
                    },
                    "drape_material_infrared_transmittance": {
                        "type": "number",
                        "note": "Long-wave transmittance of the drape fabric at zero openness fraction. Assumed same for front and back sides.",
                        "units": "dimensionless",
                        "exclusiveMaximum": 1.0,
                        "minimum": 0.0,
                        "default": 0.05
                    },
                    "front_side_drape_material_infrared_emissivity": {
                        "type": "number",
                        "note": "Front side long-wave emissivity of the drape fabric at zero shade openness. Openness fraction specified above is used to calculate the effective emissivity value.",
                        "units": "dimensionless",
                        "exclusiveMaximum": 1.0,
                        "exclusiveMinimum": 0.0,
                        "default": 0.87
                    },
                    "back_side_drape_material_infrared_emissivity": {
                        "type": "number",
                        "note": "Back side long-wave emissivity of the drape fabric at zero shade openness. Openness fraction specified above is used to calculate the effective emissivity value.",
                        "units": "dimensionless",
                        "exclusiveMaximum": 1.0,
                        "exclusiveMinimum": 0.0,
                        "default": 0.87
                    },
                    "width_of_pleated_fabric": {
                        "type": "number",
                        "note": "Width of the pleated section of the draped fabric. If the drape fabric is unpleated or is flat, then the pleated section width is set to zero.",
                        "units": "m",
                        "minimum": 0.0,
                        "ip-units": "in",
                        "default": 0.0
                    },
                    "length_of_pleated_fabric": {
                        "type": "number",
                        "note": "Length of the pleated section of the draped fabric. If the drape fabric is unpleated or is flat, then the pleated section length is set to zero.",
                        "units": "m",
                        "minimum": 0.0,
                        "ip-units": "in",
                        "default": 0.0
                    }
                },
                "required": [
                    "front_side_drape_beam_diffuse_solar_transmittance",
                    "back_side_drape_beam_diffuse_solar_transmittance",
                    "front_side_drape_beam_diffuse_solar_reflectance",
                    "back_side_drape_beam_diffuse_solar_reflectance"
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
                "drape_beam_beam_solar_transmittance_at_normal_incidence": {
                    "field_name": "Drape Beam-Beam Solar Transmittance at Normal Incidence",
                    "field_type": "n"
                },
                "front_side_drape_beam_diffuse_solar_transmittance": {
                    "field_name": "Front Side Drape Beam-Diffuse Solar Transmittance",
                    "field_type": "n"
                },
                "back_side_drape_beam_diffuse_solar_transmittance": {
                    "field_name": "Back Side Drape Beam-Diffuse Solar Transmittance",
                    "field_type": "n"
                },
                "front_side_drape_beam_diffuse_solar_reflectance": {
                    "field_name": "Front Side Drape Beam-Diffuse Solar Reflectance",
                    "field_type": "n"
                },
                "back_side_drape_beam_diffuse_solar_reflectance": {
                    "field_name": "Back Side Drape Beam-Diffuse Solar Reflectance",
                    "field_type": "n"
                },
                "drape_beam_beam_visible_transmittance": {
                    "field_name": "Drape Beam-Beam Visible Transmittance",
                    "field_type": "n"
                },
                "drape_beam_diffuse_visible_transmittance": {
                    "field_name": "Drape Beam-Diffuse Visible Transmittance",
                    "field_type": "n"
                },
                "drape_beam_diffuse_visible_reflectance": {
                    "field_name": "Drape Beam-Diffuse Visible Reflectance",
                    "field_type": "n"
                },
                "drape_material_infrared_transmittance": {
                    "field_name": "Drape Material Infrared Transmittance",
                    "field_type": "n"
                },
                "front_side_drape_material_infrared_emissivity": {
                    "field_name": "Front Side Drape Material Infrared Emissivity",
                    "field_type": "n"
                },
                "back_side_drape_material_infrared_emissivity": {
                    "field_name": "Back Side Drape Material Infrared Emissivity",
                    "field_type": "n"
                },
                "width_of_pleated_fabric": {
                    "field_name": "Width of Pleated Fabric",
                    "field_type": "n"
                },
                "length_of_pleated_fabric": {
                    "field_name": "Length of Pleated Fabric",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "drape_beam_beam_solar_transmittance_at_normal_incidence",
                "front_side_drape_beam_diffuse_solar_transmittance",
                "back_side_drape_beam_diffuse_solar_transmittance",
                "front_side_drape_beam_diffuse_solar_reflectance",
                "back_side_drape_beam_diffuse_solar_reflectance",
                "drape_beam_beam_visible_transmittance",
                "drape_beam_diffuse_visible_transmittance",
                "drape_beam_diffuse_visible_reflectance",
                "drape_material_infrared_transmittance",
                "front_side_drape_material_infrared_emissivity",
                "back_side_drape_material_infrared_emissivity",
                "width_of_pleated_fabric",
                "length_of_pleated_fabric"
            ],
            "alphas": {
                "fields": [
                    "name"
                ]
            },
            "numerics": {
                "fields": [
                    "drape_beam_beam_solar_transmittance_at_normal_incidence",
                    "front_side_drape_beam_diffuse_solar_transmittance",
                    "back_side_drape_beam_diffuse_solar_transmittance",
                    "front_side_drape_beam_diffuse_solar_reflectance",
                    "back_side_drape_beam_diffuse_solar_reflectance",
                    "drape_beam_beam_visible_transmittance",
                    "drape_beam_diffuse_visible_transmittance",
                    "drape_beam_diffuse_visible_reflectance",
                    "drape_material_infrared_transmittance",
                    "front_side_drape_material_infrared_emissivity",
                    "back_side_drape_material_infrared_emissivity",
                    "width_of_pleated_fabric",
                    "length_of_pleated_fabric"
                ]
            }
        },
        "type": "object",
        "memo": "Specifies the properties of equivalent layer drape fabric materials. Shades are considered to be perfect diffusers (all transmitted and reflected radiation is hemispherically-diffuse) independent of angle of incidence. unpleated drape fabric is treated as thin and flat layer.",
        "min_fields": 4.0
    }
}
```
