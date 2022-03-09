```
{
    "ZoneHVAC:IdealLoadsAirSystem": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "availability_schedule_name": {
                        "type": "string",
                        "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "zone_supply_air_node_name": {
                        "type": "string",
                        "note": "Must match a zone air inlet node name."
                    },
                    "zone_exhaust_air_node_name": {
                        "type": "string",
                        "note": "Should match a zone air exhaust node name. This field is optional, but is required if this this object is used with other forced air equipment."
                    },
                    "system_inlet_air_node_name": {
                        "type": "string",
                        "note": "This field is only required when the Ideal Loads Air System is connected to an AirloopHVAC:ZoneReturnPlenum, otherwise leave this field blank. When connected to a plenum the return plenum Outlet Node Name (or Induced Air Outlet Node Name when connecting multiple ideal loads air sytems) is entered here. The two ideal loads air system node name fields described above, the Zone Supply Air Node Name and the Zone Exhaust Air Node Name must also be entered. The Zone Supply Air Node Name must match a zone inlet air node name for the zone where this Ideal Loads Air System is connected. The Zone Exhaust Air Node Name must match an inlet air node name of an AirloopHVAC:ReturnAirPlenum object."
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
                    "design_specification_outdoor_air_object_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DSOASpaceListNames",
                            "DesignSpecificationOutdoorAirNames"
                        ],
                        "note": "When the name of a DesignSpecification:OutdoorAir object is entered, the minimum outdoor air flow rate will be computed using these specifications. The outdoor air flow rate will also be affected by the next two fields. If this field is blank, there will be no outdoor air and the remaining fields will be ignored."
                    },
                    "outdoor_air_inlet_node_name": {
                        "type": "string",
                        "note": "This field is required if the system provides outdoor air Enter the name of an outdoor air node. This node name is also specified in an OutdoorAir:Node or OutdoorAir:NodeList object."
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
                    },
                    "design_specification_zonehvac_sizing_object_name": {
                        "type": "string",
                        "note": "Enter the name of a DesignSpecificationZoneHVACSizing object.",
                        "data_type": "object_list",
                        "object_list": [
                            "DesignSpecificationZoneHVACSizingName"
                        ]
                    }
                },
                "required": [
                    "zone_supply_air_node_name"
                ]
            }
        },
        "group": "Zone HVAC Forced Air Units",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "ZoneEquipmentNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "availability_schedule_name": {
                    "field_name": "Availability Schedule Name",
                    "field_type": "a"
                },
                "zone_supply_air_node_name": {
                    "field_name": "Zone Supply Air Node Name",
                    "field_type": "a"
                },
                "zone_exhaust_air_node_name": {
                    "field_name": "Zone Exhaust Air Node Name",
                    "field_type": "a"
                },
                "system_inlet_air_node_name": {
                    "field_name": "System Inlet Air Node Name",
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
                "humidification_control_type": {
                    "field_name": "Humidification Control Type",
                    "field_type": "a"
                },
                "design_specification_outdoor_air_object_name": {
                    "field_name": "Design Specification Outdoor Air Object Name",
                    "field_type": "a"
                },
                "outdoor_air_inlet_node_name": {
                    "field_name": "Outdoor Air Inlet Node Name",
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
                },
                "design_specification_zonehvac_sizing_object_name": {
                    "field_name": "Design Specification ZoneHVAC Sizing Object Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "zone_supply_air_node_name",
                "zone_exhaust_air_node_name",
                "system_inlet_air_node_name",
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
                "humidification_control_type",
                "design_specification_outdoor_air_object_name",
                "outdoor_air_inlet_node_name",
                "demand_controlled_ventilation_type",
                "outdoor_air_economizer_type",
                "heat_recovery_type",
                "sensible_heat_recovery_effectiveness",
                "latent_heat_recovery_effectiveness",
                "design_specification_zonehvac_sizing_object_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "zone_supply_air_node_name",
                    "zone_exhaust_air_node_name",
                    "system_inlet_air_node_name",
                    "heating_limit",
                    "cooling_limit",
                    "heating_availability_schedule_name",
                    "cooling_availability_schedule_name",
                    "dehumidification_control_type",
                    "humidification_control_type",
                    "design_specification_outdoor_air_object_name",
                    "outdoor_air_inlet_node_name",
                    "demand_controlled_ventilation_type",
                    "outdoor_air_economizer_type",
                    "heat_recovery_type",
                    "design_specification_zonehvac_sizing_object_name"
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
                    "sensible_heat_recovery_effectiveness",
                    "latent_heat_recovery_effectiveness"
                ]
            }
        },
        "type": "object",
        "memo": "Ideal system used to calculate loads without modeling a full HVAC system. All that is required for the ideal system are zone controls, zone equipment configurations, and the ideal loads system component. This component can be thought of as an ideal unit that mixes zone air with the specified amount of outdoor air and then adds or removes heat and moisture at 100% efficiency in order to meet the specified controls. Energy use is reported as DistrictHeating and DistrictCooling.",
        "min_fields": 27.0
    }
}
```
