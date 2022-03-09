```
{
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
                "air_inlet_node_name": {
                    "type": "string"
                },
                "air_outlet_node_name": {
                    "type": "string"
                },
                "supply_air_fan_object_type": {
                    "type": "string",
                    "enum": [
                        "Fan:ConstantVolume",
                        "Fan:OnOff",
                        "Fan:SystemModel",
                        "Fan:VariableVolume"
                    ],
                    "note": "Allowable fan types are Fan:ConstantVolume, Fan:OnOff, Fan:VariableVolume and Fan:SystemModel"
                },
                "supply_air_fan_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "FansCVandOnOffandVAV",
                        "FansSystemModel"
                    ]
                },
                "maximum_supply_air_flow_rate": {
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
                "supply_air_fan_operating_mode_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Enter the name of a schedule that controls fan operation. Schedule name values of 0 denote cycling fan operation (fan cycles with the heating coil). Schedule values greater than 0 denote constant fan operation (fan runs continually regardless of coil operation). The fan operating mode defaults to cycling fan operation if this input field is left blank."
                },
                "supply_air_fan_operation_during_no_heating": {
                    "type": "string",
                    "enum": [
                        "No",
                        "Yes"
                    ],
                    "note": "This choice field allows the user to define how the unit heater will operate under \"no heating load\" or cooling conditions. If the \"No\" is selected, then the fan will not run unless there is a heating load. If the fan does not run, this effectively shuts the unit heater system off when there is no heating load. If the \"Yes\" is selected, the unit heater is available and has a ConstantVolume fan, or has an OnOff fan with \"Supply Air Fan Operating Mode Schedule\" value greater than zero, then the fan will always run regardless of the zone load."
                },
                "maximum_hot_water_or_steam_flow_rate": {
                    "note": "Not used when heating coil is gas or electric",
                    "units": "m3/s",
                    "ip-units": "gal/min",
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
                "minimum_hot_water_or_steam_flow_rate": {
                    "type": "number",
                    "note": "Not used when heating coil is gas or electric",
                    "units": "m3/s",
                    "minimum": 0.0,
                    "default": 0.0,
                    "ip-units": "gal/min"
                },
                "heating_convergence_tolerance": {
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
                "supply_air_fan_object_type",
                "supply_air_fan_name",
                "maximum_supply_air_flow_rate",
                "heating_coil_object_type",
                "heating_coil_name",
                "supply_air_fan_operation_during_no_heating"
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
            "air_inlet_node_name": {
                "field_name": "Air Inlet Node Name",
                "field_type": "a"
            },
            "air_outlet_node_name": {
                "field_name": "Air Outlet Node Name",
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
            "maximum_supply_air_flow_rate": {
                "field_name": "Maximum Supply Air Flow Rate",
                "field_type": "n"
            },
            "heating_coil_object_type": {
                "field_name": "Heating Coil Object Type",
                "field_type": "a"
            },
            "heating_coil_name": {
                "field_name": "Heating Coil Name",
                "field_type": "a"
            },
            "supply_air_fan_operating_mode_schedule_name": {
                "field_name": "Supply Air Fan Operating Mode Schedule Name",
                "field_type": "a"
            },
            "supply_air_fan_operation_during_no_heating": {
                "field_name": "Supply Air Fan Operation During No Heating",
                "field_type": "a"
            },
            "maximum_hot_water_or_steam_flow_rate": {
                "field_name": "Maximum Hot Water or Steam Flow Rate",
                "field_type": "n"
            },
            "minimum_hot_water_or_steam_flow_rate": {
                "field_name": "Minimum Hot Water or Steam Flow Rate",
                "field_type": "n"
            },
            "heating_convergence_tolerance": {
                "field_name": "Heating Convergence Tolerance",
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
            "air_inlet_node_name",
            "air_outlet_node_name",
            "supply_air_fan_object_type",
            "supply_air_fan_name",
            "maximum_supply_air_flow_rate",
            "heating_coil_object_type",
            "heating_coil_name",
            "supply_air_fan_operating_mode_schedule_name",
            "supply_air_fan_operation_during_no_heating",
            "maximum_hot_water_or_steam_flow_rate",
            "minimum_hot_water_or_steam_flow_rate",
            "heating_convergence_tolerance",
            "availability_manager_list_name",
            "design_specification_zonehvac_sizing_object_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "supply_air_fan_object_type",
                "supply_air_fan_name",
                "heating_coil_object_type",
                "heating_coil_name",
                "supply_air_fan_operating_mode_schedule_name",
                "supply_air_fan_operation_during_no_heating",
                "availability_manager_list_name",
                "design_specification_zonehvac_sizing_object_name"
            ]
        },
        "numerics": {
            "fields": [
                "maximum_supply_air_flow_rate",
                "maximum_hot_water_or_steam_flow_rate",
                "minimum_hot_water_or_steam_flow_rate",
                "heating_convergence_tolerance"
            ]
        }
    },
    "type": "object",
    "memo": "Unit heater. Forced-convection heating-only unit with supply fan, heating coil (gas, electric, hot water, or steam) and fixed-position outdoor air mixer.",
    "min_fields": 11.0
}
```
