```
{
    "HVACTemplate:Zone:VAV": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "zone_name": {
                        "type": "string",
                        "note": "Zone name must match a building zone name",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "template_vav_system_name": {
                        "type": "string",
                        "note": "Name of a HVACTemplate:System:VAV or HVACTemplate:System:PackagedVAV object serving this zone",
                        "data_type": "object_list",
                        "object_list": [
                            "CompactHVACSystemVAV"
                        ]
                    },
                    "template_thermostat_name": {
                        "type": "string",
                        "note": "Enter the name of a HVACTemplate:Thermostat object. If blank, then it is assumed that standard thermostat objects have been defined for this zone.",
                        "data_type": "object_list",
                        "object_list": [
                            "CompactHVACThermostats"
                        ]
                    },
                    "supply_air_maximum_flow_rate": {
                        "note": "This field may be set to \"autosize\". If a value is entered, it will be multiplied by the Supply Air Sizing Factor and by zone multipliers.",
                        "default": "Autosize",
                        "units": "m3/s",
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
                    "zone_heating_sizing_factor": {
                        "type": "number",
                        "note": "If blank, value from Sizing:Parameters will be used.",
                        "minimum": 0.0
                    },
                    "zone_cooling_sizing_factor": {
                        "type": "number",
                        "note": "If blank, value from Sizing:Parameters will be used.",
                        "minimum": 0.0
                    },
                    "zone_minimum_air_flow_input_method": {
                        "type": "string",
                        "enum": [
                            "",
                            "Constant",
                            "FixedFlowRate",
                            "Scheduled"
                        ],
                        "default": "Constant",
                        "note": "Constant = Constant Minimum Air Flow Fraction (a fraction of Maximum Air Flow Rate) FixedFlowRate = Fixed Minimum Air Flow Rate (a fixed minimum air volume flow rate) Scheduled = Scheduled Minimum Air Flow Fraction (a fraction of Maximum Air Flow"
                    },
                    "constant_minimum_air_flow_fraction": {
                        "type": "number",
                        "note": "This field is used if the field Zone Minimum Air Flow Input Method is Constant If the field Zone Minimum Air Flow Input Method is Scheduled, then this field is optional. If a value is entered, then it is used for sizing normal-action reheat coils. If both this field and the following field are entered, the larger result is used.",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.2
                    },
                    "fixed_minimum_air_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "note": "This field is used if the field Zone Minimum Air Flow Input Method is FixedFlowRate. If the field Zone Minimum Air Flow Input Method is Scheduled, then this field is optional. If a value is entered, then it is used for sizing normal-action reheat coils. If both this field and the previous field are entered, the larger result is used."
                    },
                    "minimum_air_flow_fraction_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "This field is used if the field Zone Minimum Air Flow Input Method is Scheduled Schedule values are fractions, 0.0 to 1.0. If the field Constant Minimum Air Flow Fraction is blank, then the average of the minimum and maximum schedule values is used for sizing normal-action reheat coils."
                    },
                    "outdoor_air_method": {
                        "type": "string",
                        "note": "Flow/Person, Flow/Zone, Flow/Area, Sum, and Maximum use the values in the next three fields: Outdoor Air Flow Rate per Person, Outdoor Air Flow Rate per Zone Floor Area, and Outdoor Air Flow Rate per Zone. DetailedSpecification ignores these three Outdoor Air Flow Rate fields and instead references design specification objects named in the fields Design Specification Outdoor Air Object Name and Design Specification Zone Air Distribution Object Name.",
                        "enum": [
                            "",
                            "DetailedSpecification",
                            "Flow/Area",
                            "Flow/Person",
                            "Flow/Zone",
                            "Maximum",
                            "Sum"
                        ],
                        "default": "Flow/Person"
                    },
                    "outdoor_air_flow_rate_per_person": {
                        "type": "number",
                        "units": "m3/s",
                        "note": "Default 0.00944 is 20 cfm per person This input is used if the field Outdoor Air Method is Flow/Person, Sum, or Maximum",
                        "default": 0.00944
                    },
                    "outdoor_air_flow_rate_per_zone_floor_area": {
                        "type": "number",
                        "units": "m3/s-m2",
                        "default": 0.0,
                        "note": "This input is used if the field Outdoor Air Method is Flow/Area, Sum, or Maximum"
                    },
                    "outdoor_air_flow_rate_per_zone": {
                        "type": "number",
                        "units": "m3/s",
                        "default": 0.0,
                        "note": "This input is used if the field Outdoor Air Method is Flow/Zone, Sum, or Maximum"
                    },
                    "reheat_coil_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Electric",
                            "Gas",
                            "HotWater",
                            "None"
                        ],
                        "default": "None"
                    },
                    "reheat_coil_availability_schedule_name": {
                        "type": "string",
                        "note": "If blank, always on",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "damper_heating_action": {
                        "type": "string",
                        "enum": [
                            "",
                            "Normal",
                            "Reverse"
                        ],
                        "default": "Reverse"
                    },
                    "maximum_flow_per_zone_floor_area_during_reheat": {
                        "units": "m3/s-m2",
                        "note": "Used only when Reheat Coil Object Type = Coil:Heating:Water and Damper Heating Action = Reverse When autocalculating, the maximum flow per zone is set to 0.002032 m3/s-m2 (0.4 cfm/sqft) This optional field limits the maximum flow allowed in reheat mode. If this field and the following field are left blank, the maximum flow will not be limited. At no time will the maximum flow rate calculated here exceed the value of Maximum Air Flow Rate.",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autocalculate"
                                ]
                            }
                        ]
                    },
                    "maximum_flow_fraction_during_reheat": {
                        "note": "Used only when Reheat Coil Object Type = Coil:Heating:Water and Damper Heating Action = Reverse When autocalculating, the maximum flow fraction is set to the ratio of 0.002032 m3/s-m2 (0.4 cfm/sqft) multiplied by the zone floor area and the Maximum Air Flow Rate. This optional field limits the maximum flow allowed in reheat mode. If this field and the previous field are left blank, the maximum flow will not be limited. At no time will the maximum flow rate calculated here exceed the value of Maximum Air Flow Rate.",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autocalculate"
                                ]
                            }
                        ]
                    },
                    "maximum_reheat_air_temperature": {
                        "type": "number",
                        "note": "Specifies the maximum allowable supply air temperature leaving the reheat coil. If left blank, there is no limit and no default. If unknown, 35C (95F) is recommended.",
                        "units": "C",
                        "exclusiveMinimum": 0.0
                    },
                    "design_specification_outdoor_air_object_name_for_control": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DSOASpaceListNames",
                            "DesignSpecificationOutdoorAirNames"
                        ],
                        "note": "When the name of a DesignSpecification:OutdoorAir object is entered, the terminal unit will increase flow as needed to meet this outdoor air requirement. If Outdoor Air Flow per Person is non-zero, then the outdoor air requirement will be computed based on the current number of occupants in the zone. At no time will the supply air flow rate exceed the value for Maximum Air Flow Rate. If this field is blank, then the terminal unit will not be controlled for outdoor air flow. Note that this field is used only for specifying the design outdoor air flow rate used for control. The field Design Specification Outdoor Air Object Name for Sizing (see below) is used to specify the design outdoor air flow rate."
                    },
                    "supply_plenum_name": {
                        "type": "string",
                        "note": "Plenum zone name. Supply plenum runs through only this zone. Blank if none.",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "return_plenum_name": {
                        "type": "string",
                        "note": "Plenum zone name. Return plenum runs through only this zone. Blank if none.",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "baseboard_heating_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Electric",
                            "HotWater",
                            "None"
                        ],
                        "default": "None"
                    },
                    "baseboard_heating_availability_schedule_name": {
                        "type": "string",
                        "note": "If blank, always on",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "baseboard_heating_capacity": {
                        "default": "Autosize",
                        "units": "W",
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
                    "zone_cooling_design_supply_air_temperature_input_method": {
                        "type": "string",
                        "note": "SupplyAirTemperature = use the value from Zone Cooling Design Supply Air Temperature TemperatureDifference = use the value from Zone Cooling Design Supply Air Temperature Difference SystemSupplyAirTemperature = use the value from HVACTemplate:System:VAV Cooling Coil Design Setpoint",
                        "enum": [
                            "",
                            "SupplyAirTemperature",
                            "SystemSupplyAirTemperature",
                            "TemperatureDifference"
                        ],
                        "default": "SystemSupplyAirTemperature"
                    },
                    "zone_cooling_design_supply_air_temperature": {
                        "type": "number",
                        "units": "C",
                        "default": 12.8,
                        "note": "Zone Cooling Design Supply Air Temperature is only used when Zone Cooling Design Supply Air Temperature Input Method = SupplyAirTemperature"
                    },
                    "zone_cooling_design_supply_air_temperature_difference": {
                        "type": "number",
                        "units": "deltaC",
                        "default": 11.11,
                        "note": "Zone Cooling Design Supply Air Temperature is only used when Zone Cooling Design Supply Air Temperature Input Method = TemperatureDifference The absolute value of this field will be subtracted from the zone temperature at peak load to calculate the Zone Cooling Design Supply Air Temperature."
                    },
                    "zone_heating_design_supply_air_temperature_input_method": {
                        "type": "string",
                        "note": "SupplyAirTemperature = use the value from Zone Heating Design Supply Air Temperature TemperatureDifference = use the value from Zone Heating Design Supply Air Temperature Difference",
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
                        "default": 50.0,
                        "note": "Zone Heating Design Supply Air Temperature is only used when Zone Heating Design Supply Air Temperature Input Method = SupplyAirTemperature"
                    },
                    "zone_heating_design_supply_air_temperature_difference": {
                        "type": "number",
                        "units": "deltaC",
                        "default": 30.0,
                        "note": "Zone Heating Design Supply Air Temperature is only used when Zone Heating Design Supply Air Temperature Input Method = TemperatureDifference The absolute value of this field will be added to the zone temperature at peak load to calculate the Zone Heating Design Supply Air Temperature."
                    },
                    "design_specification_outdoor_air_object_name_for_sizing": {
                        "type": "string",
                        "note": "This field is used only when Outdoor Air Method=DetailedSpecification. Note that this field is used only for specifying the design outdoor air flow rate used for sizing. The field Design Specification Outdoor Air Object Name for Control (see above) is used to actively control the VAV terminal air flow rate.",
                        "data_type": "object_list",
                        "object_list": [
                            "DSOASpaceListNames",
                            "DesignSpecificationOutdoorAirNames"
                        ]
                    },
                    "design_specification_zone_air_distribution_object_name": {
                        "type": "string",
                        "note": "This field is used only when Outdoor Air Method=DetailedSpecification.",
                        "data_type": "object_list",
                        "object_list": [
                            "DesignSpecificationZoneAirDistributionNames"
                        ]
                    }
                },
                "required": [
                    "zone_name",
                    "template_vav_system_name"
                ]
            }
        },
        "group": "HVAC Templates",
        "legacy_idd": {
            "field_info": {
                "zone_name": {
                    "field_name": "Zone Name",
                    "field_type": "a"
                },
                "template_vav_system_name": {
                    "field_name": "Template VAV System Name",
                    "field_type": "a"
                },
                "template_thermostat_name": {
                    "field_name": "Template Thermostat Name",
                    "field_type": "a"
                },
                "supply_air_maximum_flow_rate": {
                    "field_name": "Supply Air Maximum Flow Rate",
                    "field_type": "n"
                },
                "zone_heating_sizing_factor": {
                    "field_name": "Zone Heating Sizing Factor",
                    "field_type": "n"
                },
                "zone_cooling_sizing_factor": {
                    "field_name": "Zone Cooling Sizing Factor",
                    "field_type": "n"
                },
                "zone_minimum_air_flow_input_method": {
                    "field_name": "Zone Minimum Air Flow Input Method",
                    "field_type": "a"
                },
                "constant_minimum_air_flow_fraction": {
                    "field_name": "Constant Minimum Air Flow Fraction",
                    "field_type": "n"
                },
                "fixed_minimum_air_flow_rate": {
                    "field_name": "Fixed Minimum Air Flow Rate",
                    "field_type": "n"
                },
                "minimum_air_flow_fraction_schedule_name": {
                    "field_name": "Minimum Air Flow Fraction Schedule Name",
                    "field_type": "a"
                },
                "outdoor_air_method": {
                    "field_name": "Outdoor Air Method",
                    "field_type": "a"
                },
                "outdoor_air_flow_rate_per_person": {
                    "field_name": "Outdoor Air Flow Rate per Person",
                    "field_type": "n"
                },
                "outdoor_air_flow_rate_per_zone_floor_area": {
                    "field_name": "Outdoor Air Flow Rate per Zone Floor Area",
                    "field_type": "n"
                },
                "outdoor_air_flow_rate_per_zone": {
                    "field_name": "Outdoor Air Flow Rate per Zone",
                    "field_type": "n"
                },
                "reheat_coil_type": {
                    "field_name": "Reheat Coil Type",
                    "field_type": "a"
                },
                "reheat_coil_availability_schedule_name": {
                    "field_name": "Reheat Coil Availability Schedule Name",
                    "field_type": "a"
                },
                "damper_heating_action": {
                    "field_name": "Damper Heating Action",
                    "field_type": "a"
                },
                "maximum_flow_per_zone_floor_area_during_reheat": {
                    "field_name": "Maximum Flow per Zone Floor Area During Reheat",
                    "field_type": "n"
                },
                "maximum_flow_fraction_during_reheat": {
                    "field_name": "Maximum Flow Fraction During Reheat",
                    "field_type": "n"
                },
                "maximum_reheat_air_temperature": {
                    "field_name": "Maximum Reheat Air Temperature",
                    "field_type": "n"
                },
                "design_specification_outdoor_air_object_name_for_control": {
                    "field_name": "Design Specification Outdoor Air Object Name for Control",
                    "field_type": "a"
                },
                "supply_plenum_name": {
                    "field_name": "Supply Plenum Name",
                    "field_type": "a"
                },
                "return_plenum_name": {
                    "field_name": "Return Plenum Name",
                    "field_type": "a"
                },
                "baseboard_heating_type": {
                    "field_name": "Baseboard Heating Type",
                    "field_type": "a"
                },
                "baseboard_heating_availability_schedule_name": {
                    "field_name": "Baseboard Heating Availability Schedule Name",
                    "field_type": "a"
                },
                "baseboard_heating_capacity": {
                    "field_name": "Baseboard Heating Capacity",
                    "field_type": "n"
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
                "design_specification_outdoor_air_object_name_for_sizing": {
                    "field_name": "Design Specification Outdoor Air Object Name for Sizing",
                    "field_type": "a"
                },
                "design_specification_zone_air_distribution_object_name": {
                    "field_name": "Design Specification Zone Air Distribution Object Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "zone_name",
                "template_vav_system_name",
                "template_thermostat_name",
                "supply_air_maximum_flow_rate",
                "zone_heating_sizing_factor",
                "zone_cooling_sizing_factor",
                "zone_minimum_air_flow_input_method",
                "constant_minimum_air_flow_fraction",
                "fixed_minimum_air_flow_rate",
                "minimum_air_flow_fraction_schedule_name",
                "outdoor_air_method",
                "outdoor_air_flow_rate_per_person",
                "outdoor_air_flow_rate_per_zone_floor_area",
                "outdoor_air_flow_rate_per_zone",
                "reheat_coil_type",
                "reheat_coil_availability_schedule_name",
                "damper_heating_action",
                "maximum_flow_per_zone_floor_area_during_reheat",
                "maximum_flow_fraction_during_reheat",
                "maximum_reheat_air_temperature",
                "design_specification_outdoor_air_object_name_for_control",
                "supply_plenum_name",
                "return_plenum_name",
                "baseboard_heating_type",
                "baseboard_heating_availability_schedule_name",
                "baseboard_heating_capacity",
                "zone_cooling_design_supply_air_temperature_input_method",
                "zone_cooling_design_supply_air_temperature",
                "zone_cooling_design_supply_air_temperature_difference",
                "zone_heating_design_supply_air_temperature_input_method",
                "zone_heating_design_supply_air_temperature",
                "zone_heating_design_supply_air_temperature_difference",
                "design_specification_outdoor_air_object_name_for_sizing",
                "design_specification_zone_air_distribution_object_name"
            ],
            "alphas": {
                "fields": [
                    "zone_name",
                    "template_vav_system_name",
                    "template_thermostat_name",
                    "zone_minimum_air_flow_input_method",
                    "minimum_air_flow_fraction_schedule_name",
                    "outdoor_air_method",
                    "reheat_coil_type",
                    "reheat_coil_availability_schedule_name",
                    "damper_heating_action",
                    "design_specification_outdoor_air_object_name_for_control",
                    "supply_plenum_name",
                    "return_plenum_name",
                    "baseboard_heating_type",
                    "baseboard_heating_availability_schedule_name",
                    "zone_cooling_design_supply_air_temperature_input_method",
                    "zone_heating_design_supply_air_temperature_input_method",
                    "design_specification_outdoor_air_object_name_for_sizing",
                    "design_specification_zone_air_distribution_object_name"
                ]
            },
            "numerics": {
                "fields": [
                    "supply_air_maximum_flow_rate",
                    "zone_heating_sizing_factor",
                    "zone_cooling_sizing_factor",
                    "constant_minimum_air_flow_fraction",
                    "fixed_minimum_air_flow_rate",
                    "outdoor_air_flow_rate_per_person",
                    "outdoor_air_flow_rate_per_zone_floor_area",
                    "outdoor_air_flow_rate_per_zone",
                    "maximum_flow_per_zone_floor_area_during_reheat",
                    "maximum_flow_fraction_during_reheat",
                    "maximum_reheat_air_temperature",
                    "baseboard_heating_capacity",
                    "zone_cooling_design_supply_air_temperature",
                    "zone_cooling_design_supply_air_temperature_difference",
                    "zone_heating_design_supply_air_temperature",
                    "zone_heating_design_supply_air_temperature_difference"
                ]
            }
        },
        "type": "object",
        "memo": "Zone terminal unit, variable volume, reheat optional. For heating, this unit activates reheat coil first, then increases airflow (if reverse action specified).",
        "min_fields": 32.0
    }
}
```
