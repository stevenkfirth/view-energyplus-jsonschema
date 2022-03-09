```
{
    "WindowMaterial:Glazing:EquivalentLayer": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "optical_data_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Spectral",
                            "SpectralAverage"
                        ],
                        "default": "SpectralAverage",
                        "note": "Spectral is not currently supported and SpectralAverage is the default."
                    },
                    "window_glass_spectral_data_set_name": {
                        "type": "string",
                        "note": "Spectral data is not currently supported. Used only when Optical Data Type = Spectral",
                        "data_type": "object_list",
                        "object_list": [
                            "SpectralDataSets"
                        ]
                    },
                    "front_side_beam_beam_solar_transmittance": {
                        "type": "number",
                        "note": "Used only when Optical Data Type = SpectralAverage",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "back_side_beam_beam_solar_transmittance": {
                        "type": "number",
                        "note": "Used only when Optical Data Type = SpectralAverage",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "front_side_beam_beam_solar_reflectance": {
                        "type": "number",
                        "note": "Used only when Optical Data Type = SpectralAverage Front Side is side closest to outdoor air",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "back_side_beam_beam_solar_reflectance": {
                        "type": "number",
                        "note": "Used only when Optical Data Type = SpectralAverage Back Side is side closest to zone air",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "front_side_beam_beam_visible_solar_transmittance": {
                        "type": "number",
                        "note": "Used only when Optical Data Type = SpectralAverage",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "back_side_beam_beam_visible_solar_transmittance": {
                        "type": "number",
                        "note": "Used only when Optical Data Type = SpectralAverage",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "front_side_beam_beam_visible_solar_reflectance": {
                        "type": "number",
                        "note": "Used only when Optical Data Type = SpectralAverage Front Side is side closest to outdoor air",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "back_side_beam_beam_visible_solar_reflectance": {
                        "type": "number",
                        "note": "Used only when Optical Data Type = SpectralAverage Back Side is side closest to zone air",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "front_side_beam_diffuse_solar_transmittance": {
                        "type": "number",
                        "note": "Used only when Optical Data Type = SpectralAverage",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "back_side_beam_diffuse_solar_transmittance": {
                        "type": "number",
                        "note": "Used only when Optical Data Type = SpectralAverage",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "front_side_beam_diffuse_solar_reflectance": {
                        "type": "number",
                        "note": "Used only when Optical Data Type = SpectralAverage Front Side is side closest to outdoor air",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "back_side_beam_diffuse_solar_reflectance": {
                        "type": "number",
                        "note": "Used only when Optical Data Type = SpectralAverage Back Side is side closest to zone air",
                        "minimum": 0.0,
                        "units": "dimensionless",
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "front_side_beam_diffuse_visible_solar_transmittance": {
                        "type": "number",
                        "note": "Used only when Optical Data Type = SpectralAverage",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "back_side_beam_diffuse_visible_solar_transmittance": {
                        "type": "number",
                        "note": "Used only when Optical Data Type = SpectralAverage",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "front_side_beam_diffuse_visible_solar_reflectance": {
                        "type": "number",
                        "note": "Used only when Optical Data Type = SpectralAverage Front Side is side closest to outdoor air",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "back_side_beam_diffuse_visible_solar_reflectance": {
                        "type": "number",
                        "note": "Used only when Optical Data Type = SpectralAverage Back Side is side closest to zone air",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "diffuse_diffuse_solar_transmittance": {
                        "note": "Used only when Optical Data Type = SpectralAverage If this field is autocalculate, then the diffuse-diffuse solar transmittance is automatically estimated from other inputs and used in subsequent calculations. If this field is zero or positive, then the value entered here will be used.",
                        "units": "dimensionless",
                        "default": "Autocalculate",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.0,
                                "maximum": 1.0
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
                    "front_side_diffuse_diffuse_solar_reflectance": {
                        "note": "Used only when Optical Data Type = SpectralAverage If this field is autocalculate, then the front diffuse-diffuse solar reflectance is automatically estimated from other inputs and used in subsequent calculations. If this field is zero or positive, then the value entered here will be used. Front Side is side closest to outdoor air.",
                        "units": "dimensionless",
                        "default": "Autocalculate",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.0,
                                "maximum": 1.0
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
                    "back_side_diffuse_diffuse_solar_reflectance": {
                        "note": "Used only when Optical Data Type = SpectralAverage If this field is autocalculate, then the back diffuse-diffuse solar reflectance is automatically estimated from other inputs and used in subsequent calculations. If this field is zero or positive, then the value entered here will be used. Back side is side closest to indoor air.",
                        "units": "dimensionless",
                        "default": "Autocalculate",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.0,
                                "maximum": 1.0
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
                    "diffuse_diffuse_visible_solar_transmittance": {
                        "note": "Used only when Optical Data Type = SpectralAverage This input field is not used currently.",
                        "units": "dimensionless",
                        "default": "Autocalculate",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.0,
                                "maximum": 1.0
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
                    "front_side_diffuse_diffuse_visible_solar_reflectance": {
                        "note": "Used only when Optical Data Type = SpectralAverage This input field is not used currently.",
                        "units": "dimensionless",
                        "default": "Autocalculate",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.0,
                                "maximum": 1.0
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
                    "back_side_diffuse_diffuse_visible_solar_reflectance": {
                        "note": "Used only when Optical Data Type = SpectralAverage This input field is not used currently.",
                        "units": "dimensionless",
                        "default": "Autocalculate",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.0,
                                "maximum": 1.0
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
                    "infrared_transmittance_applies_to_front_and_back_": {
                        "type": "number",
                        "note": "The long-wave hemispherical transmittance of the glazing. Assumed to be the same for both sides of the glazing.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "front_side_infrared_emissivity": {
                        "type": "number",
                        "note": "The front side long-wave hemispherical emissivity of the glazing.",
                        "units": "dimensionless",
                        "exclusiveMinimum": 0.0,
                        "exclusiveMaximum": 1.0,
                        "default": 0.84
                    },
                    "back_side_infrared_emissivity": {
                        "type": "number",
                        "note": "The back side long-wave hemispherical emissivity of the glazing.",
                        "units": "dimensionless",
                        "exclusiveMinimum": 0.0,
                        "exclusiveMaximum": 1.0,
                        "default": 0.84
                    },
                    "thermal_resistance": {
                        "type": "number",
                        "note": "This is the R-Value in SI for the glass. The default value is an approximation for a single layer of glass at 1/4\" inch thickness. This field is used only for movable insulation defined with this material type.",
                        "units": "m2-K/W",
                        "exclusiveMinimum": 0.0,
                        "default": 0.158
                    }
                },
                "required": [
                    "front_side_beam_beam_solar_transmittance",
                    "back_side_beam_beam_solar_transmittance",
                    "front_side_beam_beam_solar_reflectance",
                    "back_side_beam_beam_solar_reflectance"
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
                "optical_data_type": {
                    "field_name": "Optical Data Type",
                    "field_type": "a"
                },
                "window_glass_spectral_data_set_name": {
                    "field_name": "Window Glass Spectral Data Set Name",
                    "field_type": "a"
                },
                "front_side_beam_beam_solar_transmittance": {
                    "field_name": "Front Side Beam-Beam Solar Transmittance",
                    "field_type": "n"
                },
                "back_side_beam_beam_solar_transmittance": {
                    "field_name": "Back Side Beam-Beam Solar Transmittance",
                    "field_type": "n"
                },
                "front_side_beam_beam_solar_reflectance": {
                    "field_name": "Front Side Beam-Beam Solar Reflectance",
                    "field_type": "n"
                },
                "back_side_beam_beam_solar_reflectance": {
                    "field_name": "Back Side Beam-Beam Solar Reflectance",
                    "field_type": "n"
                },
                "front_side_beam_beam_visible_solar_transmittance": {
                    "field_name": "Front Side Beam-Beam Visible Solar Transmittance",
                    "field_type": "n"
                },
                "back_side_beam_beam_visible_solar_transmittance": {
                    "field_name": "Back Side Beam-Beam Visible Solar Transmittance",
                    "field_type": "n"
                },
                "front_side_beam_beam_visible_solar_reflectance": {
                    "field_name": "Front Side Beam-Beam Visible Solar Reflectance",
                    "field_type": "n"
                },
                "back_side_beam_beam_visible_solar_reflectance": {
                    "field_name": "Back Side Beam-Beam Visible Solar Reflectance",
                    "field_type": "n"
                },
                "front_side_beam_diffuse_solar_transmittance": {
                    "field_name": "Front Side Beam-Diffuse Solar Transmittance",
                    "field_type": "n"
                },
                "back_side_beam_diffuse_solar_transmittance": {
                    "field_name": "Back Side Beam-Diffuse Solar Transmittance",
                    "field_type": "n"
                },
                "front_side_beam_diffuse_solar_reflectance": {
                    "field_name": "Front Side Beam-Diffuse Solar Reflectance",
                    "field_type": "n"
                },
                "back_side_beam_diffuse_solar_reflectance": {
                    "field_name": "Back Side Beam-Diffuse Solar Reflectance",
                    "field_type": "n"
                },
                "front_side_beam_diffuse_visible_solar_transmittance": {
                    "field_name": "Front Side Beam-Diffuse Visible Solar Transmittance",
                    "field_type": "n"
                },
                "back_side_beam_diffuse_visible_solar_transmittance": {
                    "field_name": "Back Side Beam-Diffuse Visible Solar Transmittance",
                    "field_type": "n"
                },
                "front_side_beam_diffuse_visible_solar_reflectance": {
                    "field_name": "Front Side Beam-Diffuse Visible Solar Reflectance",
                    "field_type": "n"
                },
                "back_side_beam_diffuse_visible_solar_reflectance": {
                    "field_name": "Back Side Beam-Diffuse Visible Solar Reflectance",
                    "field_type": "n"
                },
                "diffuse_diffuse_solar_transmittance": {
                    "field_name": "Diffuse-Diffuse Solar Transmittance",
                    "field_type": "n"
                },
                "front_side_diffuse_diffuse_solar_reflectance": {
                    "field_name": "Front Side Diffuse-Diffuse Solar Reflectance",
                    "field_type": "n"
                },
                "back_side_diffuse_diffuse_solar_reflectance": {
                    "field_name": "Back Side Diffuse-Diffuse Solar Reflectance",
                    "field_type": "n"
                },
                "diffuse_diffuse_visible_solar_transmittance": {
                    "field_name": "Diffuse-Diffuse Visible Solar Transmittance",
                    "field_type": "n"
                },
                "front_side_diffuse_diffuse_visible_solar_reflectance": {
                    "field_name": "Front Side Diffuse-Diffuse Visible Solar Reflectance",
                    "field_type": "n"
                },
                "back_side_diffuse_diffuse_visible_solar_reflectance": {
                    "field_name": "Back Side Diffuse-Diffuse Visible Solar Reflectance",
                    "field_type": "n"
                },
                "infrared_transmittance_applies_to_front_and_back_": {
                    "field_name": "Infrared Transmittance (applies to front and back)",
                    "field_type": "n"
                },
                "front_side_infrared_emissivity": {
                    "field_name": "Front Side Infrared Emissivity",
                    "field_type": "n"
                },
                "back_side_infrared_emissivity": {
                    "field_name": "Back Side Infrared Emissivity",
                    "field_type": "n"
                },
                "thermal_resistance": {
                    "field_name": "Thermal Resistance",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "optical_data_type",
                "window_glass_spectral_data_set_name",
                "front_side_beam_beam_solar_transmittance",
                "back_side_beam_beam_solar_transmittance",
                "front_side_beam_beam_solar_reflectance",
                "back_side_beam_beam_solar_reflectance",
                "front_side_beam_beam_visible_solar_transmittance",
                "back_side_beam_beam_visible_solar_transmittance",
                "front_side_beam_beam_visible_solar_reflectance",
                "back_side_beam_beam_visible_solar_reflectance",
                "front_side_beam_diffuse_solar_transmittance",
                "back_side_beam_diffuse_solar_transmittance",
                "front_side_beam_diffuse_solar_reflectance",
                "back_side_beam_diffuse_solar_reflectance",
                "front_side_beam_diffuse_visible_solar_transmittance",
                "back_side_beam_diffuse_visible_solar_transmittance",
                "front_side_beam_diffuse_visible_solar_reflectance",
                "back_side_beam_diffuse_visible_solar_reflectance",
                "diffuse_diffuse_solar_transmittance",
                "front_side_diffuse_diffuse_solar_reflectance",
                "back_side_diffuse_diffuse_solar_reflectance",
                "diffuse_diffuse_visible_solar_transmittance",
                "front_side_diffuse_diffuse_visible_solar_reflectance",
                "back_side_diffuse_diffuse_visible_solar_reflectance",
                "infrared_transmittance_applies_to_front_and_back_",
                "front_side_infrared_emissivity",
                "back_side_infrared_emissivity",
                "thermal_resistance"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "optical_data_type",
                    "window_glass_spectral_data_set_name"
                ]
            },
            "numerics": {
                "fields": [
                    "front_side_beam_beam_solar_transmittance",
                    "back_side_beam_beam_solar_transmittance",
                    "front_side_beam_beam_solar_reflectance",
                    "back_side_beam_beam_solar_reflectance",
                    "front_side_beam_beam_visible_solar_transmittance",
                    "back_side_beam_beam_visible_solar_transmittance",
                    "front_side_beam_beam_visible_solar_reflectance",
                    "back_side_beam_beam_visible_solar_reflectance",
                    "front_side_beam_diffuse_solar_transmittance",
                    "back_side_beam_diffuse_solar_transmittance",
                    "front_side_beam_diffuse_solar_reflectance",
                    "back_side_beam_diffuse_solar_reflectance",
                    "front_side_beam_diffuse_visible_solar_transmittance",
                    "back_side_beam_diffuse_visible_solar_transmittance",
                    "front_side_beam_diffuse_visible_solar_reflectance",
                    "back_side_beam_diffuse_visible_solar_reflectance",
                    "diffuse_diffuse_solar_transmittance",
                    "front_side_diffuse_diffuse_solar_reflectance",
                    "back_side_diffuse_diffuse_solar_reflectance",
                    "diffuse_diffuse_visible_solar_transmittance",
                    "front_side_diffuse_diffuse_visible_solar_reflectance",
                    "back_side_diffuse_diffuse_visible_solar_reflectance",
                    "infrared_transmittance_applies_to_front_and_back_",
                    "front_side_infrared_emissivity",
                    "back_side_infrared_emissivity",
                    "thermal_resistance"
                ]
            }
        },
        "type": "object",
        "memo": "Glass material properties for Windows or Glass Doors Transmittance/Reflectance input method.",
        "min_fields": 11.0
    }
}
```
