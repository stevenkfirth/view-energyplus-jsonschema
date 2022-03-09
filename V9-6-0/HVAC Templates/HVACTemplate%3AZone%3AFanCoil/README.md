```
{
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
                "system_availability_schedule_name": {
                    "type": "string",
                    "note": "If blank, always on",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
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
                "supply_fan_motor_in_air_stream_fraction": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 1.0
                },
                "cooling_coil_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "ChilledWater",
                        "ChilledWaterDetailedFlatModel",
                        "HeatExchangerAssistedChilledWater"
                    ],
                    "default": "ChilledWater"
                },
                "cooling_coil_availability_schedule_name": {
                    "type": "string",
                    "note": "If blank, always on",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "cooling_coil_design_setpoint": {
                    "type": "number",
                    "note": "Used for sizing when Zone Cooling Design Supply Air Temperature Input Method = SupplyAirTemperature",
                    "default": 14.0,
                    "units": "C"
                },
                "heating_coil_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "Electric",
                        "HotWater"
                    ],
                    "default": "HotWater"
                },
                "heating_coil_availability_schedule_name": {
                    "type": "string",
                    "note": "If blank, always on",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "heating_coil_design_setpoint": {
                    "type": "number",
                    "note": "Used for sizing when Zone Heating Design Supply Air Temperature Input Method = SupplyAirTemperature",
                    "default": 50.0,
                    "units": "C"
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
                    "note": "SupplyAirTemperature = use the value from Cooling Coil Design Setpoint (above) TemperatureDifference = use the value from Zone Cooling Design Supply Air Temperature Difference",
                    "enum": [
                        "",
                        "SupplyAirTemperature",
                        "TemperatureDifference"
                    ],
                    "default": "SupplyAirTemperature"
                },
                "zone_cooling_design_supply_air_temperature_difference": {
                    "type": "number",
                    "units": "deltaC",
                    "default": 11.11,
                    "note": "Zone Cooling Design Supply Air Temperature is only used when Zone Cooling Design Supply Air Temperature Input Method = TemperatureDifference The absolute value of this field will be subtracted from the zone temperature at peak load to calculate the Zone Cooling Design Supply Air Temperature."
                },
                "zone_heating_design_supply_air_temperature_input_method": {
                    "type": "string",
                    "note": "SupplyAirTemperature = use the value from Heating Coil Design Setpoint (above) TemperatureDifference = use the value from Zone Heating Design Supply Air Temperature Difference",
                    "enum": [
                        "",
                        "SupplyAirTemperature",
                        "TemperatureDifference"
                    ],
                    "default": "SupplyAirTemperature"
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
                "capacity_control_method": {
                    "type": "string",
                    "note": "If this field is left blank, it will default to CyclingFan if a Dedicated Outdoor Air System is specified (see above), otherwise it will default to ConstantFanVariableFlow.",
                    "enum": [
                        "ASHRAE90VariableFan",
                        "ConstantFanVariableFlow",
                        "CyclingFan",
                        "MultiSpeedFan",
                        "VariableFanConstantFlow",
                        "VariableFanVariableFlow"
                    ]
                },
                "low_speed_supply_air_flow_ratio": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 0.33
                },
                "medium_speed_supply_air_flow_ratio": {
                    "type": "number",
                    "note": "Medium Speed Supply Air Flow Ratio should be greater than Low Speed Supply Air Flow Ratio",
                    "exclusiveMinimum": 0.0,
                    "default": 0.66
                },
                "outdoor_air_schedule_name": {
                    "type": "string",
                    "note": "Value of schedule multiplies maximum outdoor air flow rate This schedule is ignored if this zone is served by an HVACTemplate dedicated outdoor air system.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
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
            "system_availability_schedule_name": {
                "field_name": "System Availability Schedule Name",
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
            "supply_fan_motor_in_air_stream_fraction": {
                "field_name": "Supply Fan Motor in Air Stream Fraction",
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
            "cooling_coil_design_setpoint": {
                "field_name": "Cooling Coil Design Setpoint",
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
            "heating_coil_design_setpoint": {
                "field_name": "Heating Coil Design Setpoint",
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
            "zone_cooling_design_supply_air_temperature_difference": {
                "field_name": "Zone Cooling Design Supply Air Temperature Difference",
                "field_type": "n"
            },
            "zone_heating_design_supply_air_temperature_input_method": {
                "field_name": "Zone Heating Design Supply Air Temperature Input Method",
                "field_type": "a"
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
            "capacity_control_method": {
                "field_name": "Capacity Control Method",
                "field_type": "a"
            },
            "low_speed_supply_air_flow_ratio": {
                "field_name": "Low Speed Supply Air Flow Ratio",
                "field_type": "n"
            },
            "medium_speed_supply_air_flow_ratio": {
                "field_name": "Medium Speed Supply Air Flow Ratio",
                "field_type": "n"
            },
            "outdoor_air_schedule_name": {
                "field_name": "Outdoor Air Schedule Name",
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
            }
        },
        "fields": [
            "zone_name",
            "template_thermostat_name",
            "supply_air_maximum_flow_rate",
            "zone_heating_sizing_factor",
            "zone_cooling_sizing_factor",
            "outdoor_air_method",
            "outdoor_air_flow_rate_per_person",
            "outdoor_air_flow_rate_per_zone_floor_area",
            "outdoor_air_flow_rate_per_zone",
            "system_availability_schedule_name",
            "supply_fan_total_efficiency",
            "supply_fan_delta_pressure",
            "supply_fan_motor_efficiency",
            "supply_fan_motor_in_air_stream_fraction",
            "cooling_coil_type",
            "cooling_coil_availability_schedule_name",
            "cooling_coil_design_setpoint",
            "heating_coil_type",
            "heating_coil_availability_schedule_name",
            "heating_coil_design_setpoint",
            "dedicated_outdoor_air_system_name",
            "zone_cooling_design_supply_air_temperature_input_method",
            "zone_cooling_design_supply_air_temperature_difference",
            "zone_heating_design_supply_air_temperature_input_method",
            "zone_heating_design_supply_air_temperature_difference",
            "design_specification_outdoor_air_object_name",
            "design_specification_zone_air_distribution_object_name",
            "capacity_control_method",
            "low_speed_supply_air_flow_ratio",
            "medium_speed_supply_air_flow_ratio",
            "outdoor_air_schedule_name",
            "baseboard_heating_type",
            "baseboard_heating_availability_schedule_name",
            "baseboard_heating_capacity"
        ],
        "alphas": {
            "fields": [
                "zone_name",
                "template_thermostat_name",
                "outdoor_air_method",
                "system_availability_schedule_name",
                "cooling_coil_type",
                "cooling_coil_availability_schedule_name",
                "heating_coil_type",
                "heating_coil_availability_schedule_name",
                "dedicated_outdoor_air_system_name",
                "zone_cooling_design_supply_air_temperature_input_method",
                "zone_heating_design_supply_air_temperature_input_method",
                "design_specification_outdoor_air_object_name",
                "design_specification_zone_air_distribution_object_name",
                "capacity_control_method",
                "outdoor_air_schedule_name",
                "baseboard_heating_type",
                "baseboard_heating_availability_schedule_name"
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
                "supply_fan_total_efficiency",
                "supply_fan_delta_pressure",
                "supply_fan_motor_efficiency",
                "supply_fan_motor_in_air_stream_fraction",
                "cooling_coil_design_setpoint",
                "heating_coil_design_setpoint",
                "zone_cooling_design_supply_air_temperature_difference",
                "zone_heating_design_supply_air_temperature_difference",
                "low_speed_supply_air_flow_ratio",
                "medium_speed_supply_air_flow_ratio",
                "baseboard_heating_capacity"
            ]
        }
    },
    "type": "object",
    "memo": "4 pipe fan coil unit with optional outdoor air.",
    "min_fields": 34.0
}
```
