```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "design_object": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "RadiantDesignObject"
                    ]
                },
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
                    "note": "Name of zone system is serving",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "surface_name_or_radiant_surface_group_name": {
                    "type": "string",
                    "note": "Identifies surfaces that radiant system is embedded in. For a system with multiple surfaces, enter the name of a ZoneHVAC:LowTemperatureRadiant:SurfaceGroup object.",
                    "data_type": "object_list",
                    "object_list": [
                        "RadiantGroupNames",
                        "RadiantSurfaceNames"
                    ]
                },
                "hydronic_tubing_length": {
                    "note": "(total length of pipe embedded in surface)",
                    "units": "m",
                    "default": "Autosize",
                    "anyOf": [
                        {
                            "type": "number",
                            "exclusiveMinimum": 0.0
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
                "heating_design_capacity": {
                    "units": "W",
                    "ip-units": "W",
                    "default": "Autosize",
                    "note": "Enter the design heating capacity. Required field when the heating design capacity method HeatingDesignCapacity.",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
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
                "maximum_hot_water_flow": {
                    "units": "m3/s",
                    "ip-units": "gal/min",
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
                "heating_water_inlet_node_name": {
                    "type": "string"
                },
                "heating_water_outlet_node_name": {
                    "type": "string"
                },
                "cooling_design_capacity": {
                    "units": "W",
                    "note": "Enter the design cooling capacity. Required field when the cooling design capacity method CoolingDesignCapacity.",
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
                "maximum_cold_water_flow": {
                    "units": "m3/s",
                    "ip-units": "gal/min",
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
                "cooling_water_inlet_node_name": {
                    "type": "string"
                },
                "cooling_water_outlet_node_name": {
                    "type": "string"
                },
                "number_of_circuits": {
                    "type": "string",
                    "enum": [
                        "",
                        "CalculateFromCircuitLength",
                        "OnePerSurface"
                    ],
                    "default": "OnePerSurface"
                },
                "circuit_length": {
                    "type": "number",
                    "units": "m",
                    "default": 106.7
                }
            }
        }
    },
    "group": "Zone HVAC Radiative/Convective Units",
    "name": {
        "type": "string",
        "is_required": true,
        "reference-class-name": [
            "validBranchEquipmentTypes"
        ],
        "reference": [
            "ZoneEquipmentNames",
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
            "design_object": {
                "field_name": "Design Object",
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
            "hydronic_tubing_length": {
                "field_name": "Hydronic Tubing Length",
                "field_type": "n"
            },
            "heating_design_capacity": {
                "field_name": "Heating Design Capacity",
                "field_type": "n"
            },
            "maximum_hot_water_flow": {
                "field_name": "Maximum Hot Water Flow",
                "field_type": "n"
            },
            "heating_water_inlet_node_name": {
                "field_name": "Heating Water Inlet Node Name",
                "field_type": "a"
            },
            "heating_water_outlet_node_name": {
                "field_name": "Heating Water Outlet Node Name",
                "field_type": "a"
            },
            "cooling_design_capacity": {
                "field_name": "Cooling Design Capacity",
                "field_type": "n"
            },
            "maximum_cold_water_flow": {
                "field_name": "Maximum Cold Water Flow",
                "field_type": "n"
            },
            "cooling_water_inlet_node_name": {
                "field_name": "Cooling Water Inlet Node Name",
                "field_type": "a"
            },
            "cooling_water_outlet_node_name": {
                "field_name": "Cooling Water Outlet Node Name",
                "field_type": "a"
            },
            "number_of_circuits": {
                "field_name": "Number of Circuits",
                "field_type": "a"
            },
            "circuit_length": {
                "field_name": "Circuit Length",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "design_object",
            "availability_schedule_name",
            "zone_name",
            "surface_name_or_radiant_surface_group_name",
            "hydronic_tubing_length",
            "heating_design_capacity",
            "maximum_hot_water_flow",
            "heating_water_inlet_node_name",
            "heating_water_outlet_node_name",
            "cooling_design_capacity",
            "maximum_cold_water_flow",
            "cooling_water_inlet_node_name",
            "cooling_water_outlet_node_name",
            "number_of_circuits",
            "circuit_length"
        ],
        "alphas": {
            "fields": [
                "name",
                "design_object",
                "availability_schedule_name",
                "zone_name",
                "surface_name_or_radiant_surface_group_name",
                "heating_water_inlet_node_name",
                "heating_water_outlet_node_name",
                "cooling_water_inlet_node_name",
                "cooling_water_outlet_node_name",
                "number_of_circuits"
            ]
        },
        "numerics": {
            "fields": [
                "hydronic_tubing_length",
                "heating_design_capacity",
                "maximum_hot_water_flow",
                "cooling_design_capacity",
                "maximum_cold_water_flow",
                "circuit_length"
            ]
        }
    },
    "type": "object",
    "memo": "Low temperature hydronic radiant heating and/or cooling system embedded in a building surface (wall, ceiling, or floor). Controlled by varying the hot or chilled water flow to the unit.",
    "min_fields": 16.0
}
```
