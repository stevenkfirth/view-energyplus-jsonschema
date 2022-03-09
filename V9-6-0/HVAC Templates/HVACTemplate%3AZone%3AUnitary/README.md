```
{
    "HVACTemplate:Zone:Unitary": {
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
                    "template_unitary_system_name": {
                        "type": "string",
                        "note": "Enter the name of an HVACTemplate:System:Unitary, HVACTemplate:System:UnitaryHeatPump:AirTtoAir, or HVACTemplate:System:UnitarySystem object serving this zone.",
                        "data_type": "object_list",
                        "object_list": [
                            "CompactHVACSystemUnitary"
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
                        "note": "SupplyAirTemperature = use the value from Zone Cooling Design Supply Air Temperature TemperatureDifference = use the value from Zone Cooling Design Supply Air Temperature Difference SystemSupplyAirTemperature = use the value from HVACTemplate:System:Unitary or HVACTemplate:System:UnitaryHeatPump:AirToAir Cooling Design Supply Air Temperature",
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
                        "note": "SupplyAirTemperature = use the value from Zone Heating Design Supply Air Temperature TemperatureDifference = use the value from Zone Heating Design Supply Air Temperature Difference SystemSupplyAirTemperature = use the value from HVACTemplate:System:Unitary or HVACTemplate:System:UnitaryHeatPump:AirToAir Heating Design Supply Air Temperature",
                        "enum": [
                            "",
                            "SupplyAirTemperature",
                            "SystemSupplyAirTemperature",
                            "TemperatureDifference"
                        ],
                        "default": "SystemSupplyAirTemperature"
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
                    "design_specification_outdoor_air_object_name": {
                        "type": "string",
                        "note": "This field is used only when Outdoor Air Method=DetailedSpecification.",
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
                    "template_unitary_system_name"
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
                "template_unitary_system_name": {
                    "field_name": "Template Unitary System Name",
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
                "design_specification_outdoor_air_object_name": {
                    "field_name": "Design Specification Outdoor Air Object Name",
                    "field_type": "a"
                },
                "design_specification_zone_air_distribution_object_name": {
                    "field_name": "Design Specification Zone Air Distribution Object Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "zone_name",
                "template_unitary_system_name",
                "template_thermostat_name",
                "supply_air_maximum_flow_rate",
                "zone_heating_sizing_factor",
                "zone_cooling_sizing_factor",
                "outdoor_air_method",
                "outdoor_air_flow_rate_per_person",
                "outdoor_air_flow_rate_per_zone_floor_area",
                "outdoor_air_flow_rate_per_zone",
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
                "design_specification_outdoor_air_object_name",
                "design_specification_zone_air_distribution_object_name"
            ],
            "alphas": {
                "fields": [
                    "zone_name",
                    "template_unitary_system_name",
                    "template_thermostat_name",
                    "outdoor_air_method",
                    "supply_plenum_name",
                    "return_plenum_name",
                    "baseboard_heating_type",
                    "baseboard_heating_availability_schedule_name",
                    "zone_cooling_design_supply_air_temperature_input_method",
                    "zone_heating_design_supply_air_temperature_input_method",
                    "design_specification_outdoor_air_object_name",
                    "design_specification_zone_air_distribution_object_name"
                ]
            },
            "numerics": {
                "fields": [
                    "supply_air_maximum_flow_rate",
                    "zone_heating_sizing_factor",
                    "zone_cooling_sizing_factor",
                    "outdoor_air_flow_rate_per_person",
                    "outdoor_air_flow_rate_per_zone_floor_area",
                    "outdoor_air_flow_rate_per_zone",
                    "baseboard_heating_capacity",
                    "zone_cooling_design_supply_air_temperature",
                    "zone_cooling_design_supply_air_temperature_difference",
                    "zone_heating_design_supply_air_temperature",
                    "zone_heating_design_supply_air_temperature_difference"
                ]
            }
        },
        "type": "object",
        "memo": "Zone terminal unit, constant volume, no controls.",
        "min_fields": 21.0
    }
}
```
