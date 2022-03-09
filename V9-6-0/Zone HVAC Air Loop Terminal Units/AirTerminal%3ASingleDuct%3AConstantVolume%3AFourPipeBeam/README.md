```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "primary_air_availability_schedule_name": {
                    "type": "string",
                    "note": "Primary air is supplied by central air handling unit and must be on for heating or cooling. Schedule value > 0 means the primary air supply is available. If this field is blank, the primary air supply is always available.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "cooling_availability_schedule_name": {
                    "type": "string",
                    "note": "Cooling operation can be controlled separately using this availability schedule. Schedule value > 0 means beam cooling is available. If this field is blank, the beam cooling is always available (as long as primary air is also available).",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "heating_availability_schedule_name": {
                    "type": "string",
                    "note": "Heating operation can be controlled separately using this availability schedule. Schedule value > 0 means beam heating is available. If this field is blank, the beam heating is always available (as long as primary air is also available).",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "primary_air_inlet_node_name": {
                    "type": "string",
                    "note": "Name of the air system node for primary supply air entering the air distribution unit."
                },
                "primary_air_outlet_node_name": {
                    "type": "string",
                    "note": "Name of the air system node for primary supply air leaving the air distribution unit and entering the zone."
                },
                "chilled_water_inlet_node_name": {
                    "type": "string",
                    "note": "Name of the plant system node for chilled water entering the beam. The two chilled water nodes can (only) be omitted to model a two-pipe heating only beam."
                },
                "chilled_water_outlet_node_name": {
                    "type": "string",
                    "note": "Name of the plant system node for chilled water leaving the beam."
                },
                "hot_water_inlet_node_name": {
                    "type": "string",
                    "note": "Name of the plant system node for hot water entering the beam. The two hot water nodes can (only) be omitted to model a two-pipe cooling-only beam."
                },
                "hot_water_outlet_node_name": {
                    "type": "string",
                    "note": "Name of the plant system node for hot water leaving the beam."
                },
                "design_primary_air_volume_flow_rate": {
                    "units": "m3/s",
                    "default": "Autosize",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "",
                                "Autosize"
                            ]
                        }
                    ]
                },
                "design_chilled_water_volume_flow_rate": {
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "default": "Autosize",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "",
                                "Autosize"
                            ]
                        }
                    ]
                },
                "design_hot_water_volume_flow_rate": {
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "default": "Autosize",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "",
                                "Autosize"
                            ]
                        }
                    ]
                },
                "zone_total_beam_length": {
                    "note": "Sum of the length of all the beam units in the zone represented by this terminal unit.",
                    "units": "m",
                    "default": "Autosize",
                    "anyOf": [
                        {
                            "type": "number",
                            "exclusiveMinimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "",
                                "Autosize"
                            ]
                        }
                    ]
                },
                "rated_primary_air_flow_rate_per_beam_length": {
                    "type": "number",
                    "note": "Primary air supply flow rate normalized by beam length.",
                    "units": "m3/s-m",
                    "exclusiveMinimum": 0.0,
                    "default": 0.035
                },
                "beam_rated_cooling_capacity_per_beam_length": {
                    "type": "number",
                    "note": "Sensible cooling capacity per meter of beam length at the rating point.",
                    "units": "W/m",
                    "exclusiveMinimum": 0.0,
                    "default": 600.0
                },
                "beam_rated_cooling_room_air_chilled_water_temperature_difference": {
                    "type": "number",
                    "note": "Difference in temperature between the zone air and the entering chilled water at the rating point.",
                    "units": "deltaC",
                    "exclusiveMinimum": 0.0,
                    "default": 10.0
                },
                "beam_rated_chilled_water_volume_flow_rate_per_beam_length": {
                    "type": "number",
                    "note": "The volume flow rate of chilled water per meter of beam length at the rating point.",
                    "units": "m3/s-m",
                    "ip-units": "gal/min-ft",
                    "exclusiveMinimum": 0.0,
                    "default": 5e-05
                },
                "beam_cooling_capacity_temperature_difference_modification_factor_curve_name": {
                    "type": "string",
                    "note": "Adjusts beam cooling capacity when the temperature difference between entering water and zone air is different than at the rating point. Single independent variable is the ratio of the current temperature difference divided by the rating point temperature difference. This field is required when beam is connected to a chilled water plant.",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "beam_cooling_capacity_air_flow_modification_factor_curve_name": {
                    "type": "string",
                    "note": "Adjusts beam cooling capacity when the primary air supply flow rate is different than at the rating point. The single independent variable is the current normalized air flow rate divided by the normalized air flow rate at the rating point. This field is required when beam is connected to a chilled water plant.",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "beam_cooling_capacity_chilled_water_flow_modification_factor_curve_name": {
                    "type": "string",
                    "note": "Adjusts beam cooling capacity when the normalized chilled water flow rate is different than at the rating point. The single independent variable is the current normalized chilled water flow rate divided by the normalized chilled water flow rate at the rating point. This field is required when beam is connected to a chilled water plant.",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "beam_rated_heating_capacity_per_beam_length": {
                    "type": "number",
                    "note": "Sensible heating capacity per meter of beam length at the rating point.",
                    "units": "W/m",
                    "exclusiveMinimum": 0.0,
                    "default": 1500.0
                },
                "beam_rated_heating_room_air_hot_water_temperature_difference": {
                    "type": "number",
                    "note": "Difference in temperature between the zone air and the entering hot water at the rating point.",
                    "units": "deltaC",
                    "exclusiveMinimum": 0.0,
                    "default": 27.8
                },
                "beam_rated_hot_water_volume_flow_rate_per_beam_length": {
                    "type": "number",
                    "note": "The volume flow rate of hoy water per meter of beam length at the rating point.",
                    "units": "m3/s-m",
                    "ip-units": "gal/min-ft",
                    "exclusiveMinimum": 0.0,
                    "default": 5e-05
                },
                "beam_heating_capacity_temperature_difference_modification_factor_curve_name": {
                    "type": "string",
                    "note": "Adjusts beam heating capacity when the temperature difference between entering water and zone air is different than at the rating point. Single independent variable is the ratio of the current temperature difference divided by the rating point temperature difference. This field is required when beam is connected to a hot water plant.",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "beam_heating_capacity_air_flow_modification_factor_curve_name": {
                    "type": "string",
                    "note": "Adjusts beam heating capacity when the primary air supply flow rate is different than at the rating point. The single independent variable is the current normalized air flow rate divided by the normalized air flow rate at the rating point. This field is required when beam is connected to a hot water plant.",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "beam_heating_capacity_hot_water_flow_modification_factor_curve_name": {
                    "type": "string",
                    "note": "Adjusts beam heating capacity when the normalized hot water flow rate is different than at the rating point. The single independent variable is the current normalized hot water flow rate divided by the normalized hot water flow rate at the rating point. This field is required when beam is connected to a hot water plant.",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                }
            },
            "required": [
                "primary_air_inlet_node_name",
                "primary_air_outlet_node_name"
            ]
        }
    },
    "group": "Zone HVAC Air Loop Terminal Units",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "AirTerminalUnitNames",
            "validBranchEquipmentNames"
        ],
        "reference-class-name": [
            "validBranchEquipmentTypes"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "primary_air_availability_schedule_name": {
                "field_name": "Primary Air Availability Schedule Name",
                "field_type": "a"
            },
            "cooling_availability_schedule_name": {
                "field_name": "Cooling Availability Schedule Name",
                "field_type": "a"
            },
            "heating_availability_schedule_name": {
                "field_name": "Heating Availability Schedule Name",
                "field_type": "a"
            },
            "primary_air_inlet_node_name": {
                "field_name": "Primary Air Inlet Node Name",
                "field_type": "a"
            },
            "primary_air_outlet_node_name": {
                "field_name": "Primary Air Outlet Node Name",
                "field_type": "a"
            },
            "chilled_water_inlet_node_name": {
                "field_name": "Chilled Water Inlet Node Name",
                "field_type": "a"
            },
            "chilled_water_outlet_node_name": {
                "field_name": "Chilled Water Outlet Node Name",
                "field_type": "a"
            },
            "hot_water_inlet_node_name": {
                "field_name": "Hot Water Inlet Node Name",
                "field_type": "a"
            },
            "hot_water_outlet_node_name": {
                "field_name": "Hot Water Outlet Node Name",
                "field_type": "a"
            },
            "design_primary_air_volume_flow_rate": {
                "field_name": "Design Primary Air Volume Flow Rate",
                "field_type": "n"
            },
            "design_chilled_water_volume_flow_rate": {
                "field_name": "Design Chilled Water Volume Flow Rate",
                "field_type": "n"
            },
            "design_hot_water_volume_flow_rate": {
                "field_name": "Design Hot Water Volume Flow Rate",
                "field_type": "n"
            },
            "zone_total_beam_length": {
                "field_name": "Zone Total Beam Length",
                "field_type": "n"
            },
            "rated_primary_air_flow_rate_per_beam_length": {
                "field_name": "Rated Primary Air Flow Rate per Beam Length",
                "field_type": "n"
            },
            "beam_rated_cooling_capacity_per_beam_length": {
                "field_name": "Beam Rated Cooling Capacity per Beam Length",
                "field_type": "n"
            },
            "beam_rated_cooling_room_air_chilled_water_temperature_difference": {
                "field_name": "Beam Rated Cooling Room Air Chilled Water Temperature Difference",
                "field_type": "n"
            },
            "beam_rated_chilled_water_volume_flow_rate_per_beam_length": {
                "field_name": "Beam Rated Chilled Water Volume Flow Rate per Beam Length",
                "field_type": "n"
            },
            "beam_cooling_capacity_temperature_difference_modification_factor_curve_name": {
                "field_name": "Beam Cooling Capacity Temperature Difference Modification Factor Curve Name",
                "field_type": "a"
            },
            "beam_cooling_capacity_air_flow_modification_factor_curve_name": {
                "field_name": "Beam Cooling Capacity Air Flow Modification Factor Curve Name",
                "field_type": "a"
            },
            "beam_cooling_capacity_chilled_water_flow_modification_factor_curve_name": {
                "field_name": "Beam Cooling Capacity Chilled Water Flow Modification Factor Curve Name",
                "field_type": "a"
            },
            "beam_rated_heating_capacity_per_beam_length": {
                "field_name": "Beam Rated Heating Capacity per Beam Length",
                "field_type": "n"
            },
            "beam_rated_heating_room_air_hot_water_temperature_difference": {
                "field_name": "Beam Rated Heating Room Air Hot Water Temperature Difference",
                "field_type": "n"
            },
            "beam_rated_hot_water_volume_flow_rate_per_beam_length": {
                "field_name": "Beam Rated Hot Water Volume Flow Rate per Beam Length",
                "field_type": "n"
            },
            "beam_heating_capacity_temperature_difference_modification_factor_curve_name": {
                "field_name": "Beam Heating Capacity Temperature Difference Modification Factor Curve Name",
                "field_type": "a"
            },
            "beam_heating_capacity_air_flow_modification_factor_curve_name": {
                "field_name": "Beam Heating Capacity Air Flow Modification Factor Curve Name",
                "field_type": "a"
            },
            "beam_heating_capacity_hot_water_flow_modification_factor_curve_name": {
                "field_name": "Beam Heating Capacity Hot Water Flow Modification Factor Curve Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "primary_air_availability_schedule_name",
            "cooling_availability_schedule_name",
            "heating_availability_schedule_name",
            "primary_air_inlet_node_name",
            "primary_air_outlet_node_name",
            "chilled_water_inlet_node_name",
            "chilled_water_outlet_node_name",
            "hot_water_inlet_node_name",
            "hot_water_outlet_node_name",
            "design_primary_air_volume_flow_rate",
            "design_chilled_water_volume_flow_rate",
            "design_hot_water_volume_flow_rate",
            "zone_total_beam_length",
            "rated_primary_air_flow_rate_per_beam_length",
            "beam_rated_cooling_capacity_per_beam_length",
            "beam_rated_cooling_room_air_chilled_water_temperature_difference",
            "beam_rated_chilled_water_volume_flow_rate_per_beam_length",
            "beam_cooling_capacity_temperature_difference_modification_factor_curve_name",
            "beam_cooling_capacity_air_flow_modification_factor_curve_name",
            "beam_cooling_capacity_chilled_water_flow_modification_factor_curve_name",
            "beam_rated_heating_capacity_per_beam_length",
            "beam_rated_heating_room_air_hot_water_temperature_difference",
            "beam_rated_hot_water_volume_flow_rate_per_beam_length",
            "beam_heating_capacity_temperature_difference_modification_factor_curve_name",
            "beam_heating_capacity_air_flow_modification_factor_curve_name",
            "beam_heating_capacity_hot_water_flow_modification_factor_curve_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "primary_air_availability_schedule_name",
                "cooling_availability_schedule_name",
                "heating_availability_schedule_name",
                "primary_air_inlet_node_name",
                "primary_air_outlet_node_name",
                "chilled_water_inlet_node_name",
                "chilled_water_outlet_node_name",
                "hot_water_inlet_node_name",
                "hot_water_outlet_node_name",
                "beam_cooling_capacity_temperature_difference_modification_factor_curve_name",
                "beam_cooling_capacity_air_flow_modification_factor_curve_name",
                "beam_cooling_capacity_chilled_water_flow_modification_factor_curve_name",
                "beam_heating_capacity_temperature_difference_modification_factor_curve_name",
                "beam_heating_capacity_air_flow_modification_factor_curve_name",
                "beam_heating_capacity_hot_water_flow_modification_factor_curve_name"
            ]
        },
        "numerics": {
            "fields": [
                "design_primary_air_volume_flow_rate",
                "design_chilled_water_volume_flow_rate",
                "design_hot_water_volume_flow_rate",
                "zone_total_beam_length",
                "rated_primary_air_flow_rate_per_beam_length",
                "beam_rated_cooling_capacity_per_beam_length",
                "beam_rated_cooling_room_air_chilled_water_temperature_difference",
                "beam_rated_chilled_water_volume_flow_rate_per_beam_length",
                "beam_rated_heating_capacity_per_beam_length",
                "beam_rated_heating_room_air_hot_water_temperature_difference",
                "beam_rated_hot_water_volume_flow_rate_per_beam_length"
            ]
        }
    },
    "type": "object",
    "memo": "Central air system terminal unit, single duct, constant volume, with heating and/or cooling. Operates as two-pipe unit if heating or cooling water is omitted. Heating and/or cooling can be scheduled off for dedicated ventilation."
}
```
