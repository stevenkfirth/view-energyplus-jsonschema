```
{
    "ZoneHVAC:EvaporativeCoolerUnit": {
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
                    "availability_manager_list_name": {
                        "type": "string",
                        "note": "Enter the name of an AvailabilityManagerAssignmentList object.",
                        "data_type": "object_list",
                        "object_list": [
                            "SystemAvailabilityManagerLists"
                        ]
                    },
                    "outdoor_air_inlet_node_name": {
                        "type": "string",
                        "note": "this is an outdoor air node"
                    },
                    "cooler_outlet_node_name": {
                        "type": "string",
                        "note": "this is a zone inlet node"
                    },
                    "zone_relief_air_node_name": {
                        "type": "string",
                        "note": "this is a zone exhaust node, optional if flow is being balanced elsewhere"
                    },
                    "supply_air_fan_object_type": {
                        "type": "string",
                        "enum": [
                            "Fan:ComponentModel",
                            "Fan:ConstantVolume",
                            "Fan:OnOff",
                            "Fan:SystemModel",
                            "Fan:VariableVolume"
                        ]
                    },
                    "supply_air_fan_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "Fans"
                        ]
                    },
                    "design_supply_air_flow_rate": {
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
                    "fan_placement": {
                        "type": "string",
                        "enum": [
                            "BlowThrough",
                            "DrawThrough"
                        ]
                    },
                    "cooler_unit_control_method": {
                        "type": "string",
                        "enum": [
                            "ZoneCoolingLoadOnOffCycling",
                            "ZoneCoolingLoadVariableSpeedFan",
                            "ZoneTemperatureDeadbandOnOffCycling"
                        ]
                    },
                    "throttling_range_temperature_difference": {
                        "type": "number",
                        "note": "used for ZoneTemperatureDeadbandOnOffCycling hystersis range for thermostatic control",
                        "units": "deltaC",
                        "default": 1.0,
                        "exclusiveMinimum": 0.0
                    },
                    "cooling_load_control_threshold_heat_transfer_rate": {
                        "type": "number",
                        "units": "W",
                        "default": 100.0,
                        "note": "Sign convention is that positive values indicate a cooling load",
                        "exclusiveMinimum": 0.0
                    },
                    "first_evaporative_cooler_object_type": {
                        "type": "string",
                        "enum": [
                            "EvaporativeCooler:Direct:CelDekPad",
                            "EvaporativeCooler:Direct:ResearchSpecial",
                            "EvaporativeCooler:Indirect:CelDekPad",
                            "EvaporativeCooler:Indirect:ResearchSpecial",
                            "EvaporativeCooler:Indirect:WetCoil"
                        ]
                    },
                    "first_evaporative_cooler_object_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "EvapCoolerNames"
                        ]
                    },
                    "second_evaporative_cooler_object_type": {
                        "type": "string",
                        "note": "optional, used for direct/indirect configurations second cooler must be immediately downstream of first cooler, if present",
                        "enum": [
                            "EvaporativeCooler:Direct:CelDekPad",
                            "EvaporativeCooler:Direct:ResearchSpecial",
                            "EvaporativeCooler:Indirect:CelDekPad",
                            "EvaporativeCooler:Indirect:ResearchSpecial",
                            "EvaporativeCooler:Indirect:WetCoil"
                        ]
                    },
                    "second_evaporative_cooler_name": {
                        "type": "string",
                        "note": "optional, used for direct/indirect configurations",
                        "data_type": "object_list",
                        "object_list": [
                            "EvapCoolerNames"
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
                    "outdoor_air_inlet_node_name",
                    "cooler_outlet_node_name",
                    "supply_air_fan_object_type",
                    "supply_air_fan_name",
                    "design_supply_air_flow_rate",
                    "fan_placement",
                    "cooler_unit_control_method",
                    "first_evaporative_cooler_object_type",
                    "first_evaporative_cooler_object_name"
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
                "availability_manager_list_name": {
                    "field_name": "Availability Manager List Name",
                    "field_type": "a"
                },
                "outdoor_air_inlet_node_name": {
                    "field_name": "Outdoor Air Inlet Node Name",
                    "field_type": "a"
                },
                "cooler_outlet_node_name": {
                    "field_name": "Cooler Outlet Node Name",
                    "field_type": "a"
                },
                "zone_relief_air_node_name": {
                    "field_name": "Zone Relief Air Node Name",
                    "field_type": "a"
                },
                "supply_air_fan_object_type": {
                    "field_name": "Supply Air Fan Object Type",
                    "field_type": "a"
                },
                "supply_air_fan_name": {
                    "field_name": "Supply Air Fan Name",
                    "field_type": "a"
                },
                "design_supply_air_flow_rate": {
                    "field_name": "Design Supply Air Flow Rate",
                    "field_type": "n"
                },
                "fan_placement": {
                    "field_name": "Fan Placement",
                    "field_type": "a"
                },
                "cooler_unit_control_method": {
                    "field_name": "Cooler Unit Control Method",
                    "field_type": "a"
                },
                "throttling_range_temperature_difference": {
                    "field_name": "Throttling Range Temperature Difference",
                    "field_type": "n"
                },
                "cooling_load_control_threshold_heat_transfer_rate": {
                    "field_name": "Cooling Load Control Threshold Heat Transfer Rate",
                    "field_type": "n"
                },
                "first_evaporative_cooler_object_type": {
                    "field_name": "First Evaporative Cooler Object Type",
                    "field_type": "a"
                },
                "first_evaporative_cooler_object_name": {
                    "field_name": "First Evaporative Cooler Object Name",
                    "field_type": "a"
                },
                "second_evaporative_cooler_object_type": {
                    "field_name": "Second Evaporative Cooler Object Type",
                    "field_type": "a"
                },
                "second_evaporative_cooler_name": {
                    "field_name": "Second Evaporative Cooler Name",
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
                "availability_manager_list_name",
                "outdoor_air_inlet_node_name",
                "cooler_outlet_node_name",
                "zone_relief_air_node_name",
                "supply_air_fan_object_type",
                "supply_air_fan_name",
                "design_supply_air_flow_rate",
                "fan_placement",
                "cooler_unit_control_method",
                "throttling_range_temperature_difference",
                "cooling_load_control_threshold_heat_transfer_rate",
                "first_evaporative_cooler_object_type",
                "first_evaporative_cooler_object_name",
                "second_evaporative_cooler_object_type",
                "second_evaporative_cooler_name",
                "design_specification_zonehvac_sizing_object_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "availability_manager_list_name",
                    "outdoor_air_inlet_node_name",
                    "cooler_outlet_node_name",
                    "zone_relief_air_node_name",
                    "supply_air_fan_object_type",
                    "supply_air_fan_name",
                    "fan_placement",
                    "cooler_unit_control_method",
                    "first_evaporative_cooler_object_type",
                    "first_evaporative_cooler_object_name",
                    "second_evaporative_cooler_object_type",
                    "second_evaporative_cooler_name",
                    "design_specification_zonehvac_sizing_object_name"
                ]
            },
            "numerics": {
                "fields": [
                    "design_supply_air_flow_rate",
                    "throttling_range_temperature_difference",
                    "cooling_load_control_threshold_heat_transfer_rate"
                ]
            }
        },
        "type": "object",
        "memo": "Zone evaporative cooler. Forced-convection cooling-only unit with supply fan, 100% outdoor air supply. Optional relief exhaust node",
        "min_fields": 15.0
    }
}
```
