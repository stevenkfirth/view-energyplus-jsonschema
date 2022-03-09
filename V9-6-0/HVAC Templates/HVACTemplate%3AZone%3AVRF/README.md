```
{
    "HVACTemplate:Zone:VRF": {
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
                    "template_vrf_system_name": {
                        "type": "string",
                        "note": "Name of a HVACTemplate:System:VRF object serving this zone",
                        "data_type": "object_list",
                        "object_list": [
                            "CompactHVACSystemVRF"
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
                    "rated_total_heating_capacity_sizing_ratio": {
                        "type": "number",
                        "units": "W/W",
                        "minimum": 1.0,
                        "default": 1.0,
                        "note": "If this terminal unit's heating coil is autosized, the heating capacity is sized to be equal to the cooling capacity multiplied by this sizing ratio. This input applies to the terminal unit heating coil and overrides the sizing ratio entered in the HVACTemplate:System:VRF object."
                    },
                    "cooling_supply_air_flow_rate": {
                        "note": "This field may be set to \"autosize\". If a value is entered, it will be multiplied by the Supply Air Sizing Factor and by zone multipliers.",
                        "units": "m3/s",
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
                    "no_cooling_supply_air_flow_rate": {
                        "note": "This flow rate is used when the terminal is not cooling and the previous mode was cooling. This field may be set to \"autosize\". If a value is entered, it will be multiplied by the Supply Air Sizing Factor and by zone multipliers.",
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
                    "heating_supply_air_flow_rate": {
                        "note": "This field may be set to \"autosize\". If a value is entered, it will be multiplied by the Supply Air Sizing Factor and by zone multipliers.",
                        "units": "m3/s",
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
                    "no_heating_supply_air_flow_rate": {
                        "note": "This flow rate is used when the terminal is not heating and the previous mode was heating. This field may be set to \"autosize\". If a value is entered, it will be multiplied by the Supply Air Sizing Factor and by zone multipliers.",
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
                    "cooling_outdoor_air_flow_rate": {
                        "note": "If this field is set to autosize it will be sized based on the outdoor air inputs below, unless a dedicated outdoor air system is specified for this zone and then it will be set to zero.",
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
                    "heating_outdoor_air_flow_rate": {
                        "note": "If this field is set to autosize it will be sized based on the outdoor air inputs below, unless a dedicated outdoor air system is specified for this zone and then it will be set to zero.",
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
                    "no_load_outdoor_air_flow_rate": {
                        "note": "If this field is set to autosize it will be sized based on the outdoor air inputs below, unless a dedicated outdoor air system is specified for this zone and then it will be set to zero.",
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
                        "note": "Refers to a schedule to specify unitary supply fan operating mode. Schedule values of 0 indicate cycling fan (auto) Schedule values of 1 indicate continuous fan (on) If this field is left blank, a schedule of always zero (cycling fan) will be used.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "supply_air_fan_placement": {
                        "type": "string",
                        "enum": [
                            "",
                            "BlowThrough",
                            "DrawThrough"
                        ],
                        "default": "BlowThrough",
                        "note": "Select fan placement as either blow through or draw through."
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
                            "None",
                            "VariableRefrigerantFlowDX"
                        ],
                        "default": "VariableRefrigerantFlowDX"
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
                    "heat_pump_heating_coil_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "None",
                            "VariableRefrigerantFlowDX"
                        ],
                        "default": "VariableRefrigerantFlowDX"
                    },
                    "heat_pump_heating_coil_availability_schedule_name": {
                        "type": "string",
                        "note": "If blank, always on",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "heat_pump_heating_coil_gross_rated_capacity": {
                        "note": "Capacity excluding supply air fan heat Rating point outdoor dry-bulb temp 8.33 C, outdoor wet-bulb temp 6.11 C Rating point heating coil entering air dry-bulb 21.11 C, coil entering wet-bulb 15.55 C",
                        "units": "W",
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
                    "zone_terminal_unit_on_parasitic_electric_energy_use": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "zone_terminal_unit_off_parasitic_electric_energy_use": {
                        "type": "number",
                        "units": "W",
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
                    }
                },
                "required": [
                    "zone_name",
                    "template_vrf_system_name"
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
                "template_vrf_system_name": {
                    "field_name": "Template VRF System Name",
                    "field_type": "a"
                },
                "template_thermostat_name": {
                    "field_name": "Template Thermostat Name",
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
                "rated_total_heating_capacity_sizing_ratio": {
                    "field_name": "Rated Total Heating Capacity Sizing Ratio",
                    "field_type": "n"
                },
                "cooling_supply_air_flow_rate": {
                    "field_name": "Cooling Supply Air Flow Rate",
                    "field_type": "n"
                },
                "no_cooling_supply_air_flow_rate": {
                    "field_name": "No Cooling Supply Air Flow Rate",
                    "field_type": "n"
                },
                "heating_supply_air_flow_rate": {
                    "field_name": "Heating Supply Air Flow Rate",
                    "field_type": "n"
                },
                "no_heating_supply_air_flow_rate": {
                    "field_name": "No Heating Supply Air Flow Rate",
                    "field_type": "n"
                },
                "cooling_outdoor_air_flow_rate": {
                    "field_name": "Cooling Outdoor Air Flow Rate",
                    "field_type": "n"
                },
                "heating_outdoor_air_flow_rate": {
                    "field_name": "Heating Outdoor Air Flow Rate",
                    "field_type": "n"
                },
                "no_load_outdoor_air_flow_rate": {
                    "field_name": "No Load Outdoor Air Flow Rate",
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
                "design_specification_outdoor_air_object_name": {
                    "field_name": "Design Specification Outdoor Air Object Name",
                    "field_type": "a"
                },
                "design_specification_zone_air_distribution_object_name": {
                    "field_name": "Design Specification Zone Air Distribution Object Name",
                    "field_type": "a"
                },
                "system_availability_schedule_name": {
                    "field_name": "System Availability Schedule Name",
                    "field_type": "a"
                },
                "supply_fan_operating_mode_schedule_name": {
                    "field_name": "Supply Fan Operating Mode Schedule Name",
                    "field_type": "a"
                },
                "supply_air_fan_placement": {
                    "field_name": "Supply Air Fan placement",
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
                "heat_pump_heating_coil_type": {
                    "field_name": "Heat Pump Heating Coil Type",
                    "field_type": "a"
                },
                "heat_pump_heating_coil_availability_schedule_name": {
                    "field_name": "Heat Pump Heating Coil Availability Schedule Name",
                    "field_type": "a"
                },
                "heat_pump_heating_coil_gross_rated_capacity": {
                    "field_name": "Heat Pump Heating Coil Gross Rated Capacity",
                    "field_type": "n"
                },
                "zone_terminal_unit_on_parasitic_electric_energy_use": {
                    "field_name": "Zone Terminal Unit On Parasitic Electric Energy Use",
                    "field_type": "n"
                },
                "zone_terminal_unit_off_parasitic_electric_energy_use": {
                    "field_name": "Zone Terminal Unit Off Parasitic Electric Energy Use",
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
                }
            },
            "fields": [
                "zone_name",
                "template_vrf_system_name",
                "template_thermostat_name",
                "zone_heating_sizing_factor",
                "zone_cooling_sizing_factor",
                "rated_total_heating_capacity_sizing_ratio",
                "cooling_supply_air_flow_rate",
                "no_cooling_supply_air_flow_rate",
                "heating_supply_air_flow_rate",
                "no_heating_supply_air_flow_rate",
                "cooling_outdoor_air_flow_rate",
                "heating_outdoor_air_flow_rate",
                "no_load_outdoor_air_flow_rate",
                "outdoor_air_method",
                "outdoor_air_flow_rate_per_person",
                "outdoor_air_flow_rate_per_zone_floor_area",
                "outdoor_air_flow_rate_per_zone",
                "design_specification_outdoor_air_object_name",
                "design_specification_zone_air_distribution_object_name",
                "system_availability_schedule_name",
                "supply_fan_operating_mode_schedule_name",
                "supply_air_fan_placement",
                "supply_fan_total_efficiency",
                "supply_fan_delta_pressure",
                "supply_fan_motor_efficiency",
                "cooling_coil_type",
                "cooling_coil_availability_schedule_name",
                "cooling_coil_gross_rated_total_capacity",
                "cooling_coil_gross_rated_sensible_heat_ratio",
                "heat_pump_heating_coil_type",
                "heat_pump_heating_coil_availability_schedule_name",
                "heat_pump_heating_coil_gross_rated_capacity",
                "zone_terminal_unit_on_parasitic_electric_energy_use",
                "zone_terminal_unit_off_parasitic_electric_energy_use",
                "dedicated_outdoor_air_system_name",
                "zone_cooling_design_supply_air_temperature_input_method",
                "zone_cooling_design_supply_air_temperature",
                "zone_cooling_design_supply_air_temperature_difference",
                "zone_heating_design_supply_air_temperature_input_method",
                "zone_heating_design_supply_air_temperature",
                "zone_heating_design_supply_air_temperature_difference",
                "baseboard_heating_type",
                "baseboard_heating_availability_schedule_name",
                "baseboard_heating_capacity"
            ],
            "alphas": {
                "fields": [
                    "zone_name",
                    "template_vrf_system_name",
                    "template_thermostat_name",
                    "outdoor_air_method",
                    "design_specification_outdoor_air_object_name",
                    "design_specification_zone_air_distribution_object_name",
                    "system_availability_schedule_name",
                    "supply_fan_operating_mode_schedule_name",
                    "supply_air_fan_placement",
                    "cooling_coil_type",
                    "cooling_coil_availability_schedule_name",
                    "heat_pump_heating_coil_type",
                    "heat_pump_heating_coil_availability_schedule_name",
                    "dedicated_outdoor_air_system_name",
                    "zone_cooling_design_supply_air_temperature_input_method",
                    "zone_heating_design_supply_air_temperature_input_method",
                    "baseboard_heating_type",
                    "baseboard_heating_availability_schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "zone_heating_sizing_factor",
                    "zone_cooling_sizing_factor",
                    "rated_total_heating_capacity_sizing_ratio",
                    "cooling_supply_air_flow_rate",
                    "no_cooling_supply_air_flow_rate",
                    "heating_supply_air_flow_rate",
                    "no_heating_supply_air_flow_rate",
                    "cooling_outdoor_air_flow_rate",
                    "heating_outdoor_air_flow_rate",
                    "no_load_outdoor_air_flow_rate",
                    "outdoor_air_flow_rate_per_person",
                    "outdoor_air_flow_rate_per_zone_floor_area",
                    "outdoor_air_flow_rate_per_zone",
                    "supply_fan_total_efficiency",
                    "supply_fan_delta_pressure",
                    "supply_fan_motor_efficiency",
                    "cooling_coil_gross_rated_total_capacity",
                    "cooling_coil_gross_rated_sensible_heat_ratio",
                    "heat_pump_heating_coil_gross_rated_capacity",
                    "zone_terminal_unit_on_parasitic_electric_energy_use",
                    "zone_terminal_unit_off_parasitic_electric_energy_use",
                    "zone_cooling_design_supply_air_temperature",
                    "zone_cooling_design_supply_air_temperature_difference",
                    "zone_heating_design_supply_air_temperature",
                    "zone_heating_design_supply_air_temperature_difference",
                    "baseboard_heating_capacity"
                ]
            }
        },
        "type": "object",
        "memo": "Zone terminal unit with variable refrigerant flow (VRF) DX cooling and heating coils (air-to-air or water-to-air heat pump). The VRF terminal units are served by an HVACTemplate:System:VRF system.",
        "min_fields": 44.0
    }
}
```
