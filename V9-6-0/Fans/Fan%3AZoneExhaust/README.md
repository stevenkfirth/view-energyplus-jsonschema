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
                "fan_total_efficiency": {
                    "type": "number",
                    "default": 0.6,
                    "exclusiveMinimum": 0.0,
                    "maximum": 1.0
                },
                "pressure_rise": {
                    "type": "number",
                    "units": "Pa",
                    "ip-units": "inH2O"
                },
                "maximum_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "minimum": 0.0
                },
                "air_inlet_node_name": {
                    "type": "string"
                },
                "air_outlet_node_name": {
                    "type": "string"
                },
                "end_use_subcategory": {
                    "type": "string",
                    "note": "Any text may be used here to categorize the end-uses in the ABUPS End Uses by Subcategory table.",
                    "retaincase": true,
                    "default": "General"
                },
                "flow_fraction_schedule_name": {
                    "type": "string",
                    "note": "If field is used, then when fan runs the exhausted air flow rate is controlled to be the scheduled fraction times the Maximum Flow Rate",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "system_availability_manager_coupling_mode": {
                    "type": "string",
                    "note": "Control if fan is to be interlocked with HVAC system Availability Managers or not.",
                    "enum": [
                        "",
                        "Coupled",
                        "Decoupled"
                    ],
                    "default": "Coupled"
                },
                "minimum_zone_temperature_limit_schedule_name": {
                    "type": "string",
                    "note": "If field is used, the exhaust fan will not run if the zone temperature is lower than this limit",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "balanced_exhaust_fraction_schedule_name": {
                    "type": "string",
                    "note": "Used to control fan's impact on flow at the return air node. Enter the portion of the exhaust that is balanced by simple airflows.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                }
            },
            "required": [
                "pressure_rise",
                "air_inlet_node_name",
                "air_outlet_node_name"
            ]
        }
    },
    "group": "Fans",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "FansZoneExhaust",
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
            "fan_total_efficiency": {
                "field_name": "Fan Total Efficiency",
                "field_type": "n"
            },
            "pressure_rise": {
                "field_name": "Pressure Rise",
                "field_type": "n"
            },
            "maximum_flow_rate": {
                "field_name": "Maximum Flow Rate",
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
            "end_use_subcategory": {
                "field_name": "End-Use Subcategory",
                "field_type": "a"
            },
            "flow_fraction_schedule_name": {
                "field_name": "Flow Fraction Schedule Name",
                "field_type": "a"
            },
            "system_availability_manager_coupling_mode": {
                "field_name": "System Availability Manager Coupling Mode",
                "field_type": "a"
            },
            "minimum_zone_temperature_limit_schedule_name": {
                "field_name": "Minimum Zone Temperature Limit Schedule Name",
                "field_type": "a"
            },
            "balanced_exhaust_fraction_schedule_name": {
                "field_name": "Balanced Exhaust Fraction Schedule Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "fan_total_efficiency",
            "pressure_rise",
            "maximum_flow_rate",
            "air_inlet_node_name",
            "air_outlet_node_name",
            "end_use_subcategory",
            "flow_fraction_schedule_name",
            "system_availability_manager_coupling_mode",
            "minimum_zone_temperature_limit_schedule_name",
            "balanced_exhaust_fraction_schedule_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "end_use_subcategory",
                "flow_fraction_schedule_name",
                "system_availability_manager_coupling_mode",
                "minimum_zone_temperature_limit_schedule_name",
                "balanced_exhaust_fraction_schedule_name"
            ]
        },
        "numerics": {
            "fields": [
                "fan_total_efficiency",
                "pressure_rise",
                "maximum_flow_rate"
            ]
        }
    },
    "type": "object",
    "memo": "Models a fan that exhausts air from a zone.",
    "min_fields": 7.0
}
```
