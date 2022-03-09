```
{
    "RoomAirSettings:UnderFloorAirDistributionExterior": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "zone_name": {
                        "type": "string",
                        "note": "Name of Zone being described. Any existing zone name",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "number_of_diffusers_per_zone": {
                        "default": "Autocalculate",
                        "anyOf": [
                            {
                                "type": "number",
                                "exclusiveMinimum": 0.0
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
                    "power_per_plume": {
                        "units": "W",
                        "default": "Autocalculate",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.0
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
                    "design_effective_area_of_diffuser": {
                        "units": "m2",
                        "default": "Autocalculate",
                        "anyOf": [
                            {
                                "type": "number",
                                "exclusiveMinimum": 0.0
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
                    "diffuser_slot_angle_from_vertical": {
                        "units": "deg",
                        "default": "Autocalculate",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.0,
                                "maximum": 90.0
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
                    "thermostat_height": {
                        "type": "number",
                        "note": "Height of thermostat/temperature control sensor above floor",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "default": 1.2
                    },
                    "comfort_height": {
                        "type": "number",
                        "note": "Height at which Air temperature is calculated for comfort purposes",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "default": 1.1
                    },
                    "temperature_difference_threshold_for_reporting": {
                        "type": "number",
                        "note": "Minimum temperature difference between upper and lower layer temperatures above which UFAD auxiliary outputs are calculated. These outputs are 'UF Transition Height' and 'UF Average Temp Gradient'. They are set to zero values when the temperature difference is less than the threshold and the output 'UF Zone Is Mixed' is set to 1",
                        "units": "deltaC",
                        "minimum": 0.0,
                        "default": 0.4
                    },
                    "floor_diffuser_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Custom",
                            "HorizontalSwirl",
                            "LinearBarGrille",
                            "Swirl",
                            "VariableArea"
                        ],
                        "default": "Swirl"
                    },
                    "transition_height": {
                        "note": "User-specified height above floor of boundary between occupied and upper subzones",
                        "units": "m",
                        "default": 1.7,
                        "anyOf": [
                            {
                                "type": "number",
                                "exclusiveMinimum": 0.0
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
                    "coefficient_a_in_formula_kc_a_gamma_b_c_d_gamma_e_gamma_2": {
                        "note": "Kc is the fraction of the total zone load attributable to the lower subzone",
                        "default": "Autocalculate",
                        "anyOf": [
                            {
                                "type": "number"
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
                    "coefficient_b_in_formula_kc_a_gamma_b_c_d_gamma_e_gamma_2": {
                        "note": "Kc is the fraction of the total zone load attributable to the lower subzone",
                        "default": "Autocalculate",
                        "anyOf": [
                            {
                                "type": "number"
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
                    "coefficient_c_in_formula_kc_a_gamma_b_c_d_gamma_e_gamma_2": {
                        "note": "Kc is the fraction of the total zone load attributable to the lower subzone",
                        "default": "Autocalculate",
                        "anyOf": [
                            {
                                "type": "number"
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
                    "coefficient_d_in_formula_kc_a_gamma_b_c_d_gamma_e_gamma_2": {
                        "note": "Kc is the fraction of the total zone load attributable to the lower subzone",
                        "default": "Autocalculate",
                        "anyOf": [
                            {
                                "type": "number"
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
                    "coefficient_e_in_formula_kc_a_gamma_b_c_d_gamma_e_gamma_2": {
                        "note": "Kc is the fraction of the total zone load attributable to the lower subzone",
                        "default": "Autocalculate",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "",
                                    "Autocalculate"
                                ]
                            }
                        ]
                    }
                },
                "required": [
                    "zone_name"
                ]
            }
        },
        "group": "Room Air Models",
        "legacy_idd": {
            "field_info": {
                "zone_name": {
                    "field_name": "Zone Name",
                    "field_type": "a"
                },
                "number_of_diffusers_per_zone": {
                    "field_name": "Number of Diffusers per Zone",
                    "field_type": "n"
                },
                "power_per_plume": {
                    "field_name": "Power per Plume",
                    "field_type": "n"
                },
                "design_effective_area_of_diffuser": {
                    "field_name": "Design Effective Area of Diffuser",
                    "field_type": "n"
                },
                "diffuser_slot_angle_from_vertical": {
                    "field_name": "Diffuser Slot Angle from Vertical",
                    "field_type": "n"
                },
                "thermostat_height": {
                    "field_name": "Thermostat Height",
                    "field_type": "n"
                },
                "comfort_height": {
                    "field_name": "Comfort Height",
                    "field_type": "n"
                },
                "temperature_difference_threshold_for_reporting": {
                    "field_name": "Temperature Difference Threshold for Reporting",
                    "field_type": "n"
                },
                "floor_diffuser_type": {
                    "field_name": "Floor Diffuser Type",
                    "field_type": "a"
                },
                "transition_height": {
                    "field_name": "Transition Height",
                    "field_type": "n"
                },
                "coefficient_a_in_formula_kc_a_gamma_b_c_d_gamma_e_gamma_2": {
                    "field_name": "Coefficient A in formula Kc = A*Gamma**B + C + D*Gamma + E*Gamma**2",
                    "field_type": "n"
                },
                "coefficient_b_in_formula_kc_a_gamma_b_c_d_gamma_e_gamma_2": {
                    "field_name": "Coefficient B in formula Kc = A*Gamma**B + C + D*Gamma + E*Gamma**2",
                    "field_type": "n"
                },
                "coefficient_c_in_formula_kc_a_gamma_b_c_d_gamma_e_gamma_2": {
                    "field_name": "Coefficient C in formula Kc = A*Gamma**B + C + D*Gamma + E*Gamma**2",
                    "field_type": "n"
                },
                "coefficient_d_in_formula_kc_a_gamma_b_c_d_gamma_e_gamma_2": {
                    "field_name": "Coefficient D in formula Kc = A*Gamma**B + C + D*Gamma + E*Gamma**2",
                    "field_type": "n"
                },
                "coefficient_e_in_formula_kc_a_gamma_b_c_d_gamma_e_gamma_2": {
                    "field_name": "Coefficient E in formula Kc = A*Gamma**B + C + D*Gamma + E*Gamma**2",
                    "field_type": "n"
                }
            },
            "fields": [
                "zone_name",
                "number_of_diffusers_per_zone",
                "power_per_plume",
                "design_effective_area_of_diffuser",
                "diffuser_slot_angle_from_vertical",
                "thermostat_height",
                "comfort_height",
                "temperature_difference_threshold_for_reporting",
                "floor_diffuser_type",
                "transition_height",
                "coefficient_a_in_formula_kc_a_gamma_b_c_d_gamma_e_gamma_2",
                "coefficient_b_in_formula_kc_a_gamma_b_c_d_gamma_e_gamma_2",
                "coefficient_c_in_formula_kc_a_gamma_b_c_d_gamma_e_gamma_2",
                "coefficient_d_in_formula_kc_a_gamma_b_c_d_gamma_e_gamma_2",
                "coefficient_e_in_formula_kc_a_gamma_b_c_d_gamma_e_gamma_2"
            ],
            "alphas": {
                "fields": [
                    "zone_name",
                    "floor_diffuser_type"
                ]
            },
            "numerics": {
                "fields": [
                    "number_of_diffusers_per_zone",
                    "power_per_plume",
                    "design_effective_area_of_diffuser",
                    "diffuser_slot_angle_from_vertical",
                    "thermostat_height",
                    "comfort_height",
                    "temperature_difference_threshold_for_reporting",
                    "transition_height",
                    "coefficient_a_in_formula_kc_a_gamma_b_c_d_gamma_e_gamma_2",
                    "coefficient_b_in_formula_kc_a_gamma_b_c_d_gamma_e_gamma_2",
                    "coefficient_c_in_formula_kc_a_gamma_b_c_d_gamma_e_gamma_2",
                    "coefficient_d_in_formula_kc_a_gamma_b_c_d_gamma_e_gamma_2",
                    "coefficient_e_in_formula_kc_a_gamma_b_c_d_gamma_e_gamma_2"
                ]
            }
        },
        "type": "object",
        "memo": "Applicable to exterior spaces that are served by an underfloor air distribution system. The dominant sources of heat gain should be from people, equipment, and other localized sources located in the occupied part of the room, as well as convective gain coming from a warm window. Used with RoomAirModelType = CrossVentilation.",
        "min_fields": 15.0
    }
}
```
