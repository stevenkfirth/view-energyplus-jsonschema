```
{
    "GroundHeatExchanger:Slinky": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "inlet_node_name": {
                        "type": "string"
                    },
                    "outlet_node_name": {
                        "type": "string"
                    },
                    "design_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "ip-units": "gal/min",
                        "exclusiveMinimum": 0.0,
                        "default": 0.002
                    },
                    "soil_thermal_conductivity": {
                        "type": "number",
                        "units": "W/m-K",
                        "exclusiveMinimum": 0.0,
                        "default": 1.08
                    },
                    "soil_density": {
                        "type": "number",
                        "units": "kg/m3",
                        "exclusiveMinimum": 0.0,
                        "default": 962.0
                    },
                    "soil_specific_heat": {
                        "type": "number",
                        "units": "J/kg-K",
                        "exclusiveMinimum": 0.0,
                        "default": 2576.0
                    },
                    "pipe_thermal_conductivity": {
                        "type": "number",
                        "units": "W/m-K",
                        "exclusiveMinimum": 0.0,
                        "default": 0.4
                    },
                    "pipe_density": {
                        "type": "number",
                        "units": "kg/m3",
                        "exclusiveMinimum": 0.0,
                        "default": 641.0
                    },
                    "pipe_specific_heat": {
                        "type": "number",
                        "units": "J/kg-K",
                        "exclusiveMinimum": 0.0,
                        "default": 2405.0
                    },
                    "pipe_outer_diameter": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "ip-units": "in",
                        "default": 0.02667
                    },
                    "pipe_thickness": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "ip-units": "in",
                        "default": 0.002413
                    },
                    "heat_exchanger_configuration": {
                        "type": "string",
                        "note": "This is the orientation of the heat exchanger",
                        "enum": [
                            "Horizontal",
                            "Vertical"
                        ]
                    },
                    "coil_diameter": {
                        "type": "number",
                        "note": "This is the diameter of the heat exchanger coil",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "ip-units": "ft",
                        "default": 1.0
                    },
                    "coil_pitch": {
                        "type": "number",
                        "note": "This is the center-to-center distance between coils",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "ip-units": "ft",
                        "default": 0.2
                    },
                    "trench_depth": {
                        "type": "number",
                        "note": "This is the distance from the ground surface to the trench bottom",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "ip-units": "ft",
                        "default": 1.8
                    },
                    "trench_length": {
                        "type": "number",
                        "note": "This is the total length of a single trench This assumes the heat exchanger runs the full length of the trench",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "ip-units": "ft",
                        "default": 10.0
                    },
                    "number_of_trenches": {
                        "type": "number",
                        "note": "This is the number of parallel trenches that has a heat exchanger, one per trench",
                        "minimum": 1.0,
                        "default": 1.0
                    },
                    "horizontal_spacing_between_pipes": {
                        "type": "number",
                        "note": "This represents the average horizontal spacing between any two trenches for heat exchangers that have multiple trenches",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "ip-units": "ft",
                        "default": 2.0
                    },
                    "undisturbed_ground_temperature_model_type": {
                        "type": "string",
                        "enum": [
                            "Site:GroundTemperature:Undisturbed:FiniteDifference",
                            "Site:GroundTemperature:Undisturbed:KusudaAchenbach",
                            "Site:GroundTemperature:Undisturbed:Xing"
                        ]
                    },
                    "undisturbed_ground_temperature_model_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UndisturbedGroundTempModels"
                        ]
                    },
                    "maximum_length_of_simulation": {
                        "type": "number",
                        "units": "years"
                    }
                },
                "required": [
                    "inlet_node_name",
                    "outlet_node_name",
                    "undisturbed_ground_temperature_model_type",
                    "undisturbed_ground_temperature_model_name"
                ]
            }
        },
        "group": "Condenser Equipment and Heat Exchangers",
        "name": {
            "type": "string",
            "is_required": true,
            "reference-class-name": [
                "validBranchEquipmentTypes",
                "validCondenserEquipmentTypes",
                "validPlantEquipmentTypes"
            ],
            "reference": [
                "validBranchEquipmentNames",
                "validCondenserEquipmentNames",
                "validPlantEquipmentNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
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
                "design_flow_rate": {
                    "field_name": "Design Flow Rate",
                    "field_type": "n"
                },
                "soil_thermal_conductivity": {
                    "field_name": "Soil Thermal Conductivity",
                    "field_type": "n"
                },
                "soil_density": {
                    "field_name": "Soil Density",
                    "field_type": "n"
                },
                "soil_specific_heat": {
                    "field_name": "Soil Specific Heat",
                    "field_type": "n"
                },
                "pipe_thermal_conductivity": {
                    "field_name": "Pipe Thermal Conductivity",
                    "field_type": "n"
                },
                "pipe_density": {
                    "field_name": "Pipe Density",
                    "field_type": "n"
                },
                "pipe_specific_heat": {
                    "field_name": "Pipe Specific Heat",
                    "field_type": "n"
                },
                "pipe_outer_diameter": {
                    "field_name": "Pipe Outer Diameter",
                    "field_type": "n"
                },
                "pipe_thickness": {
                    "field_name": "Pipe Thickness",
                    "field_type": "n"
                },
                "heat_exchanger_configuration": {
                    "field_name": "Heat Exchanger Configuration",
                    "field_type": "a"
                },
                "coil_diameter": {
                    "field_name": "Coil Diameter",
                    "field_type": "n"
                },
                "coil_pitch": {
                    "field_name": "Coil Pitch",
                    "field_type": "n"
                },
                "trench_depth": {
                    "field_name": "Trench Depth",
                    "field_type": "n"
                },
                "trench_length": {
                    "field_name": "Trench Length",
                    "field_type": "n"
                },
                "number_of_trenches": {
                    "field_name": "Number of Trenches",
                    "field_type": "n"
                },
                "horizontal_spacing_between_pipes": {
                    "field_name": "Horizontal Spacing Between Pipes",
                    "field_type": "n"
                },
                "undisturbed_ground_temperature_model_type": {
                    "field_name": "Undisturbed Ground Temperature Model Type",
                    "field_type": "a"
                },
                "undisturbed_ground_temperature_model_name": {
                    "field_name": "Undisturbed Ground Temperature Model Name",
                    "field_type": "a"
                },
                "maximum_length_of_simulation": {
                    "field_name": "Maximum Length of Simulation",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "inlet_node_name",
                "outlet_node_name",
                "design_flow_rate",
                "soil_thermal_conductivity",
                "soil_density",
                "soil_specific_heat",
                "pipe_thermal_conductivity",
                "pipe_density",
                "pipe_specific_heat",
                "pipe_outer_diameter",
                "pipe_thickness",
                "heat_exchanger_configuration",
                "coil_diameter",
                "coil_pitch",
                "trench_depth",
                "trench_length",
                "number_of_trenches",
                "horizontal_spacing_between_pipes",
                "undisturbed_ground_temperature_model_type",
                "undisturbed_ground_temperature_model_name",
                "maximum_length_of_simulation"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "inlet_node_name",
                    "outlet_node_name",
                    "heat_exchanger_configuration",
                    "undisturbed_ground_temperature_model_type",
                    "undisturbed_ground_temperature_model_name"
                ]
            },
            "numerics": {
                "fields": [
                    "design_flow_rate",
                    "soil_thermal_conductivity",
                    "soil_density",
                    "soil_specific_heat",
                    "pipe_thermal_conductivity",
                    "pipe_density",
                    "pipe_specific_heat",
                    "pipe_outer_diameter",
                    "pipe_thickness",
                    "coil_diameter",
                    "coil_pitch",
                    "trench_depth",
                    "trench_length",
                    "number_of_trenches",
                    "horizontal_spacing_between_pipes",
                    "maximum_length_of_simulation"
                ]
            }
        },
        "type": "object",
        "memo": "This models a slinky horizontal heat exchanger placed in a series of trenches The model uses the model developed by: Xiong, Z., D.E. Fisher, and J.D. Spitler. 2015. Development and Validation of a Slinky Ground Heat Exchanger Model. Applied Energy 141: 57-69.",
        "min_fields": 21.0
    }
}
```
