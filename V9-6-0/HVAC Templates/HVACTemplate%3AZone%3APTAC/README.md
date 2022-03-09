```
{
    "HVACTemplate:Zone:PTAC": {
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
                    "template_thermostat_name": {
                        "type": "string",
                        "note": "Enter the name of a HVACTemplate:Thermostat object. If blank, then it is assumed that standard thermostat objects have been defined for this zone.",
                        "data_type": "object_list",
                        "object_list": [
                            "CompactHVACThermostats"
                        ]
                    },
                    "cooling_supply_air_flow_rate": {
                        "note": "Supply air flow rate during cooling operation This field may be set to \"autosize\". If a value is entered, it will be multiplied by the Supply Air Sizing Factor and by zone multipliers.",
                        "default": "Autosize",
                        "units": "m3/s",
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
                    "heating_supply_air_flow_rate": {
                        "note": "Supply air flow rate during heating operation This field may be set to \"autosize\". If a value is entered, it will be multiplied by the Supply Air Sizing Factor and by zone multipliers.",
                        "default": "Autosize",
                        "units": "m3/s",
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
                    "no_load_supply_air_flow_rate": {
                        "note": "Supply air flow rate when no cooling or heating is needed Only used when heat pump fan operating mode is continuous. This air flow rate is used when no heating or cooling is required and the DX coil compressor is off. If this field is left blank or zero, the supply air flow rate from the previous on cycle (either cooling or heating) is used. A value entered in this field will *not* be multiplied by the sizing factor or by zone multipliers. It is best to autosize or leave blank when using zone multipliers.",
                        "units": "m3/s",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.0
                            },
                            {
                                "type": "string",
                                "enum": [
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
                    "system_availability_schedule_name": {
                        "type": "string",
                        "note": "If blank, always on",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "supply_fan_operating_mode_schedule_name": {
                        "type": "string",
                        "note": "Refers to a schedule to specify unitary supply fan operating mode. Schedule Name values of 0 indicate cycling fan (auto) Schedule values of 1 indicate continuous fan (on) If this field is left blank, a schedule of always zero (cycling fan) will be used.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "supply_fan_placement": {
                        "type": "string",
                        "enum": [
                            "",
                            "BlowThrough",
                            "DrawThrough"
                        ],
                        "default": "DrawThrough"
                    },
                    "supply_fan_total_efficiency": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.7
                    },
                    "supply_fan_delta_pressure": {
                        "type": "number",
                        "units": "Pa",
                        "ip-units": "inH2O",
                        "minimum": 0.0,
                        "default": 75.0
                    },
                    "supply_fan_motor_efficiency": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.9
                    },
                    "cooling_coil_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "SingleSpeedDX"
                        ],
                        "default": "SingleSpeedDX"
                    },
                    "cooling_coil_availability_schedule_name": {
                        "type": "string",
                        "note": "If blank, always on",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "cooling_coil_gross_rated_total_capacity": {
                        "note": "Total cooling capacity not accounting for the effect of supply air fan heat Rating point: air entering the cooling coil at 26.7 C dry-bulb/19.4 C wet-bulb, and air entering the outdoor condenser coil at 35 C dry-bulb/23.9 C wet-bulb",
                        "default": "Autosize",
                        "units": "W",
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
                    "cooling_coil_gross_rated_sensible_heat_ratio": {
                        "note": "Rated sensible heat ratio (gross sensible capacity/gross total capacity) Sensible and total capacities do not include effect of supply fan heat",
                        "default": "Autosize",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.5,
                                "maximum": 1.0
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
                    "cooling_coil_gross_rated_cooling_cop": {
                        "type": "number",
                        "note": "Gross cooling capacity divided by power input to the compressor and outdoor fan, does not include supply fan heat or supply fan electrical energy input",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0,
                        "default": 3.0
                    },
                    "heating_coil_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Electric",
                            "Gas",
                            "HotWater"
                        ],
                        "default": "Electric"
                    },
                    "heating_coil_availability_schedule_name": {
                        "type": "string",
                        "note": "If blank, always on",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "heating_coil_capacity": {
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
                    "gas_heating_coil_efficiency": {
                        "type": "number",
                        "note": "Applies only if Heating Coil Type is Gas",
                        "maximum": 1.0,
                        "minimum": 0.0,
                        "default": 0.8
                    },
                    "gas_heating_coil_parasitic_electric_load": {
                        "type": "number",
                        "note": "Applies only if Heating Coil Type is Gas",
                        "units": "W",
                        "ip-units": "W",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "dedicated_outdoor_air_system_name": {
                        "type": "string",
                        "note": "Enter the name of an HVACTemplate:System:DedicatedOutdoorAir object if this zone is served by a separate dedicated outdoor air system (DOAS). Leave field blank if no DOAS serves this zone.",
                        "data_type": "object_list",
                        "object_list": [
                            "HVACTemplateDOASSystems"
                        ]
                    },
                    "zone_cooling_design_supply_air_temperature_input_method": {
                        "type": "string",
                        "note": "SupplyAirTemperature = use the value from Zone Cooling Design Supply Air Temperature TemperatureDifference = use the value from Zone Cooling Design Supply Air Temperature Difference",
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
                        "default": 14.0,
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
                    "capacity_control_method": {
                        "type": "string",
                        "enum": [
                            "",
                            "None",
                            "SingleZoneVAV"
                        ],
                        "default": "None"
                    }
                },
                "required": [
                    "zone_name"
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
                "template_thermostat_name": {
                    "field_name": "Template Thermostat Name",
                    "field_type": "a"
                },
                "cooling_supply_air_flow_rate": {
                    "field_name": "Cooling Supply Air Flow Rate",
                    "field_type": "n"
                },
                "heating_supply_air_flow_rate": {
                    "field_name": "Heating Supply Air Flow Rate",
                    "field_type": "n"
                },
                "no_load_supply_air_flow_rate": {
                    "field_name": "No Load Supply Air Flow Rate",
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
                "system_availability_schedule_name": {
                    "field_name": "System Availability Schedule Name",
                    "field_type": "a"
                },
                "supply_fan_operating_mode_schedule_name": {
                    "field_name": "Supply Fan Operating Mode Schedule Name",
                    "field_type": "a"
                },
                "supply_fan_placement": {
                    "field_name": "Supply Fan Placement",
                    "field_type": "a"
                },
                "supply_fan_total_efficiency": {
                    "field_name": "Supply Fan Total Efficiency",
                    "field_type": "n"
                },
                "supply_fan_delta_pressure": {
                    "field_name": "Supply Fan Delta Pressure",
                    "field_type": "n"
                },
                "supply_fan_motor_efficiency": {
                    "field_name": "Supply Fan Motor Efficiency",
                    "field_type": "n"
                },
                "cooling_coil_type": {
                    "field_name": "Cooling Coil Type",
                    "field_type": "a"
                },
                "cooling_coil_availability_schedule_name": {
                    "field_name": "Cooling Coil Availability Schedule Name",
                    "field_type": "a"
                },
                "cooling_coil_gross_rated_total_capacity": {
                    "field_name": "Cooling Coil Gross Rated Total Capacity",
                    "field_type": "n"
                },
                "cooling_coil_gross_rated_sensible_heat_ratio": {
                    "field_name": "Cooling Coil Gross Rated Sensible Heat Ratio",
                    "field_type": "n"
                },
                "cooling_coil_gross_rated_cooling_cop": {
                    "field_name": "Cooling Coil Gross Rated Cooling COP",
                    "field_type": "n"
                },
                "heating_coil_type": {
                    "field_name": "Heating Coil Type",
                    "field_type": "a"
                },
                "heating_coil_availability_schedule_name": {
                    "field_name": "Heating Coil Availability Schedule Name",
                    "field_type": "a"
                },
                "heating_coil_capacity": {
                    "field_name": "Heating Coil Capacity",
                    "field_type": "n"
                },
                "gas_heating_coil_efficiency": {
                    "field_name": "Gas Heating Coil Efficiency",
                    "field_type": "n"
                },
                "gas_heating_coil_parasitic_electric_load": {
                    "field_name": "Gas Heating Coil Parasitic Electric Load",
                    "field_type": "n"
                },
                "dedicated_outdoor_air_system_name": {
                    "field_name": "Dedicated Outdoor Air System Name",
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
                "design_specification_outdoor_air_object_name": {
                    "field_name": "Design Specification Outdoor Air Object Name",
                    "field_type": "a"
                },
                "design_specification_zone_air_distribution_object_name": {
                    "field_name": "Design Specification Zone Air Distribution Object Name",
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
                "capacity_control_method": {
                    "field_name": "Capacity Control Method",
                    "field_type": "a"
                }
            },
            "fields": [
                "zone_name",
                "template_thermostat_name",
                "cooling_supply_air_flow_rate",
                "heating_supply_air_flow_rate",
                "no_load_supply_air_flow_rate",
                "zone_heating_sizing_factor",
                "zone_cooling_sizing_factor",
                "outdoor_air_method",
                "outdoor_air_flow_rate_per_person",
                "outdoor_air_flow_rate_per_zone_floor_area",
                "outdoor_air_flow_rate_per_zone",
                "system_availability_schedule_name",
                "supply_fan_operating_mode_schedule_name",
                "supply_fan_placement",
                "supply_fan_total_efficiency",
                "supply_fan_delta_pressure",
                "supply_fan_motor_efficiency",
                "cooling_coil_type",
                "cooling_coil_availability_schedule_name",
                "cooling_coil_gross_rated_total_capacity",
                "cooling_coil_gross_rated_sensible_heat_ratio",
                "cooling_coil_gross_rated_cooling_cop",
                "heating_coil_type",
                "heating_coil_availability_schedule_name",
                "heating_coil_capacity",
                "gas_heating_coil_efficiency",
                "gas_heating_coil_parasitic_electric_load",
                "dedicated_outdoor_air_system_name",
                "zone_cooling_design_supply_air_temperature_input_method",
                "zone_cooling_design_supply_air_temperature",
                "zone_cooling_design_supply_air_temperature_difference",
                "zone_heating_design_supply_air_temperature_input_method",
                "zone_heating_design_supply_air_temperature",
                "zone_heating_design_supply_air_temperature_difference",
                "design_specification_outdoor_air_object_name",
                "design_specification_zone_air_distribution_object_name",
                "baseboard_heating_type",
                "baseboard_heating_availability_schedule_name",
                "baseboard_heating_capacity",
                "capacity_control_method"
            ],
            "alphas": {
                "fields": [
                    "zone_name",
                    "template_thermostat_name",
                    "outdoor_air_method",
                    "system_availability_schedule_name",
                    "supply_fan_operating_mode_schedule_name",
                    "supply_fan_placement",
                    "cooling_coil_type",
                    "cooling_coil_availability_schedule_name",
                    "heating_coil_type",
                    "heating_coil_availability_schedule_name",
                    "dedicated_outdoor_air_system_name",
                    "zone_cooling_design_supply_air_temperature_input_method",
                    "zone_heating_design_supply_air_temperature_input_method",
                    "design_specification_outdoor_air_object_name",
                    "design_specification_zone_air_distribution_object_name",
                    "baseboard_heating_type",
                    "baseboard_heating_availability_schedule_name",
                    "capacity_control_method"
                ]
            },
            "numerics": {
                "fields": [
                    "cooling_supply_air_flow_rate",
                    "heating_supply_air_flow_rate",
                    "no_load_supply_air_flow_rate",
                    "zone_heating_sizing_factor",
                    "zone_cooling_sizing_factor",
                    "outdoor_air_flow_rate_per_person",
                    "outdoor_air_flow_rate_per_zone_floor_area",
                    "outdoor_air_flow_rate_per_zone",
                    "supply_fan_total_efficiency",
                    "supply_fan_delta_pressure",
                    "supply_fan_motor_efficiency",
                    "cooling_coil_gross_rated_total_capacity",
                    "cooling_coil_gross_rated_sensible_heat_ratio",
                    "cooling_coil_gross_rated_cooling_cop",
                    "heating_coil_capacity",
                    "gas_heating_coil_efficiency",
                    "gas_heating_coil_parasitic_electric_load",
                    "zone_cooling_design_supply_air_temperature",
                    "zone_cooling_design_supply_air_temperature_difference",
                    "zone_heating_design_supply_air_temperature",
                    "zone_heating_design_supply_air_temperature_difference",
                    "baseboard_heating_capacity"
                ]
            }
        },
        "type": "object",
        "memo": "Packaged Terminal Air Conditioner",
        "min_fields": 40.0
    }
}
```
