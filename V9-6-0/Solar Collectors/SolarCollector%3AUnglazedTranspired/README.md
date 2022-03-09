```
{
    "SolarCollector:UnglazedTranspired": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "boundary_conditions_model_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "OSCMNames"
                        ],
                        "note": "Enter the name of a SurfaceProperty:OtherSideConditionsModel object"
                    },
                    "availability_schedule_name": {
                        "type": "string",
                        "note": "Availability schedule name for this collector. Schedule value > 0 means it is available. If this field is blank, the collector is always available.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "inlet_node_name": {
                        "type": "string",
                        "note": "required field if no SolarCollector:UnglazedTranspired:Multisystem"
                    },
                    "outlet_node_name": {
                        "type": "string",
                        "note": "required field if no SolarCollector:UnglazedTranspired:Multisystem"
                    },
                    "setpoint_node_name": {
                        "type": "string",
                        "note": "This node is where the mixed air setpoint is determined. required field if no SolarCollector:UnglazedTranspired:Multisystem"
                    },
                    "zone_node_name": {
                        "type": "string",
                        "note": "This node is used to identify the affected zone required field if no SolarCollector:UnglazedTranspired:Multisystem"
                    },
                    "free_heating_setpoint_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "diameter_of_perforations_in_collector": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "m"
                    },
                    "distance_between_perforations_in_collector": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "m"
                    },
                    "thermal_emissivity_of_collector_surface": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "units": "dimensionless"
                    },
                    "solar_absorbtivity_of_collector_surface": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "units": "dimensionless"
                    },
                    "effective_overall_height_of_collector": {
                        "type": "number",
                        "exclusiveMinimum": 0.0
                    },
                    "effective_gap_thickness_of_plenum_behind_collector": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "m",
                        "note": "if corrugated, use average depth"
                    },
                    "effective_cross_section_area_of_plenum_behind_collector": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "m2",
                        "note": "if corrugated, use average depth"
                    },
                    "hole_layout_pattern_for_pitch": {
                        "type": "string",
                        "enum": [
                            "",
                            "Square",
                            "Triangle"
                        ],
                        "default": "Square"
                    },
                    "heat_exchange_effectiveness_correlation": {
                        "type": "string",
                        "enum": [
                            "",
                            "Kutscher1994",
                            "VanDeckerHollandsBrunger2001"
                        ],
                        "default": "Kutscher1994"
                    },
                    "ratio_of_actual_collector_surface_area_to_projected_surface_area": {
                        "type": "number",
                        "note": "This parameter is used to help account for corrugations in the collector",
                        "default": 1.0,
                        "minimum": 1.0,
                        "maximum": 2.0,
                        "units": "dimensionless"
                    },
                    "roughness_of_collector": {
                        "type": "string",
                        "enum": [
                            "MediumRough",
                            "MediumSmooth",
                            "Rough",
                            "Smooth",
                            "VeryRough",
                            "VerySmooth"
                        ]
                    },
                    "collector_thickness": {
                        "type": "number",
                        "note": "Collector thickness is not required for Kutscher correlation Collector thickness is required for Van Decker et al. correlation",
                        "minimum": 0.0005,
                        "maximum": 0.007,
                        "units": "m"
                    },
                    "effectiveness_for_perforations_with_respect_to_wind": {
                        "type": "number",
                        "note": "Cv",
                        "units": "dimensionless",
                        "default": 0.25,
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.5
                    },
                    "discharge_coefficient_for_openings_with_respect_to_buoyancy_driven_flow": {
                        "type": "number",
                        "note": "Cd",
                        "units": "dimensionless",
                        "default": 0.65,
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.5
                    },
                    "surfaces": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "surface_name": {
                                    "type": "string",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "AllShadingAndHTSurfNames"
                                    ]
                                }
                            },
                            "type": "object",
                            "required": [
                                "surface_name"
                            ]
                        }
                    }
                },
                "required": [
                    "boundary_conditions_model_name",
                    "diameter_of_perforations_in_collector",
                    "distance_between_perforations_in_collector",
                    "thermal_emissivity_of_collector_surface",
                    "solar_absorbtivity_of_collector_surface",
                    "effective_overall_height_of_collector",
                    "effective_gap_thickness_of_plenum_behind_collector",
                    "effective_cross_section_area_of_plenum_behind_collector",
                    "roughness_of_collector"
                ]
            }
        },
        "group": "Solar Collectors",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "UTSCNames",
                "validOASysEquipmentNames"
            ],
            "reference-class-name": [
                "validOASysEquipmentTypes"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "boundary_conditions_model_name": {
                    "field_name": "Boundary Conditions Model Name",
                    "field_type": "a"
                },
                "availability_schedule_name": {
                    "field_name": "Availability Schedule Name",
                    "field_type": "a"
                },
                "inlet_node_name": {
                    "field_name": "Inlet Node Name",
                    "field_type": "a"
                },
                "outlet_node_name": {
                    "field_name": "Outlet Node Name",
                    "field_type": "a"
                },
                "setpoint_node_name": {
                    "field_name": "Setpoint Node Name",
                    "field_type": "a"
                },
                "zone_node_name": {
                    "field_name": "Zone Node Name",
                    "field_type": "a"
                },
                "free_heating_setpoint_schedule_name": {
                    "field_name": "Free Heating Setpoint Schedule Name",
                    "field_type": "a"
                },
                "diameter_of_perforations_in_collector": {
                    "field_name": "Diameter of Perforations in Collector",
                    "field_type": "n"
                },
                "distance_between_perforations_in_collector": {
                    "field_name": "Distance Between Perforations in Collector",
                    "field_type": "n"
                },
                "thermal_emissivity_of_collector_surface": {
                    "field_name": "Thermal Emissivity of Collector Surface",
                    "field_type": "n"
                },
                "solar_absorbtivity_of_collector_surface": {
                    "field_name": "Solar Absorbtivity of Collector Surface",
                    "field_type": "n"
                },
                "effective_overall_height_of_collector": {
                    "field_name": "Effective Overall Height of Collector",
                    "field_type": "n"
                },
                "effective_gap_thickness_of_plenum_behind_collector": {
                    "field_name": "Effective Gap Thickness of Plenum Behind Collector",
                    "field_type": "n"
                },
                "effective_cross_section_area_of_plenum_behind_collector": {
                    "field_name": "Effective Cross Section Area of Plenum Behind Collector",
                    "field_type": "n"
                },
                "hole_layout_pattern_for_pitch": {
                    "field_name": "Hole Layout Pattern for Pitch",
                    "field_type": "a"
                },
                "heat_exchange_effectiveness_correlation": {
                    "field_name": "Heat Exchange Effectiveness Correlation",
                    "field_type": "a"
                },
                "ratio_of_actual_collector_surface_area_to_projected_surface_area": {
                    "field_name": "Ratio of Actual Collector Surface Area to Projected Surface Area",
                    "field_type": "n"
                },
                "roughness_of_collector": {
                    "field_name": "Roughness of Collector",
                    "field_type": "a"
                },
                "collector_thickness": {
                    "field_name": "Collector Thickness",
                    "field_type": "n"
                },
                "effectiveness_for_perforations_with_respect_to_wind": {
                    "field_name": "Effectiveness for Perforations with Respect to Wind",
                    "field_type": "n"
                },
                "discharge_coefficient_for_openings_with_respect_to_buoyancy_driven_flow": {
                    "field_name": "Discharge Coefficient for Openings with Respect to Buoyancy Driven Flow",
                    "field_type": "n"
                },
                "surface_name": {
                    "field_name": "Surface Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "boundary_conditions_model_name",
                "availability_schedule_name",
                "inlet_node_name",
                "outlet_node_name",
                "setpoint_node_name",
                "zone_node_name",
                "free_heating_setpoint_schedule_name",
                "diameter_of_perforations_in_collector",
                "distance_between_perforations_in_collector",
                "thermal_emissivity_of_collector_surface",
                "solar_absorbtivity_of_collector_surface",
                "effective_overall_height_of_collector",
                "effective_gap_thickness_of_plenum_behind_collector",
                "effective_cross_section_area_of_plenum_behind_collector",
                "hole_layout_pattern_for_pitch",
                "heat_exchange_effectiveness_correlation",
                "ratio_of_actual_collector_surface_area_to_projected_surface_area",
                "roughness_of_collector",
                "collector_thickness",
                "effectiveness_for_perforations_with_respect_to_wind",
                "discharge_coefficient_for_openings_with_respect_to_buoyancy_driven_flow"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "boundary_conditions_model_name",
                    "availability_schedule_name",
                    "inlet_node_name",
                    "outlet_node_name",
                    "setpoint_node_name",
                    "zone_node_name",
                    "free_heating_setpoint_schedule_name",
                    "hole_layout_pattern_for_pitch",
                    "heat_exchange_effectiveness_correlation",
                    "roughness_of_collector"
                ],
                "extensions": [
                    "surface_name"
                ]
            },
            "numerics": {
                "fields": [
                    "diameter_of_perforations_in_collector",
                    "distance_between_perforations_in_collector",
                    "thermal_emissivity_of_collector_surface",
                    "solar_absorbtivity_of_collector_surface",
                    "effective_overall_height_of_collector",
                    "effective_gap_thickness_of_plenum_behind_collector",
                    "effective_cross_section_area_of_plenum_behind_collector",
                    "ratio_of_actual_collector_surface_area_to_projected_surface_area",
                    "collector_thickness",
                    "effectiveness_for_perforations_with_respect_to_wind",
                    "discharge_coefficient_for_openings_with_respect_to_buoyancy_driven_flow"
                ]
            },
            "extensibles": [
                "surface_name"
            ],
            "extension": "surfaces"
        },
        "type": "object",
        "memo": "Unglazed transpired solar collector (UTSC) used to condition outdoor air. This type of collector is generally used to heat air drawn through perforated absorbers and also recover heat conducted out through the underlying surface. This object represents a single collector attached to one or more building or shading surfaces and to one or more outdoor air systems.",
        "min_fields": 23.0,
        "extensible_size": 1.0
    }
}
```
