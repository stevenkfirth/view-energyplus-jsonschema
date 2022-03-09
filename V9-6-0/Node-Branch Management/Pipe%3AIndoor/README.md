```
{
    "Pipe:Indoor": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "construction_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ConstructionNames"
                        ]
                    },
                    "fluid_inlet_node_name": {
                        "type": "string"
                    },
                    "fluid_outlet_node_name": {
                        "type": "string"
                    },
                    "environment_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Schedule",
                            "Zone"
                        ],
                        "default": "Zone"
                    },
                    "ambient_temperature_zone_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "ambient_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "ambient_air_velocity_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "pipe_inside_diameter": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "ip-units": "in"
                    },
                    "pipe_length": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0
                    }
                },
                "required": [
                    "construction_name",
                    "fluid_inlet_node_name",
                    "fluid_outlet_node_name"
                ]
            }
        },
        "group": "Node-Branch Management",
        "name": {
            "type": "string",
            "is_required": true,
            "reference-class-name": [
                "validBranchEquipmentTypes"
            ],
            "reference": [
                "validBranchEquipmentNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "construction_name": {
                    "field_name": "Construction Name",
                    "field_type": "a"
                },
                "fluid_inlet_node_name": {
                    "field_name": "Fluid Inlet Node Name",
                    "field_type": "a"
                },
                "fluid_outlet_node_name": {
                    "field_name": "Fluid Outlet Node Name",
                    "field_type": "a"
                },
                "environment_type": {
                    "field_name": "Environment Type",
                    "field_type": "a"
                },
                "ambient_temperature_zone_name": {
                    "field_name": "Ambient Temperature Zone Name",
                    "field_type": "a"
                },
                "ambient_temperature_schedule_name": {
                    "field_name": "Ambient Temperature Schedule Name",
                    "field_type": "a"
                },
                "ambient_air_velocity_schedule_name": {
                    "field_name": "Ambient Air Velocity Schedule Name",
                    "field_type": "a"
                },
                "pipe_inside_diameter": {
                    "field_name": "Pipe Inside Diameter",
                    "field_type": "n"
                },
                "pipe_length": {
                    "field_name": "Pipe Length",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "construction_name",
                "fluid_inlet_node_name",
                "fluid_outlet_node_name",
                "environment_type",
                "ambient_temperature_zone_name",
                "ambient_temperature_schedule_name",
                "ambient_air_velocity_schedule_name",
                "pipe_inside_diameter",
                "pipe_length"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "construction_name",
                    "fluid_inlet_node_name",
                    "fluid_outlet_node_name",
                    "environment_type",
                    "ambient_temperature_zone_name",
                    "ambient_temperature_schedule_name",
                    "ambient_air_velocity_schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "pipe_inside_diameter",
                    "pipe_length"
                ]
            }
        },
        "type": "object",
        "memo": "Pipe model with transport delay and heat transfer to the environment."
    }
}
```
