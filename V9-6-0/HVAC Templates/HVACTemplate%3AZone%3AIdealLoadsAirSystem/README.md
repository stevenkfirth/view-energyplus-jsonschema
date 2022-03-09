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
                "system_availability_schedule_name": {
                    "type": "string",
                    "note": "If blank, always on",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "maximum_heating_supply_air_temperature": {
                    "type": "number",
                    "units": "C",
                    "exclusiveMinimum": 0.0,
                    "exclusiveMaximum": 100.0,
                    "default": 50.0
                },
                "minimum_cooling_supply_air_temperature": {
                    "type": "number",
                    "units": "C",
                    "exclusiveMinimum": -100.0,
                    "exclusiveMaximum": 50.0,
                    "default": 13.0
                },
                "maximum_heating_supply_air_humidity_ratio": {
                    "type": "number",
                    "units": "kgWater/kgDryAir",
                    "exclusiveMinimum": 0.0,
                    "default": 0.0156
                },
                "minimum_cooling_supply_air_humidity_ratio": {
                    "type": "number",
                    "units": "kgWater/kgDryAir",
                    "exclusiveMinimum": 0.0,
                    "default": 0.0077
                },
                "heating_limit": {
                    "type": "string",
                    "enum": [
                        "",
                        "LimitCapacity",
                        "LimitFlowRate",
                        "LimitFlowRateAndCapacity",
                        "NoLimit"
                    ],
                    "default": "NoLimit"
                },
                "maximum_heating_air_flow_rate": {
                    "note": "This field is ignored if Heating Limit = NoLimit If this field is blank, there is no limit.",
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
                "maximum_sensible_heating_capacity": {
                    "note": "This field is ignored if Heating Limit = NoLimit If this field is blank, there is no limit.",
                    "units": "W",
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
                "cooling_limit": {
                    "type": "string",
                    "enum": [
                        "",
                        "LimitCapacity",
                        "LimitFlowRate",
                        "LimitFlowRateAndCapacity",
                        "NoLimit"
                    ],
                    "default": "NoLimit"
                },
                "maximum_cooling_air_flow_rate": {
                    "note": "This field is ignored if Cooling Limit = NoLimit This field is required if Outdoor Air Economizer Type is anything other than NoEconomizer.",
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
                "maximum_total_cooling_capacity": {
                    "note": "This field is ignored if Cooling Limit = NoLimit",
                    "units": "W",
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
                "heating_availability_schedule_name": {
                    "type": "string",
                    "note": "If blank, heating is always available.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "cooling_availability_schedule_name": {
                    "type": "string",
                    "note": "If blank, cooling is always available.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "dehumidification_control_type": {
                    "type": "string",
                    "note": "ConstantSensibleHeatRatio means that the ideal loads system will be controlled to meet the sensible cooling load, and the latent cooling rate will be computed using a constant sensible heat ratio (SHR) Humidistat means that there is a ZoneControl:Humidistat for this zone and the ideal loads system will attempt to satisfy the humidistat. None means that there is no dehumidification. ConstantSupplyHumidityRatio means that during cooling the supply air will always be at the Minimum Cooling Supply Humidity Ratio.",
                    "enum": [
                        "",
                        "ConstantSensibleHeatRatio",
                        "ConstantSupplyHumidityRatio",
                        "Humidistat",
                        "None"
                    ],
                    "default": "ConstantSensibleHeatRatio"
                },
                "cooling_sensible_heat_ratio": {
                    "type": "number",
                    "note": "This field is applicable only when Dehumidification Control Type is ConstantSensibleHeatRatio",
                    "units": "dimensionless",
                    "exclusiveMinimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.7
                },
                "dehumidification_setpoint": {
                    "type": "number",
                    "note": "Zone relative humidity setpoint in percent (0 to 100)",
                    "minimum": 0.0,
                    "maximum": 100.0,
                    "default": 60.0,
                    "units": "percent"
                },
                "humidification_control_type": {
                    "type": "string",
                    "note": "None means that there is no humidification. Humidistat means that there is a ZoneControl:Humidistat for this zone and the ideal loads system will attempt to satisfy the humidistat. ConstantSupplyHumidityRatio means that during heating the supply air will always be at the Maximum Heating Supply Humidity Ratio.",
                    "enum": [
                        "",
                        "ConstantSupplyHumidityRatio",
                        "Humidistat",
                        "None"
                    ],
                    "default": "None"
                },
                "humidification_setpoint": {
                    "type": "number",
                    "note": "Zone relative humidity setpoint in percent (0 to 100)",
                    "minimum": 0.0,
                    "maximum": 100.0,
                    "default": 30.0,
                    "units": "percent"
                },
                "outdoor_air_method": {
                    "type": "string",
                    "note": "None means there is no outdoor air and all related fields will be ignored Flow/Person, Flow/Zone, Flow/Area, Sum, and Maximum use the values in the next three fields: Outdoor Air Flow Rate per Person, Outdoor Air Flow Rate per Zone Floor Area, and Outdoor Air Flow Rate per Zone. DetailedSpecification ignores these three Outdoor Air Flow Rate fields and instead references design specification objects named in the fields Design Specification Outdoor Air Object Name and Design Specification Zone Air Distribution Object Name.",
                    "enum": [
                        "",
                        "DetailedSpecification",
                        "Flow/Area",
                        "Flow/Person",
                        "Flow/Zone",
                        "Maximum",
                        "None",
                        "Sum"
                    ],
                    "default": "None"
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
                    "data_type": "object_list",
                    "object_list": [
                        "DSOASpaceListNames",
                        "DesignSpecificationOutdoorAirNames"
                    ],
                    "note": "When the name of a DesignSpecification:OutdoorAir object is entered, the minimum outdoor air flow rate will be computed using these specifications. The outdoor air flow rate will also be affected by the next two fields. If this field is blank, there will be no outdoor air and the remaining fields will be ignored."
                },
                "demand_controlled_ventilation_type": {
                    "type": "string",
                    "note": "This field controls how the minimum outdoor air flow rate is calculated. None means that design occupancy will be used to compute the minimum outdoor air flow rate OccupancySchedule means that current occupancy level will be used. CO2Setpoint means that the design occupancy will be used to compute the minimum outdoor air flow rate and the outdoor air flow rate may be increased if necessary to maintain the indoor air carbon dioxide setpoint defined in a ZoneControl:ContaminantController object.",
                    "enum": [
                        "",
                        "CO2Setpoint",
                        "None",
                        "OccupancySchedule"
                    ],
                    "default": "None"
                },
                "outdoor_air_economizer_type": {
                    "type": "string",
                    "note": "DifferentialDryBulb and DifferentialEnthalpy will increase the outdoor air flow rate when there is a cooling load and the outdoor air temperature or enthalpy is below the zone exhaust air temperature or enthalpy.",
                    "enum": [
                        "",
                        "DifferentialDryBulb",
                        "DifferentialEnthalpy",
                        "NoEconomizer"
                    ],
                    "default": "NoEconomizer"
                },
                "heat_recovery_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "Enthalpy",
                        "None",
                        "Sensible"
                    ],
                    "default": "None"
                },
                "sensible_heat_recovery_effectiveness": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.7
                },
                "latent_heat_recovery_effectiveness": {
                    "type": "number",
                    "note": "Applicable only if Heat Recovery Type is Enthalpy.",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.65
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
            "system_availability_schedule_name": {
                "field_name": "System Availability Schedule Name",
                "field_type": "a"
            },
            "maximum_heating_supply_air_temperature": {
                "field_name": "Maximum Heating Supply Air Temperature",
                "field_type": "n"
            },
            "minimum_cooling_supply_air_temperature": {
                "field_name": "Minimum Cooling Supply Air Temperature",
                "field_type": "n"
            },
            "maximum_heating_supply_air_humidity_ratio": {
                "field_name": "Maximum Heating Supply Air Humidity Ratio",
                "field_type": "n"
            },
            "minimum_cooling_supply_air_humidity_ratio": {
                "field_name": "Minimum Cooling Supply Air Humidity Ratio",
                "field_type": "n"
            },
            "heating_limit": {
                "field_name": "Heating Limit",
                "field_type": "a"
            },
            "maximum_heating_air_flow_rate": {
                "field_name": "Maximum Heating Air Flow Rate",
                "field_type": "n"
            },
            "maximum_sensible_heating_capacity": {
                "field_name": "Maximum Sensible Heating Capacity",
                "field_type": "n"
            },
            "cooling_limit": {
                "field_name": "Cooling Limit",
                "field_type": "a"
            },
            "maximum_cooling_air_flow_rate": {
                "field_name": "Maximum Cooling Air Flow Rate",
                "field_type": "n"
            },
            "maximum_total_cooling_capacity": {
                "field_name": "Maximum Total Cooling Capacity",
                "field_type": "n"
            },
            "heating_availability_schedule_name": {
                "field_name": "Heating Availability Schedule Name",
                "field_type": "a"
            },
            "cooling_availability_schedule_name": {
                "field_name": "Cooling Availability Schedule Name",
                "field_type": "a"
            },
            "dehumidification_control_type": {
                "field_name": "Dehumidification Control Type",
                "field_type": "a"
            },
            "cooling_sensible_heat_ratio": {
                "field_name": "Cooling Sensible Heat Ratio",
                "field_type": "n"
            },
            "dehumidification_setpoint": {
                "field_name": "Dehumidification Setpoint",
                "field_type": "n"
            },
            "humidification_control_type": {
                "field_name": "Humidification Control Type",
                "field_type": "a"
            },
            "humidification_setpoint": {
                "field_name": "Humidification Setpoint",
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
            "demand_controlled_ventilation_type": {
                "field_name": "Demand Controlled Ventilation Type",
                "field_type": "a"
            },
            "outdoor_air_economizer_type": {
                "field_name": "Outdoor Air Economizer Type",
                "field_type": "a"
            },
            "heat_recovery_type": {
                "field_name": "Heat Recovery Type",
                "field_type": "a"
            },
            "sensible_heat_recovery_effectiveness": {
                "field_name": "Sensible Heat Recovery Effectiveness",
                "field_type": "n"
            },
            "latent_heat_recovery_effectiveness": {
                "field_name": "Latent Heat Recovery Effectiveness",
                "field_type": "n"
            }
        },
        "fields": [
            "zone_name",
            "template_thermostat_name",
            "system_availability_schedule_name",
            "maximum_heating_supply_air_temperature",
            "minimum_cooling_supply_air_temperature",
            "maximum_heating_supply_air_humidity_ratio",
            "minimum_cooling_supply_air_humidity_ratio",
            "heating_limit",
            "maximum_heating_air_flow_rate",
            "maximum_sensible_heating_capacity",
            "cooling_limit",
            "maximum_cooling_air_flow_rate",
            "maximum_total_cooling_capacity",
            "heating_availability_schedule_name",
            "cooling_availability_schedule_name",
            "dehumidification_control_type",
            "cooling_sensible_heat_ratio",
            "dehumidification_setpoint",
            "humidification_control_type",
            "humidification_setpoint",
            "outdoor_air_method",
            "outdoor_air_flow_rate_per_person",
            "outdoor_air_flow_rate_per_zone_floor_area",
            "outdoor_air_flow_rate_per_zone",
            "design_specification_outdoor_air_object_name",
            "demand_controlled_ventilation_type",
            "outdoor_air_economizer_type",
            "heat_recovery_type",
            "sensible_heat_recovery_effectiveness",
            "latent_heat_recovery_effectiveness"
        ],
        "alphas": {
            "fields": [
                "zone_name",
                "template_thermostat_name",
                "system_availability_schedule_name",
                "heating_limit",
                "cooling_limit",
                "heating_availability_schedule_name",
                "cooling_availability_schedule_name",
                "dehumidification_control_type",
                "humidification_control_type",
                "outdoor_air_method",
                "design_specification_outdoor_air_object_name",
                "demand_controlled_ventilation_type",
                "outdoor_air_economizer_type",
                "heat_recovery_type"
            ]
        },
        "numerics": {
            "fields": [
                "maximum_heating_supply_air_temperature",
                "minimum_cooling_supply_air_temperature",
                "maximum_heating_supply_air_humidity_ratio",
                "minimum_cooling_supply_air_humidity_ratio",
                "maximum_heating_air_flow_rate",
                "maximum_sensible_heating_capacity",
                "maximum_cooling_air_flow_rate",
                "maximum_total_cooling_capacity",
                "cooling_sensible_heat_ratio",
                "dehumidification_setpoint",
                "humidification_setpoint",
                "outdoor_air_flow_rate_per_person",
                "outdoor_air_flow_rate_per_zone_floor_area",
                "outdoor_air_flow_rate_per_zone",
                "sensible_heat_recovery_effectiveness",
                "latent_heat_recovery_effectiveness"
            ]
        }
    },
    "type": "object",
    "memo": "Zone with ideal air system that meets heating or cooling loads",
    "min_fields": 26.0
}
```
