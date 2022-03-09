```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "spectrum_data_type": {
                    "type": "string",
                    "enum": [
                        "Solar",
                        "Visible"
                    ]
                },
                "wavelength": {
                    "type": "number",
                    "units": "micron"
                },
                "spectrum": {
                    "type": "number"
                },
                "wavelength_1": {
                    "type": "number",
                    "units": "micron"
                },
                "spectrum_2": {
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
                            "spectrum": {
                                "type": "number"
                            }
                        },
                        "type": "object"
                    }
                }
            },
            "required": [
                "spectrum_data_type"
            ]
        }
    },
    "group": "Location and Climate",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "SpectrumDataNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "spectrum_data_type": {
                "field_name": "Spectrum Data Type",
                "field_type": "a"
            },
            "wavelength": {
                "field_name": "Wavelength",
                "field_type": "n"
            },
            "spectrum": {
                "field_name": "Spectrum",
                "field_type": "n"
            },
            "wavelength_1": {
                "field_name": "Wavelength",
                "field_type": "n"
            },
            "spectrum_2": {
                "field_name": "Spectrum",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "spectrum_data_type",
            "wavelength",
            "spectrum",
            "wavelength_1",
            "spectrum_2"
        ],
        "alphas": {
            "fields": [
                "name",
                "spectrum_data_type"
            ]
        },
        "numerics": {
            "fields": [
                "wavelength",
                "spectrum",
                "wavelength_1",
                "spectrum_2"
            ],
            "extensions": [
                "wavelength",
                "spectrum"
            ]
        },
        "extensibles": [
            "wavelength",
            "spectrum"
        ],
        "extension": "extensions"
    },
    "type": "object",
    "memo": "Spectrum Data Type is followed by up to 107 sets of normal-incidence measured values of [wavelength, spectrum] for wavelengths covering the solar (0.25 to 2.5 microns) or visible spectrum (0.38 to 0.78 microns)",
    "min_fields": 8.0,
    "extensible_size": 2.0
}
```
