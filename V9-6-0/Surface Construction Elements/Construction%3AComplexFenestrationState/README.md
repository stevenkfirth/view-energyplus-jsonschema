```
{
    "Construction:ComplexFenestrationState": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "basis_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "LBNLWINDOW",
                            "UserDefined"
                        ],
                        "default": "LBNLWINDOW"
                    },
                    "basis_symmetry_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Axisymmetric",
                            "None"
                        ],
                        "default": "None"
                    },
                    "window_thermal_model": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "WindowThermalModelParameters"
                        ]
                    },
                    "basis_matrix_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DataMatrices"
                        ]
                    },
                    "solar_optical_complex_front_transmittance_matrix_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DataMatrices"
                        ]
                    },
                    "solar_optical_complex_back_reflectance_matrix_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DataMatrices"
                        ]
                    },
                    "visible_optical_complex_front_transmittance_matrix_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DataMatrices"
                        ]
                    },
                    "visible_optical_complex_back_transmittance_matrix_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DataMatrices"
                        ]
                    },
                    "outside_layer_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "CFSGlazingName",
                            "WindowComplexShades"
                        ]
                    },
                    "outside_layer_directional_front_absoptance_matrix_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DataMatrices"
                        ]
                    },
                    "outside_layer_directional_back_absoptance_matrix_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DataMatrices"
                        ]
                    },
                    "gap_1_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "CFSGap"
                        ]
                    },
                    "cfs_gap_1_directional_front_absoptance_matrix_name": {
                        "type": "string",
                        "note": "Reserved for future use. Leave it blank for this version",
                        "data_type": "object_list",
                        "object_list": [
                            "DataMatrices"
                        ]
                    },
                    "cfs_gap_1_directional_back_absoptance_matrix_name": {
                        "type": "string",
                        "note": "Reserved for future use. Leave it blank for this version",
                        "data_type": "object_list",
                        "object_list": [
                            "DataMatrices"
                        ]
                    },
                    "layer_2_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "CFSGlazingName",
                            "WindowComplexShades"
                        ]
                    },
                    "layer_2_directional_front_absoptance_matrix_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DataMatrices"
                        ]
                    },
                    "layer_2_directional_back_absoptance_matrix_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DataMatrices"
                        ]
                    },
                    "gap_2_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "CFSGap"
                        ]
                    },
                    "gap_2_directional_front_absoptance_matrix_name": {
                        "type": "string",
                        "note": "Reserved for future use. Leave it blank for this version",
                        "data_type": "object_list",
                        "object_list": [
                            "DataMatrices"
                        ]
                    },
                    "gap_2_directional_back_absoptance_matrix_name": {
                        "type": "string",
                        "note": "Reserved for future use. Leave it blank for this version",
                        "data_type": "object_list",
                        "object_list": [
                            "DataMatrices"
                        ]
                    },
                    "layer_3_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "CFSGlazingName",
                            "WindowComplexShades"
                        ]
                    },
                    "layer_3_directional_front_absoptance_matrix_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DataMatrices"
                        ]
                    },
                    "layer_3_directional_back_absoptance_matrix_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DataMatrices"
                        ]
                    },
                    "gap_3_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "CFSGap"
                        ]
                    },
                    "gap_3_directional_front_absoptance_matrix_name": {
                        "type": "string",
                        "note": "Reserved for future use. Leave it blank for this version",
                        "data_type": "object_list",
                        "object_list": [
                            "DataMatrices"
                        ]
                    },
                    "gap_3_directional_back_absoptance_matrix_name": {
                        "type": "string",
                        "note": "Reserved for future use. Leave it blank for this version",
                        "data_type": "object_list",
                        "object_list": [
                            "DataMatrices"
                        ]
                    },
                    "layer_4_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "CFSGlazingName",
                            "WindowComplexShades"
                        ]
                    },
                    "layer_4_directional_front_absoptance_matrix_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DataMatrices"
                        ]
                    },
                    "layer_4_directional_back_absoptance_matrix_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DataMatrices"
                        ]
                    },
                    "gap_4_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "CFSGap"
                        ]
                    },
                    "gap_4_directional_front_absoptance_matrix_name": {
                        "type": "string",
                        "note": "Reserved for future use. Leave it blank for this version",
                        "data_type": "object_list",
                        "object_list": [
                            "DataMatrices"
                        ]
                    },
                    "gap_4_directional_back_absoptance_matrix_name": {
                        "type": "string",
                        "note": "Reserved for future use. Leave it blank for this version",
                        "data_type": "object_list",
                        "object_list": [
                            "DataMatrices"
                        ]
                    },
                    "layer_5_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "CFSGlazingName",
                            "WindowComplexShades"
                        ]
                    },
                    "layer_5_directional_front_absoptance_matrix_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DataMatrices"
                        ]
                    },
                    "layer_5_directional_back_absoptance_matrix_name": {
                        "type": "string"
                    }
                },
                "required": [
                    "window_thermal_model",
                    "basis_matrix_name",
                    "solar_optical_complex_front_transmittance_matrix_name",
                    "solar_optical_complex_back_reflectance_matrix_name",
                    "visible_optical_complex_front_transmittance_matrix_name",
                    "visible_optical_complex_back_transmittance_matrix_name",
                    "outside_layer_name",
                    "outside_layer_directional_front_absoptance_matrix_name",
                    "outside_layer_directional_back_absoptance_matrix_name"
                ]
            }
        },
        "group": "Surface Construction Elements",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "ComplexFenestrationStates"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "basis_type": {
                    "field_name": "Basis Type",
                    "field_type": "a"
                },
                "basis_symmetry_type": {
                    "field_name": "Basis Symmetry Type",
                    "field_type": "a"
                },
                "window_thermal_model": {
                    "field_name": "Window Thermal Model",
                    "field_type": "a"
                },
                "basis_matrix_name": {
                    "field_name": "Basis Matrix Name",
                    "field_type": "a"
                },
                "solar_optical_complex_front_transmittance_matrix_name": {
                    "field_name": "Solar Optical Complex Front Transmittance Matrix Name",
                    "field_type": "a"
                },
                "solar_optical_complex_back_reflectance_matrix_name": {
                    "field_name": "Solar Optical Complex Back Reflectance Matrix Name",
                    "field_type": "a"
                },
                "visible_optical_complex_front_transmittance_matrix_name": {
                    "field_name": "Visible Optical Complex Front Transmittance Matrix Name",
                    "field_type": "a"
                },
                "visible_optical_complex_back_transmittance_matrix_name": {
                    "field_name": "Visible Optical Complex Back Transmittance Matrix Name",
                    "field_type": "a"
                },
                "outside_layer_name": {
                    "field_name": "Outside Layer Name",
                    "field_type": "a"
                },
                "outside_layer_directional_front_absoptance_matrix_name": {
                    "field_name": "Outside Layer Directional Front Absoptance Matrix Name",
                    "field_type": "a"
                },
                "outside_layer_directional_back_absoptance_matrix_name": {
                    "field_name": "Outside Layer Directional Back Absoptance Matrix Name",
                    "field_type": "a"
                },
                "gap_1_name": {
                    "field_name": "Gap 1 Name",
                    "field_type": "a"
                },
                "cfs_gap_1_directional_front_absoptance_matrix_name": {
                    "field_name": "CFS Gap 1 Directional Front Absoptance Matrix Name",
                    "field_type": "a"
                },
                "cfs_gap_1_directional_back_absoptance_matrix_name": {
                    "field_name": "CFS Gap 1 Directional Back Absoptance Matrix Name",
                    "field_type": "a"
                },
                "layer_2_name": {
                    "field_name": "Layer 2 Name",
                    "field_type": "a"
                },
                "layer_2_directional_front_absoptance_matrix_name": {
                    "field_name": "Layer 2 Directional Front Absoptance Matrix Name",
                    "field_type": "a"
                },
                "layer_2_directional_back_absoptance_matrix_name": {
                    "field_name": "Layer 2 Directional Back Absoptance Matrix Name",
                    "field_type": "a"
                },
                "gap_2_name": {
                    "field_name": "Gap 2 Name",
                    "field_type": "a"
                },
                "gap_2_directional_front_absoptance_matrix_name": {
                    "field_name": "Gap 2 Directional Front Absoptance Matrix Name",
                    "field_type": "a"
                },
                "gap_2_directional_back_absoptance_matrix_name": {
                    "field_name": "Gap 2 Directional Back Absoptance Matrix Name",
                    "field_type": "a"
                },
                "layer_3_name": {
                    "field_name": "Layer 3 Name",
                    "field_type": "a"
                },
                "layer_3_directional_front_absoptance_matrix_name": {
                    "field_name": "Layer 3 Directional Front Absoptance Matrix Name",
                    "field_type": "a"
                },
                "layer_3_directional_back_absoptance_matrix_name": {
                    "field_name": "Layer 3 Directional Back Absoptance Matrix Name",
                    "field_type": "a"
                },
                "gap_3_name": {
                    "field_name": "Gap 3 Name",
                    "field_type": "a"
                },
                "gap_3_directional_front_absoptance_matrix_name": {
                    "field_name": "Gap 3 Directional Front Absoptance Matrix Name",
                    "field_type": "a"
                },
                "gap_3_directional_back_absoptance_matrix_name": {
                    "field_name": "Gap 3 Directional Back Absoptance Matrix Name",
                    "field_type": "a"
                },
                "layer_4_name": {
                    "field_name": "Layer 4 Name",
                    "field_type": "a"
                },
                "layer_4_directional_front_absoptance_matrix_name": {
                    "field_name": "Layer 4 Directional Front Absoptance Matrix Name",
                    "field_type": "a"
                },
                "layer_4_directional_back_absoptance_matrix_name": {
                    "field_name": "Layer 4 Directional Back Absoptance Matrix Name",
                    "field_type": "a"
                },
                "gap_4_name": {
                    "field_name": "Gap 4 Name",
                    "field_type": "a"
                },
                "gap_4_directional_front_absoptance_matrix_name": {
                    "field_name": "Gap 4 Directional Front Absoptance Matrix Name",
                    "field_type": "a"
                },
                "gap_4_directional_back_absoptance_matrix_name": {
                    "field_name": "Gap 4 Directional Back Absoptance Matrix Name",
                    "field_type": "a"
                },
                "layer_5_name": {
                    "field_name": "Layer 5 Name",
                    "field_type": "a"
                },
                "layer_5_directional_front_absoptance_matrix_name": {
                    "field_name": "Layer 5 Directional Front Absoptance Matrix Name",
                    "field_type": "a"
                },
                "layer_5_directional_back_absoptance_matrix_name": {
                    "field_name": "Layer 5 Directional Back Absoptance Matrix Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "basis_type",
                "basis_symmetry_type",
                "window_thermal_model",
                "basis_matrix_name",
                "solar_optical_complex_front_transmittance_matrix_name",
                "solar_optical_complex_back_reflectance_matrix_name",
                "visible_optical_complex_front_transmittance_matrix_name",
                "visible_optical_complex_back_transmittance_matrix_name",
                "outside_layer_name",
                "outside_layer_directional_front_absoptance_matrix_name",
                "outside_layer_directional_back_absoptance_matrix_name",
                "gap_1_name",
                "cfs_gap_1_directional_front_absoptance_matrix_name",
                "cfs_gap_1_directional_back_absoptance_matrix_name",
                "layer_2_name",
                "layer_2_directional_front_absoptance_matrix_name",
                "layer_2_directional_back_absoptance_matrix_name",
                "gap_2_name",
                "gap_2_directional_front_absoptance_matrix_name",
                "gap_2_directional_back_absoptance_matrix_name",
                "layer_3_name",
                "layer_3_directional_front_absoptance_matrix_name",
                "layer_3_directional_back_absoptance_matrix_name",
                "gap_3_name",
                "gap_3_directional_front_absoptance_matrix_name",
                "gap_3_directional_back_absoptance_matrix_name",
                "layer_4_name",
                "layer_4_directional_front_absoptance_matrix_name",
                "layer_4_directional_back_absoptance_matrix_name",
                "gap_4_name",
                "gap_4_directional_front_absoptance_matrix_name",
                "gap_4_directional_back_absoptance_matrix_name",
                "layer_5_name",
                "layer_5_directional_front_absoptance_matrix_name",
                "layer_5_directional_back_absoptance_matrix_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "basis_type",
                    "basis_symmetry_type",
                    "window_thermal_model",
                    "basis_matrix_name",
                    "solar_optical_complex_front_transmittance_matrix_name",
                    "solar_optical_complex_back_reflectance_matrix_name",
                    "visible_optical_complex_front_transmittance_matrix_name",
                    "visible_optical_complex_back_transmittance_matrix_name",
                    "outside_layer_name",
                    "outside_layer_directional_front_absoptance_matrix_name",
                    "outside_layer_directional_back_absoptance_matrix_name",
                    "gap_1_name",
                    "cfs_gap_1_directional_front_absoptance_matrix_name",
                    "cfs_gap_1_directional_back_absoptance_matrix_name",
                    "layer_2_name",
                    "layer_2_directional_front_absoptance_matrix_name",
                    "layer_2_directional_back_absoptance_matrix_name",
                    "gap_2_name",
                    "gap_2_directional_front_absoptance_matrix_name",
                    "gap_2_directional_back_absoptance_matrix_name",
                    "layer_3_name",
                    "layer_3_directional_front_absoptance_matrix_name",
                    "layer_3_directional_back_absoptance_matrix_name",
                    "gap_3_name",
                    "gap_3_directional_front_absoptance_matrix_name",
                    "gap_3_directional_back_absoptance_matrix_name",
                    "layer_4_name",
                    "layer_4_directional_front_absoptance_matrix_name",
                    "layer_4_directional_back_absoptance_matrix_name",
                    "gap_4_name",
                    "gap_4_directional_front_absoptance_matrix_name",
                    "gap_4_directional_back_absoptance_matrix_name",
                    "layer_5_name",
                    "layer_5_directional_front_absoptance_matrix_name",
                    "layer_5_directional_back_absoptance_matrix_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "Describes one state for a complex glazing system These input objects are typically generated by using WINDOW software and export to IDF syntax"
    }
}
```
