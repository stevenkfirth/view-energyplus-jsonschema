```
{
    "Sizing:Zone": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "zone_or_zonelist_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneAndZoneListNames"
                        ]
                    },
                    "zone_cooling_design_supply_air_temperature_input_method": {
                        "type": "string",
                        "enum": [
                            "",
                            "SupplyAirTemperature",
                            "TemperatureDifference"
                        ],
                        "default": "SupplyAirTemperature"
                    },
                    "zone_cooling_design_supply_air_temperature": {
                        "type": "number",
                        "units": "C",
                        "note": "Zone Cooling Design Supply Air Temperature is only used when Zone Cooling Design Supply Air Temperature Input Method = SupplyAirTemperature"
                    },
                    "zone_cooling_design_supply_air_temperature_difference": {
                        "type": "number",
                        "units": "deltaC",
                        "note": "Zone Cooling Design Supply Air Temperature is only used when Zone Cooling Design Supply Air Temperature Input Method = TemperatureDifference The absolute value of this field will be subtracted from the zone temperature at peak load to calculate the Zone Cooling Design Supply Air Temperature."
                    },
                    "zone_heating_design_supply_air_temperature_input_method": {
                        "type": "string",
                        "enum": [
                            "",
                            "SupplyAirTemperature",
                            "TemperatureDifference"
                        ],
                        "default": "SupplyAirTemperature"
                    },
                    "zone_heating_design_supply_air_temperature": {
                        "type": "number",
                        "units": "C",
                        "note": "Zone Heating Design Supply Air Temperature is only used when Zone Heating Design Supply Air Temperature Input Method = SupplyAirTemperature"
                    },
                    "zone_heating_design_supply_air_temperature_difference": {
                        "type": "number",
                        "units": "deltaC",
                        "note": "Zone Heating Design Supply Air Temperature is only used when Zone Heating Design Supply Air Temperature Input Method = TemperatureDifference The absolute value of this field will be added to the zone temperature at peak load to calculate the Zone Heating Design Supply Air Temperature."
                    },
                    "zone_cooling_design_supply_air_humidity_ratio": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kgWater/kgDryAir"
                    },
                    "zone_heating_design_supply_air_humidity_ratio": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kgWater/kgDryAir"
                    },
                    "design_specification_outdoor_air_object_name": {
                        "type": "string",
                        "note": "Specify the name of a DesignSpecification:OutdoorAir object to specify one set of requirements for the Zone. Use a DesignSpecification:OutdoorAir:SpaceList object name to specify different  requirements for Spaces within the Zone.",
                        "data_type": "object_list",
                        "object_list": [
                            "DSOASpaceListNames",
                            "DesignSpecificationOutdoorAirNames"
                        ]
                    },
                    "zone_heating_sizing_factor": {
                        "type": "number",
                        "note": "if blank or zero, global heating sizing factor from Sizing:Parameters is used.",
                        "minimum": 0.0
                    },
                    "zone_cooling_sizing_factor": {
                        "type": "number",
                        "note": "if blank or zero, global cooling sizing factor from Sizing:Parameters is used.",
                        "minimum": 0.0
                    },
                    "cooling_design_air_flow_method": {
                        "type": "string",
                        "enum": [
                            "",
                            "DesignDay",
                            "DesignDayWithLimit",
                            "Flow/Zone"
                        ],
                        "default": "DesignDay"
                    },
                    "cooling_design_air_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0,
                        "default": 0.0,
                        "note": "This input is used if Cooling Design Air Flow Method is Flow/Zone This value will be multiplied by the global or zone sizing factor and by zone multipliers."
                    },
                    "cooling_minimum_air_flow_per_zone_floor_area": {
                        "type": "number",
                        "units": "m3/s-m2",
                        "minimum": 0.0,
                        "default": 0.000762,
                        "note": "default is .15 cfm/ft2 This input is used if Cooling Design Air Flow Method is DesignDayWithLimit"
                    },
                    "cooling_minimum_air_flow": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0,
                        "default": 0.0,
                        "note": "This input is used if Cooling Design Air Flow Method is DesignDayWithLimit"
                    },
                    "cooling_minimum_air_flow_fraction": {
                        "type": "number",
                        "note": "fraction of the Cooling design Air Flow Rate This input is currently used in sizing the VAV air terminal unit and fan minimum flow rate It does not currently affect other component autosizing.",
                        "minimum": 0.0,
                        "default": 0.2
                    },
                    "heating_design_air_flow_method": {
                        "type": "string",
                        "enum": [
                            "",
                            "DesignDay",
                            "DesignDayWithLimit",
                            "Flow/Zone"
                        ],
                        "default": "DesignDay"
                    },
                    "heating_design_air_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0,
                        "default": 0.0,
                        "note": "This input is used if Heating Design Air Flow Method is Flow/Zone. This value will be multiplied by the global or zone sizing factor and by zone multipliers."
                    },
                    "heating_maximum_air_flow_per_zone_floor_area": {
                        "type": "number",
                        "units": "m3/s-m2",
                        "minimum": 0.0,
                        "default": 0.002032,
                        "note": "default is .40 cfm/ft2 This field is used to size the heating design flow rate when Heating Design Air Flow Method = Flow/Zone. This input is used for autosizing components when Heating Design Air Flow Method = DesignDayWithLimit."
                    },
                    "heating_maximum_air_flow": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0,
                        "default": 0.1415762,
                        "note": "default is 300 cfm This input is used for autosizing components when Heating Design Air Flow Method = DesignDayWithLimit."
                    },
                    "heating_maximum_air_flow_fraction": {
                        "type": "number",
                        "note": "fraction of the Heating Design Air Flow Rate This input is used for autosizing components when Heating Design Air Flow Method = DesignDayWithLimit.",
                        "minimum": 0.0,
                        "default": 0.3
                    },
                    "design_specification_zone_air_distribution_object_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DesignSpecificationZoneAirDistributionNames"
                        ]
                    },
                    "account_for_dedicated_outdoor_air_system": {
                        "type": "string",
                        "note": "account for effect of dedicated outdoor air system supplying air directly to the zone",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No"
                    },
                    "dedicated_outdoor_air_system_control_strategy": {
                        "type": "string",
                        "note": "1)supply neutral ventilation air; 2)supply neutral dehumidified and reheated ventilation air; 3)supply cold ventilation air",
                        "enum": [
                            "",
                            "ColdSupplyAir",
                            "NeutralDehumidifiedSupplyAir",
                            "NeutralSupplyAir"
                        ],
                        "default": "NeutralSupplyAir"
                    },
                    "dedicated_outdoor_air_low_setpoint_temperature_for_design": {
                        "units": "C",
                        "default": "Autosize",
                        "anyOf": [
                            {
                                "type": "number"
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
                    "dedicated_outdoor_air_high_setpoint_temperature_for_design": {
                        "units": "C",
                        "default": "Autosize",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "",
                                    "Autosize"
                                ]
                            }
                        ]
                    }
                },
                "required": [
                    "zone_or_zonelist_name",
                    "zone_cooling_design_supply_air_humidity_ratio",
                    "zone_heating_design_supply_air_humidity_ratio"
                ]
            }
        },
        "group": "HVAC Design Objects",
        "legacy_idd": {
            "field_info": {
                "zone_or_zonelist_name": {
                    "field_name": "Zone or ZoneList Name",
                    "field_type": "a"
                },
                "zone_cooling_design_supply_air_temperature_input_method": {
                    "field_name": "Zone Cooling Design Supply Air Temperature Input Method",
                    "field_type": "a"
                },
                "zone_cooling_design_supply_air_temperature": {
                    "field_name": "Zone Cooling Design Supply Air Temperature",
                    "field_type": "n"
                },
                "zone_cooling_design_supply_air_temperature_difference": {
                    "field_name": "Zone Cooling Design Supply Air Temperature Difference",
                    "field_type": "n"
                },
                "zone_heating_design_supply_air_temperature_input_method": {
                    "field_name": "Zone Heating Design Supply Air Temperature Input Method",
                    "field_type": "a"
                },
                "zone_heating_design_supply_air_temperature": {
                    "field_name": "Zone Heating Design Supply Air Temperature",
                    "field_type": "n"
                },
                "zone_heating_design_supply_air_temperature_difference": {
                    "field_name": "Zone Heating Design Supply Air Temperature Difference",
                    "field_type": "n"
                },
                "zone_cooling_design_supply_air_humidity_ratio": {
                    "field_name": "Zone Cooling Design Supply Air Humidity Ratio",
                    "field_type": "n"
                },
                "zone_heating_design_supply_air_humidity_ratio": {
                    "field_name": "Zone Heating Design Supply Air Humidity Ratio",
                    "field_type": "n"
                },
                "design_specification_outdoor_air_object_name": {
                    "field_name": "Design Specification Outdoor Air Object Name",
                    "field_type": "a"
                },
                "zone_heating_sizing_factor": {
                    "field_name": "Zone Heating Sizing Factor",
                    "field_type": "n"
                },
                "zone_cooling_sizing_factor": {
                    "field_name": "Zone Cooling Sizing Factor",
                    "field_type": "n"
                },
                "cooling_design_air_flow_method": {
                    "field_name": "Cooling Design Air Flow Method",
                    "field_type": "a"
                },
                "cooling_design_air_flow_rate": {
                    "field_name": "Cooling Design Air Flow Rate",
                    "field_type": "n"
                },
                "cooling_minimum_air_flow_per_zone_floor_area": {
                    "field_name": "Cooling Minimum Air Flow per Zone Floor Area",
                    "field_type": "n"
                },
                "cooling_minimum_air_flow": {
                    "field_name": "Cooling Minimum Air Flow",
                    "field_type": "n"
                },
                "cooling_minimum_air_flow_fraction": {
                    "field_name": "Cooling Minimum Air Flow Fraction",
                    "field_type": "n"
                },
                "heating_design_air_flow_method": {
                    "field_name": "Heating Design Air Flow Method",
                    "field_type": "a"
                },
                "heating_design_air_flow_rate": {
                    "field_name": "Heating Design Air Flow Rate",
                    "field_type": "n"
                },
                "heating_maximum_air_flow_per_zone_floor_area": {
                    "field_name": "Heating Maximum Air Flow per Zone Floor Area",
                    "field_type": "n"
                },
                "heating_maximum_air_flow": {
                    "field_name": "Heating Maximum Air Flow",
                    "field_type": "n"
                },
                "heating_maximum_air_flow_fraction": {
                    "field_name": "Heating Maximum Air Flow Fraction",
                    "field_type": "n"
                },
                "design_specification_zone_air_distribution_object_name": {
                    "field_name": "Design Specification Zone Air Distribution Object Name",
                    "field_type": "a"
                },
                "account_for_dedicated_outdoor_air_system": {
                    "field_name": "Account for Dedicated Outdoor Air System",
                    "field_type": "a"
                },
                "dedicated_outdoor_air_system_control_strategy": {
                    "field_name": "Dedicated Outdoor Air System Control Strategy",
                    "field_type": "a"
                },
                "dedicated_outdoor_air_low_setpoint_temperature_for_design": {
                    "field_name": "Dedicated Outdoor Air Low Setpoint Temperature for Design",
                    "field_type": "n"
                },
                "dedicated_outdoor_air_high_setpoint_temperature_for_design": {
                    "field_name": "Dedicated Outdoor Air High Setpoint Temperature for Design",
                    "field_type": "n"
                }
            },
            "fields": [
                "zone_or_zonelist_name",
                "zone_cooling_design_supply_air_temperature_input_method",
                "zone_cooling_design_supply_air_temperature",
                "zone_cooling_design_supply_air_temperature_difference",
                "zone_heating_design_supply_air_temperature_input_method",
                "zone_heating_design_supply_air_temperature",
                "zone_heating_design_supply_air_temperature_difference",
                "zone_cooling_design_supply_air_humidity_ratio",
                "zone_heating_design_supply_air_humidity_ratio",
                "design_specification_outdoor_air_object_name",
                "zone_heating_sizing_factor",
                "zone_cooling_sizing_factor",
                "cooling_design_air_flow_method",
                "cooling_design_air_flow_rate",
                "cooling_minimum_air_flow_per_zone_floor_area",
                "cooling_minimum_air_flow",
                "cooling_minimum_air_flow_fraction",
                "heating_design_air_flow_method",
                "heating_design_air_flow_rate",
                "heating_maximum_air_flow_per_zone_floor_area",
                "heating_maximum_air_flow",
                "heating_maximum_air_flow_fraction",
                "design_specification_zone_air_distribution_object_name",
                "account_for_dedicated_outdoor_air_system",
                "dedicated_outdoor_air_system_control_strategy",
                "dedicated_outdoor_air_low_setpoint_temperature_for_design",
                "dedicated_outdoor_air_high_setpoint_temperature_for_design"
            ],
            "alphas": {
                "fields": [
                    "zone_or_zonelist_name",
                    "zone_cooling_design_supply_air_temperature_input_method",
                    "zone_heating_design_supply_air_temperature_input_method",
                    "design_specification_outdoor_air_object_name",
                    "cooling_design_air_flow_method",
                    "heating_design_air_flow_method",
                    "design_specification_zone_air_distribution_object_name",
                    "account_for_dedicated_outdoor_air_system",
                    "dedicated_outdoor_air_system_control_strategy"
                ]
            },
            "numerics": {
                "fields": [
                    "zone_cooling_design_supply_air_temperature",
                    "zone_cooling_design_supply_air_temperature_difference",
                    "zone_heating_design_supply_air_temperature",
                    "zone_heating_design_supply_air_temperature_difference",
                    "zone_cooling_design_supply_air_humidity_ratio",
                    "zone_heating_design_supply_air_humidity_ratio",
                    "zone_heating_sizing_factor",
                    "zone_cooling_sizing_factor",
                    "cooling_design_air_flow_rate",
                    "cooling_minimum_air_flow_per_zone_floor_area",
                    "cooling_minimum_air_flow",
                    "cooling_minimum_air_flow_fraction",
                    "heating_design_air_flow_rate",
                    "heating_maximum_air_flow_per_zone_floor_area",
                    "heating_maximum_air_flow",
                    "heating_maximum_air_flow_fraction",
                    "dedicated_outdoor_air_low_setpoint_temperature_for_design",
                    "dedicated_outdoor_air_high_setpoint_temperature_for_design"
                ]
            }
        },
        "type": "object",
        "memo": "Specifies the data needed to perform a zone design air flow calculation. The calculation is done for every sizing period included in the input. The maximum cooling and heating load and cooling, heating, and ventilation air flows are then saved for system level and zone component design calculations.",
        "min_fields": 27.0
    }
}
```
