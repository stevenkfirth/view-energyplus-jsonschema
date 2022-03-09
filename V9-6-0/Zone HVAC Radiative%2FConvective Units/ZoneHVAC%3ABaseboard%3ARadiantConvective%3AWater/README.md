```
{
    "ZoneHVAC:Baseboard:RadiantConvective:Water": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "design_object": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BaseboardDesignObject"
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
                    "rated_average_water_temperature": {
                        "type": "number",
                        "note": "Rated average water temperature is the average of the inlet and outlet water temperatures at rated conditions.",
                        "maximum": 150.0,
                        "minimum": 20.0,
                        "units": "C",
                        "default": 87.78
                    },
                    "rated_water_mass_flow_rate": {
                        "type": "number",
                        "note": "Standard is I=B=R Rating document where all baseboards are rated at either 0.063 kg/s (1 gpm) or 0.252 kg/s (4 gpm). It is recommended that users find data for the baseboard heater that corresponds to performance at 0.063 kg/s unless the flow rate is expected to be above 0.252 kg/s. If the flow rate is expected to be above 0.252 kg/s, this field should be 0.252 kg/s.",
                        "maximum": 10.0,
                        "exclusiveMinimum": 0.0,
                        "units": "kg/s",
                        "default": 0.063
                    },
                    "heating_design_capacity": {
                        "units": "W",
                        "ip-units": "W",
                        "default": "Autosize",
                        "note": "Enter the design heating capacity. Required field when the heating design capacity method HeatingDesignCapacity. This input field is rated heating capacity. Users must multiply the actual finned length published in the literature to determine the rated capacity. Rated Capacity is for an inlet air dry-bulb temperature of 18.0C, the Rated Water Mass Flow Rate of 0.063kg/s or 0.252kg/s, and the Rated Average Water Temperature between 32.2C and 115.6C.",
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
                    "maximum_water_flow_rate": {
                        "units": "m3/s",
                        "ip-units": "gal/min",
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
                    "maximum_water_flow_rate"
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
                "rated_average_water_temperature": {
                    "field_name": "Rated Average Water Temperature",
                    "field_type": "n"
                },
                "rated_water_mass_flow_rate": {
                    "field_name": "Rated Water Mass Flow Rate",
                    "field_type": "n"
                },
                "heating_design_capacity": {
                    "field_name": "Heating Design Capacity",
                    "field_type": "n"
                },
                "maximum_water_flow_rate": {
                    "field_name": "Maximum Water Flow Rate",
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
                "rated_average_water_temperature",
                "rated_water_mass_flow_rate",
                "heating_design_capacity",
                "maximum_water_flow_rate"
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
                    "rated_average_water_temperature",
                    "rated_water_mass_flow_rate",
                    "heating_design_capacity",
                    "maximum_water_flow_rate"
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
        "memo": "The number of surfaces can be expanded beyond 100, if necessary, by adding more groups to the end of the list",
        "min_fields": 9.0,
        "extensible_size": 2.0
    }
}
```
