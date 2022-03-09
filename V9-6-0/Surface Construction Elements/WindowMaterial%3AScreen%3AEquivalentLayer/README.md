```
{
    "WindowMaterial:Screen:EquivalentLayer": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "screen_beam_beam_solar_transmittance": {
                        "note": "The beam-beam transmittance of the screen material at normal incidence. This input field is the same as the material openness area fraction and can be autocalculated from the wire spacing and wire and diameter. Assumed to be the same for both sides of the screen.",
                        "units": "dimensionless",
                        "default": "Autocalculate",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.0,
                                "exclusiveMaximum": 1.0
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
                    "screen_beam_diffuse_solar_transmittance": {
                        "type": "number",
                        "note": "The beam-diffuse solar transmittance of the screen material at normal incidence averaged over the entire spectrum of solar radiation. Assumed to be the same for both sides of the screen.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "exclusiveMaximum": 1.0
                    },
                    "screen_beam_diffuse_solar_reflectance": {
                        "type": "number",
                        "note": "The beam-diffuse solar reflectance of the screen material at normal incidence averaged over the entire spectrum of solar radiation. Assumed to be the same for both sides of the screen.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "exclusiveMaximum": 1.0
                    },
                    "screen_beam_beam_visible_transmittance": {
                        "type": "number",
                        "note": "The beam-beam visible transmittance of the screen material at normal incidence averaged over the visible spectrum range of solar radiation. Assumed to be the same for both sides of the screen.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "exclusiveMaximum": 1.0
                    },
                    "screen_beam_diffuse_visible_transmittance": {
                        "type": "number",
                        "note": "The beam-diffuse visible transmittance of the screen material at normal incidence averaged over the visible spectrum range of solar radiation. Assumed to be the same for both sides of the screen.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "exclusiveMaximum": 1.0
                    },
                    "screen_beam_diffuse_visible_reflectance": {
                        "type": "number",
                        "note": "Beam-diffuse visible reflectance of the screen material at normal incidence averaged over the visible spectrum range of solar radiation. Assumed to be the same for both sides of the screen.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "exclusiveMaximum": 1.0
                    },
                    "screen_infrared_transmittance": {
                        "type": "number",
                        "note": "The long-wave hemispherical transmittance of the screen material. Assumed to be the same for both sides of the screen.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "exclusiveMaximum": 1.0,
                        "default": 0.02
                    },
                    "screen_infrared_emissivity": {
                        "type": "number",
                        "note": "The long-wave hemispherical emissivity of the screen material. Assumed to be the same for both sides of the screen.",
                        "units": "dimensionless",
                        "exclusiveMaximum": 1.0,
                        "exclusiveMinimum": 0.0,
                        "default": 0.93
                    },
                    "screen_wire_spacing": {
                        "type": "number",
                        "note": "Spacing assumed to be the same in both directions.",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "ip-units": "in",
                        "default": 0.025
                    },
                    "screen_wire_diameter": {
                        "type": "number",
                        "note": "Diameter assumed to be the same in both directions.",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "ip-units": "in",
                        "default": 0.005
                    }
                },
                "required": [
                    "screen_beam_diffuse_solar_transmittance",
                    "screen_beam_diffuse_solar_reflectance",
                    "screen_beam_beam_visible_transmittance",
                    "screen_beam_diffuse_visible_transmittance",
                    "screen_beam_diffuse_visible_reflectance"
                ]
            }
        },
        "group": "Surface Construction Elements",
        "name": {
            "type": "string",
            "note": "Enter a unique name for this window screen material.",
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
                "screen_beam_beam_solar_transmittance": {
                    "field_name": "Screen Beam-Beam Solar Transmittance",
                    "field_type": "n"
                },
                "screen_beam_diffuse_solar_transmittance": {
                    "field_name": "Screen Beam-Diffuse Solar Transmittance",
                    "field_type": "n"
                },
                "screen_beam_diffuse_solar_reflectance": {
                    "field_name": "Screen Beam-Diffuse Solar Reflectance",
                    "field_type": "n"
                },
                "screen_beam_beam_visible_transmittance": {
                    "field_name": "Screen Beam-Beam Visible Transmittance",
                    "field_type": "n"
                },
                "screen_beam_diffuse_visible_transmittance": {
                    "field_name": "Screen Beam-Diffuse Visible Transmittance",
                    "field_type": "n"
                },
                "screen_beam_diffuse_visible_reflectance": {
                    "field_name": "Screen Beam-Diffuse Visible Reflectance",
                    "field_type": "n"
                },
                "screen_infrared_transmittance": {
                    "field_name": "Screen Infrared Transmittance",
                    "field_type": "n"
                },
                "screen_infrared_emissivity": {
                    "field_name": "Screen Infrared Emissivity",
                    "field_type": "n"
                },
                "screen_wire_spacing": {
                    "field_name": "Screen Wire Spacing",
                    "field_type": "n"
                },
                "screen_wire_diameter": {
                    "field_name": "Screen Wire Diameter",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "screen_beam_beam_solar_transmittance",
                "screen_beam_diffuse_solar_transmittance",
                "screen_beam_diffuse_solar_reflectance",
                "screen_beam_beam_visible_transmittance",
                "screen_beam_diffuse_visible_transmittance",
                "screen_beam_diffuse_visible_reflectance",
                "screen_infrared_transmittance",
                "screen_infrared_emissivity",
                "screen_wire_spacing",
                "screen_wire_diameter"
            ],
            "alphas": {
                "fields": [
                    "name"
                ]
            },
            "numerics": {
                "fields": [
                    "screen_beam_beam_solar_transmittance",
                    "screen_beam_diffuse_solar_transmittance",
                    "screen_beam_diffuse_solar_reflectance",
                    "screen_beam_beam_visible_transmittance",
                    "screen_beam_diffuse_visible_transmittance",
                    "screen_beam_diffuse_visible_reflectance",
                    "screen_infrared_transmittance",
                    "screen_infrared_emissivity",
                    "screen_wire_spacing",
                    "screen_wire_diameter"
                ]
            }
        },
        "type": "object",
        "memo": "Equivalent layer window screen physical properties. Can only be located on the exterior side of a window construction.",
        "min_fields": 11.0
    }
}
```
