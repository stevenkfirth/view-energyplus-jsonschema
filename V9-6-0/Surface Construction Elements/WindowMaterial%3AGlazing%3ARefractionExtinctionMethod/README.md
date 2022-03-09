```
{
    "WindowMaterial:Glazing:RefractionExtinctionMethod": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "thickness": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "ip-units": "in"
                    },
                    "solar_index_of_refraction": {
                        "type": "number",
                        "exclusiveMinimum": 1.0
                    },
                    "solar_extinction_coefficient": {
                        "type": "number",
                        "units": "1/m",
                        "exclusiveMinimum": 0.0
                    },
                    "visible_index_of_refraction": {
                        "type": "number",
                        "exclusiveMinimum": 1.0
                    },
                    "visible_extinction_coefficient": {
                        "type": "number",
                        "units": "1/m",
                        "exclusiveMinimum": 0.0
                    },
                    "infrared_transmittance_at_normal_incidence": {
                        "type": "number",
                        "exclusiveMaximum": 1.0,
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "infrared_hemispherical_emissivity": {
                        "type": "number",
                        "note": "Emissivity of front and back side assumed equal",
                        "exclusiveMaximum": 1.0,
                        "exclusiveMinimum": 0.0,
                        "default": 0.84
                    },
                    "conductivity": {
                        "type": "number",
                        "units": "W/m-K",
                        "exclusiveMinimum": 0.0,
                        "default": 0.9
                    },
                    "dirt_correction_factor_for_solar_and_visible_transmittance": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0,
                        "default": 1.0
                    },
                    "solar_diffusing": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No"
                    }
                },
                "required": [
                    "thickness",
                    "solar_index_of_refraction",
                    "solar_extinction_coefficient",
                    "visible_index_of_refraction",
                    "visible_extinction_coefficient"
                ]
            }
        },
        "group": "Surface Construction Elements",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "GlazingMaterialName",
                "MaterialName"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "thickness": {
                    "field_name": "Thickness",
                    "field_type": "n"
                },
                "solar_index_of_refraction": {
                    "field_name": "Solar Index of Refraction",
                    "field_type": "n"
                },
                "solar_extinction_coefficient": {
                    "field_name": "Solar Extinction Coefficient",
                    "field_type": "n"
                },
                "visible_index_of_refraction": {
                    "field_name": "Visible Index of Refraction",
                    "field_type": "n"
                },
                "visible_extinction_coefficient": {
                    "field_name": "Visible Extinction Coefficient",
                    "field_type": "n"
                },
                "infrared_transmittance_at_normal_incidence": {
                    "field_name": "Infrared Transmittance at Normal Incidence",
                    "field_type": "n"
                },
                "infrared_hemispherical_emissivity": {
                    "field_name": "Infrared Hemispherical Emissivity",
                    "field_type": "n"
                },
                "conductivity": {
                    "field_name": "Conductivity",
                    "field_type": "n"
                },
                "dirt_correction_factor_for_solar_and_visible_transmittance": {
                    "field_name": "Dirt Correction Factor for Solar and Visible Transmittance",
                    "field_type": "n"
                },
                "solar_diffusing": {
                    "field_name": "Solar Diffusing",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "thickness",
                "solar_index_of_refraction",
                "solar_extinction_coefficient",
                "visible_index_of_refraction",
                "visible_extinction_coefficient",
                "infrared_transmittance_at_normal_incidence",
                "infrared_hemispherical_emissivity",
                "conductivity",
                "dirt_correction_factor_for_solar_and_visible_transmittance",
                "solar_diffusing"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "solar_diffusing"
                ]
            },
            "numerics": {
                "fields": [
                    "thickness",
                    "solar_index_of_refraction",
                    "solar_extinction_coefficient",
                    "visible_index_of_refraction",
                    "visible_extinction_coefficient",
                    "infrared_transmittance_at_normal_incidence",
                    "infrared_hemispherical_emissivity",
                    "conductivity",
                    "dirt_correction_factor_for_solar_and_visible_transmittance"
                ]
            }
        },
        "type": "object",
        "memo": "Glass material properties for Windows or Glass Doors Index of Refraction/Extinction Coefficient input method Not to be used for coated glass"
    }
}
```
