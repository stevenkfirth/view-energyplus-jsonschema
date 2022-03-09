```
{
    "RoomAirSettings:UnderFloorAirDistributionInterior": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "zone_name": {
                        "type": "string",
                        "note": "Name of Zone with underfloor air distribution",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "number_of_diffusers": {
                        "note": "Total number of diffusers in this zone",
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
                        "note": "Height at which air temperature is calculated for comfort purposes",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "default": 1.1
                    },
                    "temperature_difference_threshold_for_reporting": {
                        "type": "number",
                        "note": "Minimum temperature difference between predicted upper and lower layer temperatures above which UFAD auxiliary outputs are calculated. These outputs are 'UF Transition Height' and 'UF Average Temp Gradient'. They are set to zero values when the temperature difference is less than the threshold and the output 'UF Zone Is Mixed' is set to 1",
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
                        "note": "user-specified height above floor of boundary between occupied and upper subzones",
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
                    "coefficient_a": {
                        "note": "Coefficient A in Formula Kc = A*Gamma**B + C + D*Gamma + E*Gamma**2 Kc is the fraction of the total zone load attributable to the lower subzone",
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
                    "coefficient_b": {
                        "note": "Coefficient B in Formula Kc = A*Gamma**B + C + D*Gamma + E*Gamma**2 Kc is the fraction of the total zone load attributable to the lower subzone",
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
                    "coefficient_c": {
                        "note": "Coefficient C in Formula Kc = A*Gamma**B + C + D*Gamma + E*Gamma**2 Kc is the fraction of the total zone load attributable to the lower subzone",
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
                    "coefficient_d": {
                        "note": "Coefficient D in Formula Kc = A*Gamma**B + C + D*Gamma + E*Gamma**2 Kc is the fraction of the total zone load attributable to the lower subzone",
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
                    "coefficient_e": {
                        "note": "Coefficient E in Formula Kc = A*Gamma**B + C + D*Gamma + E*Gamma**2 Kc is the fraction of the total zone load attributable to the lower subzone",
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
                "number_of_diffusers": {
                    "field_name": "Number of Diffusers",
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
                "coefficient_a": {
                    "field_name": "Coefficient A",
                    "field_type": "n"
                },
                "coefficient_b": {
                    "field_name": "Coefficient B",
                    "field_type": "n"
                },
                "coefficient_c": {
                    "field_name": "Coefficient C",
                    "field_type": "n"
                },
                "coefficient_d": {
                    "field_name": "Coefficient D",
                    "field_type": "n"
                },
                "coefficient_e": {
                    "field_name": "Coefficient E",
                    "field_type": "n"
                }
            },
            "fields": [
                "zone_name",
                "number_of_diffusers",
                "power_per_plume",
                "design_effective_area_of_diffuser",
                "diffuser_slot_angle_from_vertical",
                "thermostat_height",
                "comfort_height",
                "temperature_difference_threshold_for_reporting",
                "floor_diffuser_type",
                "transition_height",
                "coefficient_a",
                "coefficient_b",
                "coefficient_c",
                "coefficient_d",
                "coefficient_e"
            ],
            "alphas": {
                "fields": [
                    "zone_name",
                    "floor_diffuser_type"
                ]
            },
            "numerics": {
                "fields": [
                    "number_of_diffusers",
                    "power_per_plume",
                    "design_effective_area_of_diffuser",
                    "diffuser_slot_angle_from_vertical",
                    "thermostat_height",
                    "comfort_height",
                    "temperature_difference_threshold_for_reporting",
                    "transition_height",
                    "coefficient_a",
                    "coefficient_b",
                    "coefficient_c",
                    "coefficient_d",
                    "coefficient_e"
                ]
            }
        },
        "type": "object",
        "memo": "This Room Air Model is applicable to interior spaces that are served by an underfloor air distribution system. The dominant sources of heat gain should be from people, equipment, and other localized sources located in the occupied part of the room. The model should be used with caution in zones which have large heat gains or losses through exterior walls or windows or which have considerable direct solar gain. Used with RoomAirModelType = UnderFloorAirDistributionInterior.",
        "min_fields": 15.0
    }
}
```
