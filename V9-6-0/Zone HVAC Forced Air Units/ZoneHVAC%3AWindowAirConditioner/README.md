```
{
    "ZoneHVAC:WindowAirConditioner": {
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
                    "maximum_supply_air_flow_rate": {
                        "units": "m3/s",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "maximum_outdoor_air_flow_rate": {
                        "units": "m3/s",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "air_inlet_node_name": {
                        "type": "string"
                    },
                    "air_outlet_node_name": {
                        "type": "string"
                    },
                    "outdoor_air_mixer_object_type": {
                        "type": "string",
                        "enum": [
                            "OutdoorAir:Mixer"
                        ],
                        "note": "currently only one OutdoorAir:Mixer object type is available."
                    },
                    "outdoor_air_mixer_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "OutdoorAirMixers"
                        ]
                    },
                    "supply_air_fan_object_type": {
                        "type": "string",
                        "enum": [
                            "Fan:ConstantVolume",
                            "Fan:OnOff",
                            "Fan:SystemModel"
                        ],
                        "note": "Fan:ConstantVolume only works when continuous fan operation is used the entire simulation (all supply air fan operating mode schedule values are greater than 0). If any fan operating mode schedule values are 0 a Fan:SystemModel or Fan:OnOff object must be used."
                    },
                    "supply_air_fan_name": {
                        "type": "string",
                        "note": "Fan type Fan:ConstantVolume is used with continuous fan and fan type Fan:OnOff is used with cycling Fan.",
                        "data_type": "object_list",
                        "object_list": [
                            "FansCVandOnOff",
                            "FansSystemModel"
                        ]
                    },
                    "cooling_coil_object_type": {
                        "type": "string",
                        "enum": [
                            "Coil:Cooling:DX:SingleSpeed",
                            "Coil:Cooling:DX:VariableSpeed",
                            "CoilSystem:Cooling:DX:HeatExchangerAssisted"
                        ]
                    },
                    "dx_cooling_coil_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "CoolingCoilsDXSingleSpeed",
                            "CoolingCoilsDXVariableSpeed"
                        ]
                    },
                    "supply_air_fan_operating_mode_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Enter the name of a schedule that controls fan operation. Schedule Name values of 0 denote cycling fan operation (fan cycles with cooling coil). Schedule values greater than 0 denote constant fan operation (fan runs continually regardless of coil operation). The fan operating mode defaults to cycling fan operation if this field is left blank."
                    },
                    "fan_placement": {
                        "type": "string",
                        "enum": [
                            "BlowThrough",
                            "DrawThrough"
                        ]
                    },
                    "cooling_convergence_tolerance": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "default": 0.001
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
                    "maximum_supply_air_flow_rate",
                    "maximum_outdoor_air_flow_rate",
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "outdoor_air_mixer_object_type",
                    "outdoor_air_mixer_name",
                    "supply_air_fan_object_type",
                    "supply_air_fan_name",
                    "cooling_coil_object_type",
                    "dx_cooling_coil_name",
                    "fan_placement"
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
                "maximum_supply_air_flow_rate": {
                    "field_name": "Maximum Supply Air Flow Rate",
                    "field_type": "n"
                },
                "maximum_outdoor_air_flow_rate": {
                    "field_name": "Maximum Outdoor Air Flow Rate",
                    "field_type": "n"
                },
                "air_inlet_node_name": {
                    "field_name": "Air Inlet Node Name",
                    "field_type": "a"
                },
                "air_outlet_node_name": {
                    "field_name": "Air Outlet Node Name",
                    "field_type": "a"
                },
                "outdoor_air_mixer_object_type": {
                    "field_name": "Outdoor Air Mixer Object Type",
                    "field_type": "a"
                },
                "outdoor_air_mixer_name": {
                    "field_name": "Outdoor Air Mixer Name",
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
                "cooling_coil_object_type": {
                    "field_name": "Cooling Coil Object Type",
                    "field_type": "a"
                },
                "dx_cooling_coil_name": {
                    "field_name": "DX Cooling Coil Name",
                    "field_type": "a"
                },
                "supply_air_fan_operating_mode_schedule_name": {
                    "field_name": "Supply Air Fan Operating Mode Schedule Name",
                    "field_type": "a"
                },
                "fan_placement": {
                    "field_name": "Fan Placement",
                    "field_type": "a"
                },
                "cooling_convergence_tolerance": {
                    "field_name": "Cooling Convergence Tolerance",
                    "field_type": "n"
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
                "maximum_supply_air_flow_rate",
                "maximum_outdoor_air_flow_rate",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "outdoor_air_mixer_object_type",
                "outdoor_air_mixer_name",
                "supply_air_fan_object_type",
                "supply_air_fan_name",
                "cooling_coil_object_type",
                "dx_cooling_coil_name",
                "supply_air_fan_operating_mode_schedule_name",
                "fan_placement",
                "cooling_convergence_tolerance",
                "availability_manager_list_name",
                "design_specification_zonehvac_sizing_object_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "outdoor_air_mixer_object_type",
                    "outdoor_air_mixer_name",
                    "supply_air_fan_object_type",
                    "supply_air_fan_name",
                    "cooling_coil_object_type",
                    "dx_cooling_coil_name",
                    "supply_air_fan_operating_mode_schedule_name",
                    "fan_placement",
                    "availability_manager_list_name",
                    "design_specification_zonehvac_sizing_object_name"
                ]
            },
            "numerics": {
                "fields": [
                    "maximum_supply_air_flow_rate",
                    "maximum_outdoor_air_flow_rate",
                    "cooling_convergence_tolerance"
                ]
            }
        },
        "type": "object",
        "memo": "Window air conditioner. Forced-convection cooling-only unit with supply fan, direct expansion (DX) cooling coil, and fixed-position outdoor air mixer.",
        "min_fields": 15.0
    }
}
```
