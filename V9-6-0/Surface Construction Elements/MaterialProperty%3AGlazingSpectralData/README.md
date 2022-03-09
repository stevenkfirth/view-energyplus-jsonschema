```
{
    "MaterialProperty:GlazingSpectralData": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "wavelength_1": {
                        "type": "number",
                        "units": "micron"
                    },
                    "transmittance_1": {
                        "type": "number"
                    },
                    "front_reflectance_1": {
                        "type": "number"
                    },
                    "back_reflectance_1": {
                        "type": "number"
                    },
                    "wavelength_2": {
                        "type": "number",
                        "units": "micron"
                    },
                    "transmittance_2": {
                        "type": "number"
                    },
                    "front_reflectance_2": {
                        "type": "number"
                    },
                    "back_reflectance_2": {
                        "type": "number"
                    },
                    "wavelength_3": {
                        "type": "number",
                        "units": "micron"
                    },
                    "transmittance_3": {
                        "type": "number"
                    },
                    "front_reflectance_3": {
                        "type": "number"
                    },
                    "back_reflectance_3": {
                        "type": "number"
                    },
                    "wavelength_4": {
                        "type": "number",
                        "units": "micron"
                    },
                    "transmittance_4": {
                        "type": "number"
                    },
                    "front_reflectance_4": {
                        "type": "number"
                    },
                    "back_reflectance_4": {
                        "type": "number"
                    },
                    "extensions": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "wavelength": {
                                    "type": "number",
                                    "units": "micron"
                                },
                                "transmittance": {
                                    "type": "number"
                                },
                                "front_reflectance": {
                                    "type": "number"
                                },
                                "back_reflectance": {
                                    "type": "number"
                                }
                            },
                            "type": "object"
                        }
                    }
                }
            }
        },
        "group": "Surface Construction Elements",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "SpectralDataSets"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "wavelength_1": {
                    "field_name": "Wavelength 1",
                    "field_type": "n"
                },
                "transmittance_1": {
                    "field_name": "Transmittance 1",
                    "field_type": "n"
                },
                "front_reflectance_1": {
                    "field_name": "Front Reflectance 1",
                    "field_type": "n"
                },
                "back_reflectance_1": {
                    "field_name": "Back Reflectance 1",
                    "field_type": "n"
                },
                "wavelength_2": {
                    "field_name": "Wavelength 2",
                    "field_type": "n"
                },
                "transmittance_2": {
                    "field_name": "Transmittance 2",
                    "field_type": "n"
                },
                "front_reflectance_2": {
                    "field_name": "Front Reflectance 2",
                    "field_type": "n"
                },
                "back_reflectance_2": {
                    "field_name": "Back Reflectance 2",
                    "field_type": "n"
                },
                "wavelength_3": {
                    "field_name": "Wavelength 3",
                    "field_type": "n"
                },
                "transmittance_3": {
                    "field_name": "Transmittance 3",
                    "field_type": "n"
                },
                "front_reflectance_3": {
                    "field_name": "Front Reflectance 3",
                    "field_type": "n"
                },
                "back_reflectance_3": {
                    "field_name": "Back Reflectance 3",
                    "field_type": "n"
                },
                "wavelength_4": {
                    "field_name": "Wavelength 4",
                    "field_type": "n"
                },
                "transmittance_4": {
                    "field_name": "Transmittance 4",
                    "field_type": "n"
                },
                "front_reflectance_4": {
                    "field_name": "Front Reflectance 4",
                    "field_type": "n"
                },
                "back_reflectance_4": {
                    "field_name": "Back Reflectance 4",
                    "field_type": "n"
                },
                "wavelength": {
                    "field_name": "Wavelength",
                    "field_type": "n"
                },
                "transmittance": {
                    "field_name": "Transmittance",
                    "field_type": "n"
                },
                "front_reflectance": {
                    "field_name": "Front Reflectance",
                    "field_type": "n"
                },
                "back_reflectance": {
                    "field_name": "Back Reflectance",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "wavelength_1",
                "transmittance_1",
                "front_reflectance_1",
                "back_reflectance_1",
                "wavelength_2",
                "transmittance_2",
                "front_reflectance_2",
                "back_reflectance_2",
                "wavelength_3",
                "transmittance_3",
                "front_reflectance_3",
                "back_reflectance_3",
                "wavelength_4",
                "transmittance_4",
                "front_reflectance_4",
                "back_reflectance_4"
            ],
            "alphas": {
                "fields": [
                    "name"
                ]
            },
            "numerics": {
                "fields": [
                    "wavelength_1",
                    "transmittance_1",
                    "front_reflectance_1",
                    "back_reflectance_1",
                    "wavelength_2",
                    "transmittance_2",
                    "front_reflectance_2",
                    "back_reflectance_2",
                    "wavelength_3",
                    "transmittance_3",
                    "front_reflectance_3",
                    "back_reflectance_3",
                    "wavelength_4",
                    "transmittance_4",
                    "front_reflectance_4",
                    "back_reflectance_4"
                ],
                "extensions": [
                    "wavelength",
                    "transmittance",
                    "front_reflectance",
                    "back_reflectance"
                ]
            },
            "extensibles": [
                "wavelength",
                "transmittance",
                "front_reflectance",
                "back_reflectance"
            ],
            "extension": "extensions"
        },
        "type": "object",
        "memo": "Name is followed by up to 800 sets of normal-incidence measured values of [wavelength, transmittance, front reflectance, back reflectance] for wavelengths covering the solar spectrum (from about 0.25 to 2.5 microns)",
        "extensible_size": 4.0,
        "format": "Spectral"
    }
}
```
