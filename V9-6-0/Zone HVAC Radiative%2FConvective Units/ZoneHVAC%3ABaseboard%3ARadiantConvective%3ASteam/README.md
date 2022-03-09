```
{
    "ZoneHVAC:Baseboard:RadiantConvective:Steam": {
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
                    "inlet_node_name": {
                        "type": "string"
                    },
                    "outlet_node_name": {
                        "type": "string"
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
                    "degree_of_subcooling": {
                        "type": "number",
                        "minimum": 1.0,
                        "default": 5.0,
                        "units": "deltaC"
                    },
                    "maximum_steam_flow_rate": {
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
                    "surface_fractions": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "surface_name": {
                                    "type": "string",
                                    "note": "Radiant energy may be distributed to specific surfaces",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "AllHeatTranSurfNames"
                                    ]
                                },
                                "fraction_of_radiant_energy_to_surface": {
                                    "type": "number",
                                    "minimum": 0.0,
                                    "maximum": 1.0
                                }
                            },
                            "type": "object"
                        }
                    }
                },
                "required": [
                    "inlet_node_name",
                    "outlet_node_name",
                    "maximum_steam_flow_rate"
                ]
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
                "inlet_node_name": {
                    "field_name": "Inlet Node Name",
                    "field_type": "a"
                },
                "outlet_node_name": {
                    "field_name": "Outlet Node Name",
                    "field_type": "a"
                },
                "heating_design_capacity": {
                    "field_name": "Heating Design Capacity",
                    "field_type": "n"
                },
                "degree_of_subcooling": {
                    "field_name": "Degree of SubCooling",
                    "field_type": "n"
                },
                "maximum_steam_flow_rate": {
                    "field_name": "Maximum Steam Flow Rate",
                    "field_type": "n"
                },
                "surface_name": {
                    "field_name": "Surface Name",
                    "field_type": "a"
                },
                "fraction_of_radiant_energy_to_surface": {
                    "field_name": "Fraction of Radiant Energy to Surface",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "design_object",
                "availability_schedule_name",
                "inlet_node_name",
                "outlet_node_name",
                "heating_design_capacity",
                "degree_of_subcooling",
                "maximum_steam_flow_rate"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "design_object",
                    "availability_schedule_name",
                    "inlet_node_name",
                    "outlet_node_name"
                ],
                "extensions": [
                    "surface_name"
                ]
            },
            "numerics": {
                "fields": [
                    "heating_design_capacity",
                    "degree_of_subcooling",
                    "maximum_steam_flow_rate"
                ],
                "extensions": [
                    "fraction_of_radiant_energy_to_surface"
                ]
            },
            "extensibles": [
                "surface_name",
                "fraction_of_radiant_energy_to_surface"
            ],
            "extension": "surface_fractions"
        },
        "type": "object",
        "memo": "The number of surfaces can be expanded beyond 100, if necessary, by adding more groups to the end of the list.",
        "min_fields": 8.0,
        "extensible_size": 2.0
    }
}
```
