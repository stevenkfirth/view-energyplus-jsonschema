```
{
    "ZoneHVAC:VentilatedSlab": {
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
                    "zone_name": {
                        "type": "string",
                        "note": "(name of zone system is serving)",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "surface_name_or_radiant_surface_group_name": {
                        "type": "string",
                        "note": "(name of surface system is embedded in) or list of surfaces",
                        "data_type": "object_list",
                        "object_list": [
                            "RadiantSurfaceNames",
                            "VentSlabGroupNames"
                        ]
                    },
                    "maximum_air_flow_rate": {
                        "units": "m3/s",
                        "anyOf": [
                            {
                                "type": "number",
                                "exclusiveMinimum": 0.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "outdoor_air_control_type": {
                        "type": "string",
                        "enum": [
                            "FixedAmount",
                            "FixedTemperature",
                            "VariablePercent"
                        ]
                    },
                    "minimum_outdoor_air_flow_rate": {
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
                    "minimum_outdoor_air_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "maximum_outdoor_air_flow_rate": {
                        "units": "m3/s",
                        "note": "schedule values multiply the minimum outdoor air flow rate",
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
                    "maximum_outdoor_air_fraction_or_temperature_schedule_name": {
                        "type": "string",
                        "note": "Note that this depends on the control type as to whether schedule values are a fraction or temperature",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "system_configuration_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "SeriesSlabs",
                            "SlabAndZone",
                            "SlabOnly"
                        ],
                        "default": "SlabOnly"
                    },
                    "hollow_core_inside_diameter": {
                        "type": "number",
                        "units": "m",
                        "minimum": 0.0,
                        "default": 0.05,
                        "ip-units": "in"
                    },
                    "hollow_core_length": {
                        "type": "number",
                        "note": "(length of core cavity embedded in surface)",
                        "units": "m",
                        "minimum": 0.0
                    },
                    "number_of_cores": {
                        "type": "number",
                        "note": "flow will be divided evenly among the cores",
                        "minimum": 0.0
                    },
                    "temperature_control_type": {
                        "type": "string",
                        "note": "(temperature on which unit is controlled)",
                        "enum": [
                            "",
                            "MeanAirTemperature",
                            "MeanRadiantTemperature",
                            "OperativeTemperature",
                            "OutdoorDryBulbTemperature",
                            "OutdoorWetBulbTemperature",
                            "SurfaceTemperature",
                            "ZoneAirDewPointTemperature"
                        ],
                        "default": "OutdoorDryBulbTemperature"
                    },
                    "heating_high_air_temperature_schedule_name": {
                        "type": "string",
                        "note": "Air and control temperatures for heating work together to provide a linear function that determines the air temperature sent to the radiant system. The current control temperature (see A14) is compared to the high and low control temperatures at the current time. If the control temperature is above the high temperature, then the inlet air temperature is set to the low air temperature. If the control temperature is below the low temperature, then the inlet air temperature is set to the high air temperature. If the control temperature is between the high and low value, then the inlet air temperature is linearly interpolated between the low and high air temperature values.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "heating_low_air_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "heating_high_control_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "heating_low_control_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "cooling_high_air_temperature_schedule_name": {
                        "type": "string",
                        "note": "See note for heating high air temperature schedule above for interpretation information (or see the Input/Output Reference).",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "cooling_low_air_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "cooling_high_control_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "cooling_low_control_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "return_air_node_name": {
                        "type": "string",
                        "note": "This is the zone return air inlet to the ventilated slab system outdoor air mixer. This node is typically a zone exhaust node (do not connect to \"Zone Return Air Node\")."
                    },
                    "slab_in_node_name": {
                        "type": "string",
                        "note": "This is the node entering the slab or series of slabs after the fan and coil(s)."
                    },
                    "zone_supply_air_node_name": {
                        "type": "string",
                        "note": "This is the node name exiting the slab. This node is typically a zone inlet node. Leave blank when the system configuration is SlabOnly or SeriesSlabs."
                    },
                    "outdoor_air_node_name": {
                        "type": "string",
                        "note": "This node is the outdoor air inlet to the ventilated slab oa mixer. This node should also be specified in an OutdoorAir:Node or OutdoorAir:NodeList object."
                    },
                    "relief_air_node_name": {
                        "type": "string",
                        "note": "This node is the relief air node from the ventilated slab outdoor air mixer."
                    },
                    "outdoor_air_mixer_outlet_node_name": {
                        "type": "string",
                        "note": "This is the node name leaving the outdoor air mixer and entering the fan and coil(s)."
                    },
                    "fan_outlet_node_name": {
                        "type": "string",
                        "note": "This is the node name of the fan outlet."
                    },
                    "fan_name": {
                        "type": "string",
                        "note": "Allowable fan types are Fan:SystemModel and Fan:ConstantVolume",
                        "data_type": "object_list",
                        "object_list": [
                            "FansCV",
                            "FansSystemModel"
                        ]
                    },
                    "coil_option_type": {
                        "type": "string",
                        "enum": [
                            "Cooling",
                            "Heating",
                            "HeatingAndCooling",
                            "None"
                        ]
                    },
                    "heating_coil_object_type": {
                        "type": "string",
                        "enum": [
                            "Coil:Heating:Electric",
                            "Coil:Heating:Fuel",
                            "Coil:Heating:Steam",
                            "Coil:Heating:Water"
                        ]
                    },
                    "heating_coil_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "HeatingCoilName"
                        ]
                    },
                    "hot_water_or_steam_inlet_node_name": {
                        "type": "string"
                    },
                    "cooling_coil_object_type": {
                        "type": "string",
                        "enum": [
                            "Coil:Cooling:Water",
                            "Coil:Cooling:Water:DetailedGeometry",
                            "CoilSystem:Cooling:Water:HeatExchangerAssisted"
                        ]
                    },
                    "cooling_coil_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "CoolingCoilsWater"
                        ]
                    },
                    "cold_water_inlet_node_name": {
                        "type": "string"
                    },
                    "availability_manager_list_name": {
                        "type": "string",
                        "note": "Enter the name of an AvailabilityManagerAssignmentList object.",
                        "data_type": "object_list",
                        "object_list": [
                            "SystemAvailabilityManagerLists"
                        ]
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
                    "zone_name",
                    "maximum_air_flow_rate",
                    "outdoor_air_control_type",
                    "minimum_outdoor_air_flow_rate",
                    "minimum_outdoor_air_schedule_name",
                    "maximum_outdoor_air_flow_rate",
                    "maximum_outdoor_air_fraction_or_temperature_schedule_name",
                    "heating_high_air_temperature_schedule_name",
                    "heating_low_air_temperature_schedule_name",
                    "heating_high_control_temperature_schedule_name",
                    "heating_low_control_temperature_schedule_name",
                    "cooling_high_air_temperature_schedule_name",
                    "cooling_low_air_temperature_schedule_name",
                    "cooling_high_control_temperature_schedule_name",
                    "cooling_low_control_temperature_schedule_name",
                    "return_air_node_name",
                    "slab_in_node_name",
                    "outdoor_air_node_name",
                    "relief_air_node_name",
                    "outdoor_air_mixer_outlet_node_name",
                    "fan_outlet_node_name",
                    "fan_name",
                    "coil_option_type"
                ]
            }
        },
        "group": "Zone HVAC Radiative/Convective Units",
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
                "zone_name": {
                    "field_name": "Zone Name",
                    "field_type": "a"
                },
                "surface_name_or_radiant_surface_group_name": {
                    "field_name": "Surface Name or Radiant Surface Group Name",
                    "field_type": "a"
                },
                "maximum_air_flow_rate": {
                    "field_name": "Maximum Air Flow Rate",
                    "field_type": "n"
                },
                "outdoor_air_control_type": {
                    "field_name": "Outdoor Air Control Type",
                    "field_type": "a"
                },
                "minimum_outdoor_air_flow_rate": {
                    "field_name": "Minimum Outdoor Air Flow Rate",
                    "field_type": "n"
                },
                "minimum_outdoor_air_schedule_name": {
                    "field_name": "Minimum Outdoor Air Schedule Name",
                    "field_type": "a"
                },
                "maximum_outdoor_air_flow_rate": {
                    "field_name": "Maximum Outdoor Air Flow Rate",
                    "field_type": "n"
                },
                "maximum_outdoor_air_fraction_or_temperature_schedule_name": {
                    "field_name": "Maximum Outdoor Air Fraction or Temperature Schedule Name",
                    "field_type": "a"
                },
                "system_configuration_type": {
                    "field_name": "System Configuration Type",
                    "field_type": "a"
                },
                "hollow_core_inside_diameter": {
                    "field_name": "Hollow Core Inside Diameter",
                    "field_type": "n"
                },
                "hollow_core_length": {
                    "field_name": "Hollow Core Length",
                    "field_type": "n"
                },
                "number_of_cores": {
                    "field_name": "Number of Cores",
                    "field_type": "n"
                },
                "temperature_control_type": {
                    "field_name": "Temperature Control Type",
                    "field_type": "a"
                },
                "heating_high_air_temperature_schedule_name": {
                    "field_name": "Heating High Air Temperature Schedule Name",
                    "field_type": "a"
                },
                "heating_low_air_temperature_schedule_name": {
                    "field_name": "Heating Low Air Temperature Schedule Name",
                    "field_type": "a"
                },
                "heating_high_control_temperature_schedule_name": {
                    "field_name": "Heating High Control Temperature Schedule Name",
                    "field_type": "a"
                },
                "heating_low_control_temperature_schedule_name": {
                    "field_name": "Heating Low Control Temperature Schedule Name",
                    "field_type": "a"
                },
                "cooling_high_air_temperature_schedule_name": {
                    "field_name": "Cooling High Air Temperature Schedule Name",
                    "field_type": "a"
                },
                "cooling_low_air_temperature_schedule_name": {
                    "field_name": "Cooling Low Air Temperature Schedule Name",
                    "field_type": "a"
                },
                "cooling_high_control_temperature_schedule_name": {
                    "field_name": "Cooling High Control Temperature Schedule Name",
                    "field_type": "a"
                },
                "cooling_low_control_temperature_schedule_name": {
                    "field_name": "Cooling Low Control Temperature Schedule Name",
                    "field_type": "a"
                },
                "return_air_node_name": {
                    "field_name": "Return Air Node Name",
                    "field_type": "a"
                },
                "slab_in_node_name": {
                    "field_name": "Slab In Node Name",
                    "field_type": "a"
                },
                "zone_supply_air_node_name": {
                    "field_name": "Zone Supply Air Node Name",
                    "field_type": "a"
                },
                "outdoor_air_node_name": {
                    "field_name": "Outdoor Air Node Name",
                    "field_type": "a"
                },
                "relief_air_node_name": {
                    "field_name": "Relief Air Node Name",
                    "field_type": "a"
                },
                "outdoor_air_mixer_outlet_node_name": {
                    "field_name": "Outdoor Air Mixer Outlet Node Name",
                    "field_type": "a"
                },
                "fan_outlet_node_name": {
                    "field_name": "Fan Outlet Node Name",
                    "field_type": "a"
                },
                "fan_name": {
                    "field_name": "Fan Name",
                    "field_type": "a"
                },
                "coil_option_type": {
                    "field_name": "Coil Option Type",
                    "field_type": "a"
                },
                "heating_coil_object_type": {
                    "field_name": "Heating Coil Object Type",
                    "field_type": "a"
                },
                "heating_coil_name": {
                    "field_name": "Heating Coil Name",
                    "field_type": "a"
                },
                "hot_water_or_steam_inlet_node_name": {
                    "field_name": "Hot Water or Steam Inlet Node Name",
                    "field_type": "a"
                },
                "cooling_coil_object_type": {
                    "field_name": "Cooling Coil Object Type",
                    "field_type": "a"
                },
                "cooling_coil_name": {
                    "field_name": "Cooling Coil Name",
                    "field_type": "a"
                },
                "cold_water_inlet_node_name": {
                    "field_name": "Cold Water Inlet Node Name",
                    "field_type": "a"
                },
                "availability_manager_list_name": {
                    "field_name": "Availability Manager List Name",
                    "field_type": "a"
                },
                "design_specification_zonehvac_sizing_object_name": {
                    "field_name": "Design Specification ZoneHVAC Sizing Object Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "zone_name",
                "surface_name_or_radiant_surface_group_name",
                "maximum_air_flow_rate",
                "outdoor_air_control_type",
                "minimum_outdoor_air_flow_rate",
                "minimum_outdoor_air_schedule_name",
                "maximum_outdoor_air_flow_rate",
                "maximum_outdoor_air_fraction_or_temperature_schedule_name",
                "system_configuration_type",
                "hollow_core_inside_diameter",
                "hollow_core_length",
                "number_of_cores",
                "temperature_control_type",
                "heating_high_air_temperature_schedule_name",
                "heating_low_air_temperature_schedule_name",
                "heating_high_control_temperature_schedule_name",
                "heating_low_control_temperature_schedule_name",
                "cooling_high_air_temperature_schedule_name",
                "cooling_low_air_temperature_schedule_name",
                "cooling_high_control_temperature_schedule_name",
                "cooling_low_control_temperature_schedule_name",
                "return_air_node_name",
                "slab_in_node_name",
                "zone_supply_air_node_name",
                "outdoor_air_node_name",
                "relief_air_node_name",
                "outdoor_air_mixer_outlet_node_name",
                "fan_outlet_node_name",
                "fan_name",
                "coil_option_type",
                "heating_coil_object_type",
                "heating_coil_name",
                "hot_water_or_steam_inlet_node_name",
                "cooling_coil_object_type",
                "cooling_coil_name",
                "cold_water_inlet_node_name",
                "availability_manager_list_name",
                "design_specification_zonehvac_sizing_object_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "zone_name",
                    "surface_name_or_radiant_surface_group_name",
                    "outdoor_air_control_type",
                    "minimum_outdoor_air_schedule_name",
                    "maximum_outdoor_air_fraction_or_temperature_schedule_name",
                    "system_configuration_type",
                    "temperature_control_type",
                    "heating_high_air_temperature_schedule_name",
                    "heating_low_air_temperature_schedule_name",
                    "heating_high_control_temperature_schedule_name",
                    "heating_low_control_temperature_schedule_name",
                    "cooling_high_air_temperature_schedule_name",
                    "cooling_low_air_temperature_schedule_name",
                    "cooling_high_control_temperature_schedule_name",
                    "cooling_low_control_temperature_schedule_name",
                    "return_air_node_name",
                    "slab_in_node_name",
                    "zone_supply_air_node_name",
                    "outdoor_air_node_name",
                    "relief_air_node_name",
                    "outdoor_air_mixer_outlet_node_name",
                    "fan_outlet_node_name",
                    "fan_name",
                    "coil_option_type",
                    "heating_coil_object_type",
                    "heating_coil_name",
                    "hot_water_or_steam_inlet_node_name",
                    "cooling_coil_object_type",
                    "cooling_coil_name",
                    "cold_water_inlet_node_name",
                    "availability_manager_list_name",
                    "design_specification_zonehvac_sizing_object_name"
                ]
            },
            "numerics": {
                "fields": [
                    "maximum_air_flow_rate",
                    "minimum_outdoor_air_flow_rate",
                    "maximum_outdoor_air_flow_rate",
                    "hollow_core_inside_diameter",
                    "hollow_core_length",
                    "number_of_cores"
                ]
            }
        },
        "type": "object",
        "memo": "Ventilated slab system where outdoor air flows through hollow cores in a building surface (wall, ceiling, or floor).",
        "min_fields": 32.0
    }
}
```
