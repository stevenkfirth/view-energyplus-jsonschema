```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "optical_data_type": {
                    "type": "string",
                    "enum": [
                        "BSDF",
                        "Spectral",
                        "SpectralAndAngle",
                        "SpectralAverage"
                    ]
                },
                "window_glass_spectral_data_set_name": {
                    "type": "string",
                    "note": "Used only when Optical Data Type = Spectral",
                    "data_type": "object_list",
                    "object_list": [
                        "SpectralDataSets"
                    ]
                },
                "thickness": {
                    "type": "number",
                    "units": "m",
                    "exclusiveMinimum": 0.0,
                    "ip-units": "in"
                },
                "solar_transmittance_at_normal_incidence": {
                    "type": "number",
                    "note": "Used only when Optical Data Type = SpectralAverage",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "front_side_solar_reflectance_at_normal_incidence": {
                    "type": "number",
                    "note": "Used only when Optical Data Type = SpectralAverage Front Side is side closest to outdoor air",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "back_side_solar_reflectance_at_normal_incidence": {
                    "type": "number",
                    "note": "Used only when Optical Data Type = SpectralAverage Back Side is side closest to zone air",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "visible_transmittance_at_normal_incidence": {
                    "type": "number",
                    "note": "Used only when Optical Data Type = SpectralAverage",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "front_side_visible_reflectance_at_normal_incidence": {
                    "type": "number",
                    "note": "Used only when Optical Data Type = SpectralAverage",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "back_side_visible_reflectance_at_normal_incidence": {
                    "type": "number",
                    "note": "Used only when Optical Data Type = SpectralAverage",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "infrared_transmittance_at_normal_incidence": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0
                },
                "front_side_infrared_hemispherical_emissivity": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "exclusiveMaximum": 1.0,
                    "default": 0.84
                },
                "back_side_infrared_hemispherical_emissivity": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "exclusiveMaximum": 1.0,
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
                },
                "young_s_modulus": {
                    "type": "number",
                    "note": "coefficient used for deflection calculations. Used only with complex fenestration when deflection model is set to TemperatureAndPressureInput",
                    "units": "Pa",
                    "exclusiveMinimum": 0.0,
                    "default": 72000000000.0
                },
                "poisson_s_ratio": {
                    "type": "number",
                    "note": "coefficient used for deflection calculations. Used only with complex fenestration when deflection model is set to TemperatureAndPressureInput",
                    "exclusiveMinimum": 0.0,
                    "exclusiveMaximum": 1.0,
                    "default": 0.22
                },
                "window_glass_spectral_and_incident_angle_transmittance_data_set_table_name": {
                    "type": "string",
                    "note": "Used only when Optical Data Type = SpectralAndAngle",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "window_glass_spectral_and_incident_angle_front_reflectance_data_set_table_name": {
                    "type": "string",
                    "note": "Used only when Optical Data Type = SpectralAndAngle",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "window_glass_spectral_and_incident_angle_back_reflectance_data_set_table_name": {
                    "type": "string",
                    "note": "Used only when Optical Data Type = SpectralAndAngle",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                }
            },
            "required": [
                "optical_data_type",
                "thickness"
            ]
        }
    },
    "group": "Surface Construction Elements",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "CFSGlazingName",
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
            "optical_data_type": {
                "field_name": "Optical Data Type",
                "field_type": "a"
            },
            "window_glass_spectral_data_set_name": {
                "field_name": "Window Glass Spectral Data Set Name",
                "field_type": "a"
            },
            "thickness": {
                "field_name": "Thickness",
                "field_type": "n"
            },
            "solar_transmittance_at_normal_incidence": {
                "field_name": "Solar Transmittance at Normal Incidence",
                "field_type": "n"
            },
            "front_side_solar_reflectance_at_normal_incidence": {
                "field_name": "Front Side Solar Reflectance at Normal Incidence",
                "field_type": "n"
            },
            "back_side_solar_reflectance_at_normal_incidence": {
                "field_name": "Back Side Solar Reflectance at Normal Incidence",
                "field_type": "n"
            },
            "visible_transmittance_at_normal_incidence": {
                "field_name": "Visible Transmittance at Normal Incidence",
                "field_type": "n"
            },
            "front_side_visible_reflectance_at_normal_incidence": {
                "field_name": "Front Side Visible Reflectance at Normal Incidence",
                "field_type": "n"
            },
            "back_side_visible_reflectance_at_normal_incidence": {
                "field_name": "Back Side Visible Reflectance at Normal Incidence",
                "field_type": "n"
            },
            "infrared_transmittance_at_normal_incidence": {
                "field_name": "Infrared Transmittance at Normal Incidence",
                "field_type": "n"
            },
            "front_side_infrared_hemispherical_emissivity": {
                "field_name": "Front Side Infrared Hemispherical Emissivity",
                "field_type": "n"
            },
            "back_side_infrared_hemispherical_emissivity": {
                "field_name": "Back Side Infrared Hemispherical Emissivity",
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
            },
            "young_s_modulus": {
                "field_name": "Young's modulus",
                "field_type": "n"
            },
            "poisson_s_ratio": {
                "field_name": "Poisson's ratio",
                "field_type": "n"
            },
            "window_glass_spectral_and_incident_angle_transmittance_data_set_table_name": {
                "field_name": "Window Glass Spectral and Incident Angle Transmittance Data Set Table Name",
                "field_type": "a"
            },
            "window_glass_spectral_and_incident_angle_front_reflectance_data_set_table_name": {
                "field_name": "Window Glass Spectral and Incident Angle Front Reflectance Data Set Table Name",
                "field_type": "a"
            },
            "window_glass_spectral_and_incident_angle_back_reflectance_data_set_table_name": {
                "field_name": "Window Glass Spectral and Incident Angle Back Reflectance Data Set Table Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "optical_data_type",
            "window_glass_spectral_data_set_name",
            "thickness",
            "solar_transmittance_at_normal_incidence",
            "front_side_solar_reflectance_at_normal_incidence",
            "back_side_solar_reflectance_at_normal_incidence",
            "visible_transmittance_at_normal_incidence",
            "front_side_visible_reflectance_at_normal_incidence",
            "back_side_visible_reflectance_at_normal_incidence",
            "infrared_transmittance_at_normal_incidence",
            "front_side_infrared_hemispherical_emissivity",
            "back_side_infrared_hemispherical_emissivity",
            "conductivity",
            "dirt_correction_factor_for_solar_and_visible_transmittance",
            "solar_diffusing",
            "young_s_modulus",
            "poisson_s_ratio",
            "window_glass_spectral_and_incident_angle_transmittance_data_set_table_name",
            "window_glass_spectral_and_incident_angle_front_reflectance_data_set_table_name",
            "window_glass_spectral_and_incident_angle_back_reflectance_data_set_table_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "optical_data_type",
                "window_glass_spectral_data_set_name",
                "solar_diffusing",
                "window_glass_spectral_and_incident_angle_transmittance_data_set_table_name",
                "window_glass_spectral_and_incident_angle_front_reflectance_data_set_table_name",
                "window_glass_spectral_and_incident_angle_back_reflectance_data_set_table_name"
            ]
        },
        "numerics": {
            "fields": [
                "thickness",
                "solar_transmittance_at_normal_incidence",
                "front_side_solar_reflectance_at_normal_incidence",
                "back_side_solar_reflectance_at_normal_incidence",
                "visible_transmittance_at_normal_incidence",
                "front_side_visible_reflectance_at_normal_incidence",
                "back_side_visible_reflectance_at_normal_incidence",
                "infrared_transmittance_at_normal_incidence",
                "front_side_infrared_hemispherical_emissivity",
                "back_side_infrared_hemispherical_emissivity",
                "conductivity",
                "dirt_correction_factor_for_solar_and_visible_transmittance",
                "young_s_modulus",
                "poisson_s_ratio"
            ]
        }
    },
    "type": "object",
    "memo": "Glass material properties for Windows or Glass Doors Transmittance/Reflectance input method.",
    "min_fields": 14.0
}
```
