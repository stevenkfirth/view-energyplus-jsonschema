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
                "zone_name": {
                    "type": "string",
                    "note": "(name of zone system is serving)",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "outdoor_air_flow_rate": {
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
                "outdoor_air_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "supply_fan_name": {
                    "type": "string",
                    "note": "Allowable fan types are Fan:SystemModel and Fan:ConstantVolume and Fan:VariableVolume",
                    "data_type": "object_list",
                    "object_list": [
                        "FansCVandVAV",
                        "FansSystemModel"
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
                "exhaust_fan_name": {
                    "type": "string",
                    "note": "Allowable fan types are Fan:SystemModel and Fan:ConstantVolume and Fan:VariableVolume Fan:VariableVolume",
                    "data_type": "object_list",
                    "object_list": [
                        "FansCVandVAV",
                        "FansSystemModel"
                    ]
                },
                "exhaust_air_flow_rate": {
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
                "exhaust_air_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "unit_control_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "NeutralControl",
                        "TemperatureControl"
                    ],
                    "default": "NeutralControl"
                },
                "high_air_control_temperature_schedule_name": {
                    "type": "string",
                    "note": "Air and control temperatures for cooling. If outdoor air temperature is above the high air control temperature, then the zone inlet air temperature is set to the high air control temperature. If the outdoor air is between high and low air control temperature, then there is no cooling/heating requirements.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "low_air_control_temperature_schedule_name": {
                    "type": "string",
                    "note": "Air and control temperatures for Heating. If outdoor air temperature is below the low air control temperature, then the zone inlet air temperature is set to the low air control temperature. If the outdoor air is between high and low air control temperature, then there is no cooling/heating requirements.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "outdoor_air_node_name": {
                    "type": "string"
                },
                "airoutlet_node_name": {
                    "type": "string"
                },
                "airinlet_node_name": {
                    "type": "string",
                    "note": "air leaves zone"
                },
                "supply_fanoutlet_node_name": {
                    "type": "string"
                },
                "outdoor_air_unit_list_name": {
                    "type": "string",
                    "note": "Enter the name of an ZoneHVAC:OutdoorAirUnit:EquipmentList object.",
                    "data_type": "object_list",
                    "object_list": [
                        "OutdoorAirUnitEquipmentLists"
                    ]
                },
                "availability_manager_list_name": {
                    "type": "string",
                    "note": "Enter the name of an AvailabilityManagerAssignmentList object.",
                    "data_type": "object_list",
                    "object_list": [
                        "SystemAvailabilityManagerLists"
                    ]
                }
            },
            "required": [
                "zone_name",
                "outdoor_air_flow_rate",
                "outdoor_air_schedule_name",
                "supply_fan_name",
                "outdoor_air_node_name",
                "airoutlet_node_name",
                "supply_fanoutlet_node_name",
                "outdoor_air_unit_list_name"
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
            "zone_name": {
                "field_name": "Zone Name",
                "field_type": "a"
            },
            "outdoor_air_flow_rate": {
                "field_name": "Outdoor Air Flow Rate",
                "field_type": "n"
            },
            "outdoor_air_schedule_name": {
                "field_name": "Outdoor Air Schedule Name",
                "field_type": "a"
            },
            "supply_fan_name": {
                "field_name": "Supply Fan Name",
                "field_type": "a"
            },
            "supply_fan_placement": {
                "field_name": "Supply Fan Placement",
                "field_type": "a"
            },
            "exhaust_fan_name": {
                "field_name": "Exhaust Fan Name",
                "field_type": "a"
            },
            "exhaust_air_flow_rate": {
                "field_name": "Exhaust Air Flow Rate",
                "field_type": "n"
            },
            "exhaust_air_schedule_name": {
                "field_name": "Exhaust Air Schedule Name",
                "field_type": "a"
            },
            "unit_control_type": {
                "field_name": "Unit Control Type",
                "field_type": "a"
            },
            "high_air_control_temperature_schedule_name": {
                "field_name": "High Air Control Temperature Schedule Name",
                "field_type": "a"
            },
            "low_air_control_temperature_schedule_name": {
                "field_name": "Low Air Control Temperature Schedule Name",
                "field_type": "a"
            },
            "outdoor_air_node_name": {
                "field_name": "Outdoor Air Node Name",
                "field_type": "a"
            },
            "airoutlet_node_name": {
                "field_name": "AirOutlet Node Name",
                "field_type": "a"
            },
            "airinlet_node_name": {
                "field_name": "AirInlet Node Name",
                "field_type": "a"
            },
            "supply_fanoutlet_node_name": {
                "field_name": "Supply FanOutlet Node Name",
                "field_type": "a"
            },
            "outdoor_air_unit_list_name": {
                "field_name": "Outdoor Air Unit List Name",
                "field_type": "a"
            },
            "availability_manager_list_name": {
                "field_name": "Availability Manager List Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "zone_name",
            "outdoor_air_flow_rate",
            "outdoor_air_schedule_name",
            "supply_fan_name",
            "supply_fan_placement",
            "exhaust_fan_name",
            "exhaust_air_flow_rate",
            "exhaust_air_schedule_name",
            "unit_control_type",
            "high_air_control_temperature_schedule_name",
            "low_air_control_temperature_schedule_name",
            "outdoor_air_node_name",
            "airoutlet_node_name",
            "airinlet_node_name",
            "supply_fanoutlet_node_name",
            "outdoor_air_unit_list_name",
            "availability_manager_list_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "zone_name",
                "outdoor_air_schedule_name",
                "supply_fan_name",
                "supply_fan_placement",
                "exhaust_fan_name",
                "exhaust_air_schedule_name",
                "unit_control_type",
                "high_air_control_temperature_schedule_name",
                "low_air_control_temperature_schedule_name",
                "outdoor_air_node_name",
                "airoutlet_node_name",
                "airinlet_node_name",
                "supply_fanoutlet_node_name",
                "outdoor_air_unit_list_name",
                "availability_manager_list_name"
            ]
        },
        "numerics": {
            "fields": [
                "outdoor_air_flow_rate",
                "exhaust_air_flow_rate"
            ]
        }
    },
    "type": "object",
    "memo": "The zone outdoor air unit models a single-zone dedicated outdoor air system (DOAS). Forced-convection 100% outdoor air unit with supply fan and optional equipment including exhaust fan, heating coil, cooling coil, and heat recovery.",
    "min_fields": 18.0
}
```
