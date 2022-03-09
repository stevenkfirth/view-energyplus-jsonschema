```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "zone_or_space_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "SpaceNames",
                        "ZoneNames"
                    ]
                },
                "daylighting_method": {
                    "type": "string",
                    "enum": [
                        "",
                        "DElight",
                        "SplitFlux"
                    ],
                    "default": "SplitFlux"
                },
                "availability_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "lighting_control_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "Continuous",
                        "ContinuousOff",
                        "Stepped"
                    ],
                    "default": "Continuous"
                },
                "minimum_input_power_fraction_for_continuous_or_continuousoff_dimming_control": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 0.6,
                    "default": 0.3
                },
                "minimum_light_output_fraction_for_continuous_or_continuousoff_dimming_control": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 0.6,
                    "default": 0.2
                },
                "number_of_stepped_control_steps": {
                    "type": "number",
                    "note": "The number of steps, excluding off, in a stepped lighting control system. If Lighting Control Type is Stepped, this field must be greater than zero. The steps are assumed to be equally spaced.",
                    "minimum": 1.0,
                    "default": 1.0
                },
                "probability_lighting_will_be_reset_when_needed_in_manual_stepped_control": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 1.0
                },
                "glare_calculation_daylighting_reference_point_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "DaylightReferencePointNames"
                    ]
                },
                "glare_calculation_azimuth_angle_of_view_direction_clockwise_from_zone_y_axis": {
                    "type": "number",
                    "units": "deg",
                    "minimum": 0.0,
                    "maximum": 360.0,
                    "default": 0.0
                },
                "maximum_allowable_discomfort_glare_index": {
                    "type": "number",
                    "minimum": 1.0,
                    "note": "The default is for general office work",
                    "default": 22.0
                },
                "delight_gridding_resolution": {
                    "type": "number",
                    "units": "m2",
                    "note": "Maximum surface area for nodes in gridding all surfaces in the DElight zone. All reflective and transmitting surfaces will be subdivided into approximately square nodes that do not exceed this maximum. Higher resolution subdivisions require greater calculation times, but generally produce more accurate results.",
                    "exclusiveMinimum": 0.0
                },
                "control_data": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "daylighting_reference_point_name": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "DaylightReferencePointNames"
                                ]
                            },
                            "fraction_of_lights_controlled_by_reference_point": {
                                "type": "number",
                                "minimum": 0.0,
                                "maximum": 1.0,
                                "default": 1.0
                            },
                            "illuminance_setpoint_at_reference_point": {
                                "type": "number",
                                "units": "lux",
                                "minimum": 0.0,
                                "default": 500.0
                            }
                        },
                        "type": "object",
                        "required": [
                            "daylighting_reference_point_name"
                        ]
                    }
                }
            },
            "required": [
                "zone_or_space_name"
            ]
        }
    },
    "group": "Daylighting",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "DaylightingControlNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "zone_or_space_name": {
                "field_name": "Zone or Space Name",
                "field_type": "a"
            },
            "daylighting_method": {
                "field_name": "Daylighting Method",
                "field_type": "a"
            },
            "availability_schedule_name": {
                "field_name": "Availability Schedule Name",
                "field_type": "a"
            },
            "lighting_control_type": {
                "field_name": "Lighting Control Type",
                "field_type": "a"
            },
            "minimum_input_power_fraction_for_continuous_or_continuousoff_dimming_control": {
                "field_name": "Minimum Input Power Fraction for Continuous or ContinuousOff Dimming Control",
                "field_type": "n"
            },
            "minimum_light_output_fraction_for_continuous_or_continuousoff_dimming_control": {
                "field_name": "Minimum Light Output Fraction for Continuous or ContinuousOff Dimming Control",
                "field_type": "n"
            },
            "number_of_stepped_control_steps": {
                "field_name": "Number of Stepped Control Steps",
                "field_type": "n"
            },
            "probability_lighting_will_be_reset_when_needed_in_manual_stepped_control": {
                "field_name": "Probability Lighting will be Reset When Needed in Manual Stepped Control",
                "field_type": "n"
            },
            "glare_calculation_daylighting_reference_point_name": {
                "field_name": "Glare Calculation Daylighting Reference Point Name",
                "field_type": "a"
            },
            "glare_calculation_azimuth_angle_of_view_direction_clockwise_from_zone_y_axis": {
                "field_name": "Glare Calculation Azimuth Angle of View Direction Clockwise from Zone y-Axis",
                "field_type": "n"
            },
            "maximum_allowable_discomfort_glare_index": {
                "field_name": "Maximum Allowable Discomfort Glare Index",
                "field_type": "n"
            },
            "delight_gridding_resolution": {
                "field_name": "DElight Gridding Resolution",
                "field_type": "n"
            },
            "daylighting_reference_point_name": {
                "field_name": "Daylighting Reference Point Name",
                "field_type": "a"
            },
            "fraction_of_lights_controlled_by_reference_point": {
                "field_name": "Fraction of Lights Controlled by Reference Point",
                "field_type": "n"
            },
            "illuminance_setpoint_at_reference_point": {
                "field_name": "Illuminance Setpoint at Reference Point",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "zone_or_space_name",
            "daylighting_method",
            "availability_schedule_name",
            "lighting_control_type",
            "minimum_input_power_fraction_for_continuous_or_continuousoff_dimming_control",
            "minimum_light_output_fraction_for_continuous_or_continuousoff_dimming_control",
            "number_of_stepped_control_steps",
            "probability_lighting_will_be_reset_when_needed_in_manual_stepped_control",
            "glare_calculation_daylighting_reference_point_name",
            "glare_calculation_azimuth_angle_of_view_direction_clockwise_from_zone_y_axis",
            "maximum_allowable_discomfort_glare_index",
            "delight_gridding_resolution"
        ],
        "alphas": {
            "fields": [
                "name",
                "zone_or_space_name",
                "daylighting_method",
                "availability_schedule_name",
                "lighting_control_type",
                "glare_calculation_daylighting_reference_point_name"
            ],
            "extensions": [
                "daylighting_reference_point_name"
            ]
        },
        "numerics": {
            "fields": [
                "minimum_input_power_fraction_for_continuous_or_continuousoff_dimming_control",
                "minimum_light_output_fraction_for_continuous_or_continuousoff_dimming_control",
                "number_of_stepped_control_steps",
                "probability_lighting_will_be_reset_when_needed_in_manual_stepped_control",
                "glare_calculation_azimuth_angle_of_view_direction_clockwise_from_zone_y_axis",
                "maximum_allowable_discomfort_glare_index",
                "delight_gridding_resolution"
            ],
            "extensions": [
                "fraction_of_lights_controlled_by_reference_point",
                "illuminance_setpoint_at_reference_point"
            ]
        },
        "extensibles": [
            "daylighting_reference_point_name",
            "fraction_of_lights_controlled_by_reference_point",
            "illuminance_setpoint_at_reference_point"
        ],
        "extension": "control_data"
    },
    "type": "object",
    "memo": "Dimming of overhead electric lighting is determined from each reference point. Glare from daylighting is also calculated.",
    "min_fields": 16.0,
    "extensible_size": 3.0
}
```
