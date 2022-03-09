```
{
    "AirTerminal:SingleDuct:ConstantVolume:CooledBeam": {
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
                    "cooled_beam_type": {
                        "type": "string",
                        "enum": [
                            "Active",
                            "Passive"
                        ]
                    },
                    "supply_air_inlet_node_name": {
                        "type": "string"
                    },
                    "supply_air_outlet_node_name": {
                        "type": "string"
                    },
                    "chilled_water_inlet_node_name": {
                        "type": "string"
                    },
                    "chilled_water_outlet_node_name": {
                        "type": "string"
                    },
                    "supply_air_volumetric_flow_rate": {
                        "units": "m3/s",
                        "default": "Autosize",
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
                    "maximum_total_chilled_water_volumetric_flow_rate": {
                        "units": "m3/s",
                        "ip-units": "gal/min",
                        "default": "Autosize",
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
                    "number_of_beams": {
                        "note": "Number of individual beam units in the zone",
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
                    "beam_length": {
                        "note": "Length of an individual beam unit",
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
                    "design_inlet_water_temperature": {
                        "type": "number",
                        "units": "C",
                        "minimum": 0.0,
                        "default": 15.0
                    },
                    "design_outlet_water_temperature": {
                        "type": "number",
                        "units": "C",
                        "minimum": 0.0,
                        "default": 17.0
                    },
                    "coil_surface_area_per_coil_length": {
                        "type": "number",
                        "units": "m2/m",
                        "minimum": 0.0,
                        "default": 5.422
                    },
                    "model_parameter_a": {
                        "type": "number",
                        "minimum": 0.0,
                        "default": 15.3
                    },
                    "model_parameter_n1": {
                        "type": "number",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "model_parameter_n2": {
                        "type": "number",
                        "minimum": 0.0,
                        "default": 0.84
                    },
                    "model_parameter_n3": {
                        "type": "number",
                        "minimum": 0.0,
                        "default": 0.12
                    },
                    "model_parameter_a0": {
                        "type": "number",
                        "note": "Free area of the coil in plan view per unit beam length",
                        "units": "m2/m",
                        "minimum": 0.0,
                        "default": 0.171
                    },
                    "model_parameter_k1": {
                        "type": "number",
                        "minimum": 0.0,
                        "default": 0.0057
                    },
                    "model_parameter_n": {
                        "type": "number",
                        "minimum": 0.0,
                        "default": 0.4
                    },
                    "coefficient_of_induction_kin": {
                        "default": "Autocalculate",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.0,
                                "maximum": 4.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "",
                                    "Autocalculate"
                                ]
                            }
                        ]
                    },
                    "leaving_pipe_inside_diameter": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "default": 0.0145
                    }
                },
                "required": [
                    "cooled_beam_type",
                    "supply_air_inlet_node_name",
                    "supply_air_outlet_node_name",
                    "chilled_water_inlet_node_name",
                    "chilled_water_outlet_node_name"
                ]
            }
        },
        "group": "Zone HVAC Air Loop Terminal Units",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "AirTerminalUnitNames",
                "validBranchEquipmentNames"
            ],
            "reference-class-name": [
                "validBranchEquipmentTypes"
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
                "cooled_beam_type": {
                    "field_name": "Cooled Beam Type",
                    "field_type": "a"
                },
                "supply_air_inlet_node_name": {
                    "field_name": "Supply Air Inlet Node Name",
                    "field_type": "a"
                },
                "supply_air_outlet_node_name": {
                    "field_name": "Supply Air Outlet Node Name",
                    "field_type": "a"
                },
                "chilled_water_inlet_node_name": {
                    "field_name": "Chilled Water Inlet Node Name",
                    "field_type": "a"
                },
                "chilled_water_outlet_node_name": {
                    "field_name": "Chilled Water Outlet Node Name",
                    "field_type": "a"
                },
                "supply_air_volumetric_flow_rate": {
                    "field_name": "Supply Air Volumetric Flow Rate",
                    "field_type": "n"
                },
                "maximum_total_chilled_water_volumetric_flow_rate": {
                    "field_name": "Maximum Total Chilled Water Volumetric Flow Rate",
                    "field_type": "n"
                },
                "number_of_beams": {
                    "field_name": "Number of Beams",
                    "field_type": "n"
                },
                "beam_length": {
                    "field_name": "Beam Length",
                    "field_type": "n"
                },
                "design_inlet_water_temperature": {
                    "field_name": "Design Inlet Water Temperature",
                    "field_type": "n"
                },
                "design_outlet_water_temperature": {
                    "field_name": "Design Outlet Water Temperature",
                    "field_type": "n"
                },
                "coil_surface_area_per_coil_length": {
                    "field_name": "Coil Surface Area per Coil Length",
                    "field_type": "n"
                },
                "model_parameter_a": {
                    "field_name": "Model Parameter a",
                    "field_type": "n"
                },
                "model_parameter_n1": {
                    "field_name": "Model Parameter n1",
                    "field_type": "n"
                },
                "model_parameter_n2": {
                    "field_name": "Model Parameter n2",
                    "field_type": "n"
                },
                "model_parameter_n3": {
                    "field_name": "Model Parameter n3",
                    "field_type": "n"
                },
                "model_parameter_a0": {
                    "field_name": "Model Parameter a0",
                    "field_type": "n"
                },
                "model_parameter_k1": {
                    "field_name": "Model Parameter K1",
                    "field_type": "n"
                },
                "model_parameter_n": {
                    "field_name": "Model Parameter n",
                    "field_type": "n"
                },
                "coefficient_of_induction_kin": {
                    "field_name": "Coefficient of Induction Kin",
                    "field_type": "n"
                },
                "leaving_pipe_inside_diameter": {
                    "field_name": "Leaving Pipe Inside Diameter",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "cooled_beam_type",
                "supply_air_inlet_node_name",
                "supply_air_outlet_node_name",
                "chilled_water_inlet_node_name",
                "chilled_water_outlet_node_name",
                "supply_air_volumetric_flow_rate",
                "maximum_total_chilled_water_volumetric_flow_rate",
                "number_of_beams",
                "beam_length",
                "design_inlet_water_temperature",
                "design_outlet_water_temperature",
                "coil_surface_area_per_coil_length",
                "model_parameter_a",
                "model_parameter_n1",
                "model_parameter_n2",
                "model_parameter_n3",
                "model_parameter_a0",
                "model_parameter_k1",
                "model_parameter_n",
                "coefficient_of_induction_kin",
                "leaving_pipe_inside_diameter"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "cooled_beam_type",
                    "supply_air_inlet_node_name",
                    "supply_air_outlet_node_name",
                    "chilled_water_inlet_node_name",
                    "chilled_water_outlet_node_name"
                ]
            },
            "numerics": {
                "fields": [
                    "supply_air_volumetric_flow_rate",
                    "maximum_total_chilled_water_volumetric_flow_rate",
                    "number_of_beams",
                    "beam_length",
                    "design_inlet_water_temperature",
                    "design_outlet_water_temperature",
                    "coil_surface_area_per_coil_length",
                    "model_parameter_a",
                    "model_parameter_n1",
                    "model_parameter_n2",
                    "model_parameter_n3",
                    "model_parameter_a0",
                    "model_parameter_k1",
                    "model_parameter_n",
                    "coefficient_of_induction_kin",
                    "leaving_pipe_inside_diameter"
                ]
            }
        },
        "type": "object",
        "memo": "Central air system terminal unit, single duct, constant volume, with cooled beam (active or passive).",
        "min_fields": 23.0
    }
}
```
