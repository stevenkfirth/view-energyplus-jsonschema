```
{
    "ElectricLoadCenter:Transformer": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "availability_schedule_name": {
                        "type": "string",
                        "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "transformer_usage": {
                        "type": "string",
                        "enum": [
                            "",
                            "LoadCenterPowerConditioning",
                            "PowerInFromGrid",
                            "PowerOutToGrid"
                        ],
                        "default": "PowerInFromGrid",
                        "note": "A transformer can be used to transfer electric energy from utility grid to building (PowerInFromGrid)or from building on-site generation to the grid (PowerOutToGrid) or within a load center to match generation to the facility service main panel (LoadCenterPowerConditioning)"
                    },
                    "zone_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ],
                        "note": "Enter name of zone to receive transformer losses as heat if blank then transformer losses are dissipated to outdoors"
                    },
                    "radiative_fraction": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "rated_capacity": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "VA",
                        "note": "the unit is VA, instead of kVA as usually shown on transformer nameplates."
                    },
                    "phase": {
                        "default": 3.0,
                        "note": "Must be single or three phase transformer. NOT used in the current model.",
                        "anyOf": [
                            {
                                "type": "number",
                                "enum": [
                                    1,
                                    3
                                ]
                            },
                            {
                                "type": "string",
                                "enum": [
                                    ""
                                ]
                            }
                        ]
                    },
                    "conductor_material": {
                        "type": "string",
                        "enum": [
                            "",
                            "Aluminum",
                            "Copper"
                        ],
                        "default": "Aluminum",
                        "note": "Winding material used by the transformer."
                    },
                    "full_load_temperature_rise": {
                        "type": "number",
                        "units": "C",
                        "minimum": 50.0,
                        "maximum": 180.0,
                        "default": 150.0
                    },
                    "fraction_of_eddy_current_losses": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.1
                    },
                    "performance_input_method": {
                        "type": "string",
                        "enum": [
                            "",
                            "NominalEfficiency",
                            "RatedLosses"
                        ],
                        "default": "RatedLosses",
                        "note": "User can define transformer performance by specifying load and no load losses at rated conditions or nameplate efficiency and maximum efficiency"
                    },
                    "rated_no_load_loss": {
                        "type": "number",
                        "units": "W",
                        "exclusiveMinimum": 0.0,
                        "note": "Only required when RatedLosses is the performance input method"
                    },
                    "rated_load_loss": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0,
                        "note": "Only required when RatedLosses is the performance input method"
                    },
                    "nameplate_efficiency": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.98,
                        "note": "Only required when NominalEfficiency is the performance input method"
                    },
                    "per_unit_load_for_nameplate_efficiency": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.35,
                        "note": "Percentage of the rated capacity at which the nameplate efficiency is defined Only required when NominalEfficiency is the performance input method"
                    },
                    "reference_temperature_for_nameplate_efficiency": {
                        "type": "number",
                        "units": "C",
                        "minimum": 20.0,
                        "maximum": 150.0,
                        "default": 75.0,
                        "note": "Conductor operating temperature at which the nameplate efficiency is defined Only required when NominalEfficiency is the performance input method"
                    },
                    "per_unit_load_for_maximum_efficiency": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0,
                        "note": "Percentage of the rate capacity at which the maximum efficiency is obtained Only required when NominalEfficiency is the performance input method"
                    },
                    "consider_transformer_loss_for_utility_cost": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes",
                        "note": "Only required when the transformer is used for power in from the utility grid"
                    },
                    "meters": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "meter_name": {
                                    "type": "string",
                                    "data_type": "external_list",
                                    "external_list": [
                                        "autoRDDmeter"
                                    ],
                                    "note": "Must be an electric meter (with electricity as the resource type) Only required when transformer is used for power in from the utility grid"
                                }
                            },
                            "type": "object"
                        }
                    }
                }
            }
        },
        "group": "Electric Load Center-Generator Specifications",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "TransformerNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "availability_schedule_name": {
                    "field_name": "Availability Schedule Name",
                    "field_type": "a"
                },
                "transformer_usage": {
                    "field_name": "Transformer Usage",
                    "field_type": "a"
                },
                "zone_name": {
                    "field_name": "Zone Name",
                    "field_type": "a"
                },
                "radiative_fraction": {
                    "field_name": "Radiative Fraction",
                    "field_type": "n"
                },
                "rated_capacity": {
                    "field_name": "Rated Capacity",
                    "field_type": "n"
                },
                "phase": {
                    "field_name": "Phase",
                    "field_type": "n"
                },
                "conductor_material": {
                    "field_name": "Conductor Material",
                    "field_type": "a"
                },
                "full_load_temperature_rise": {
                    "field_name": "Full Load Temperature Rise",
                    "field_type": "n"
                },
                "fraction_of_eddy_current_losses": {
                    "field_name": "Fraction of Eddy Current Losses",
                    "field_type": "n"
                },
                "performance_input_method": {
                    "field_name": "Performance Input Method",
                    "field_type": "a"
                },
                "rated_no_load_loss": {
                    "field_name": "Rated No Load Loss",
                    "field_type": "n"
                },
                "rated_load_loss": {
                    "field_name": "Rated Load Loss",
                    "field_type": "n"
                },
                "nameplate_efficiency": {
                    "field_name": "Nameplate Efficiency",
                    "field_type": "n"
                },
                "per_unit_load_for_nameplate_efficiency": {
                    "field_name": "Per Unit Load for Nameplate Efficiency",
                    "field_type": "n"
                },
                "reference_temperature_for_nameplate_efficiency": {
                    "field_name": "Reference Temperature for Nameplate Efficiency",
                    "field_type": "n"
                },
                "per_unit_load_for_maximum_efficiency": {
                    "field_name": "Per Unit Load for Maximum Efficiency",
                    "field_type": "n"
                },
                "consider_transformer_loss_for_utility_cost": {
                    "field_name": "Consider Transformer Loss for Utility Cost",
                    "field_type": "a"
                },
                "meter_name": {
                    "field_name": "Meter Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "transformer_usage",
                "zone_name",
                "radiative_fraction",
                "rated_capacity",
                "phase",
                "conductor_material",
                "full_load_temperature_rise",
                "fraction_of_eddy_current_losses",
                "performance_input_method",
                "rated_no_load_loss",
                "rated_load_loss",
                "nameplate_efficiency",
                "per_unit_load_for_nameplate_efficiency",
                "reference_temperature_for_nameplate_efficiency",
                "per_unit_load_for_maximum_efficiency",
                "consider_transformer_loss_for_utility_cost"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "transformer_usage",
                    "zone_name",
                    "conductor_material",
                    "performance_input_method",
                    "consider_transformer_loss_for_utility_cost"
                ],
                "extensions": [
                    "meter_name"
                ]
            },
            "numerics": {
                "fields": [
                    "radiative_fraction",
                    "rated_capacity",
                    "phase",
                    "full_load_temperature_rise",
                    "fraction_of_eddy_current_losses",
                    "rated_no_load_loss",
                    "rated_load_loss",
                    "nameplate_efficiency",
                    "per_unit_load_for_nameplate_efficiency",
                    "reference_temperature_for_nameplate_efficiency",
                    "per_unit_load_for_maximum_efficiency"
                ]
            },
            "extensibles": [
                "meter_name"
            ],
            "extension": "meters"
        },
        "type": "object",
        "memo": "a list of meters that can be reported are available after a run on the meter dictionary file (.mdd) if the Output:VariableDictionary has been requested.",
        "extensible_size": 1.0
    }
}
```
