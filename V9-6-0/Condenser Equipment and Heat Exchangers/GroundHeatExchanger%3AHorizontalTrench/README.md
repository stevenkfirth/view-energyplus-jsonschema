```
{
    "GroundHeatExchanger:HorizontalTrench": {
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
                        "exclusiveMinimum": 0.0
                    },
                    "trench_length_in_pipe_axial_direction": {
                        "type": "number",
                        "note": "This is the total pipe axial length of the heat exchanger If all pipe trenches are parallel, this is the length of a single trench. If a single, long run of pipe is used with one trench, this is the full length of the pipe run.",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "ip-units": "ft",
                        "default": 50.0
                    },
                    "number_of_trenches": {
                        "type": "number",
                        "note": "This is the number of horizontal legs that will be used in the entire heat exchanger, one pipe per trench",
                        "minimum": 1.0,
                        "default": 1.0
                    },
                    "horizontal_spacing_between_pipes": {
                        "type": "number",
                        "note": "This represents the average horizontal spacing between any two trenches for heat exchangers that have multiple trenches",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "default": 1.0
                    },
                    "pipe_inner_diameter": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "ip-units": "in",
                        "default": 0.016
                    },
                    "pipe_outer_diameter": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "ip-units": "in",
                        "default": 0.026
                    },
                    "burial_depth": {
                        "type": "number",
                        "note": "This is the burial depth of the pipes, or the trenches containing the pipes",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "ip-units": "ft",
                        "default": 1.5
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
                        "default": 0.3895
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
                    "soil_moisture_content_percent": {
                        "type": "number",
                        "units": "percent",
                        "minimum": 0.0,
                        "maximum": 100.0,
                        "default": 30.0
                    },
                    "soil_moisture_content_percent_at_saturation": {
                        "type": "number",
                        "units": "percent",
                        "minimum": 0.0,
                        "maximum": 100.0,
                        "default": 50.0
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
                    "evapotranspiration_ground_cover_parameter": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.5,
                        "default": 0.4,
                        "note": "This specifies the ground cover effects during evapotranspiration calculations. The value roughly represents the following cases: = 0   : concrete or other solid, non-permeable ground surface material = 0.5 : short grass, much like a manicured lawn = 1   : standard reference state (12 cm grass) = 1.5 : wild growth"
                    }
                },
                "required": [
                    "inlet_node_name",
                    "outlet_node_name",
                    "design_flow_rate",
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
                "trench_length_in_pipe_axial_direction": {
                    "field_name": "Trench Length in Pipe Axial Direction",
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
                "pipe_inner_diameter": {
                    "field_name": "Pipe Inner Diameter",
                    "field_type": "n"
                },
                "pipe_outer_diameter": {
                    "field_name": "Pipe Outer Diameter",
                    "field_type": "n"
                },
                "burial_depth": {
                    "field_name": "Burial Depth",
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
                "soil_moisture_content_percent": {
                    "field_name": "Soil Moisture Content Percent",
                    "field_type": "n"
                },
                "soil_moisture_content_percent_at_saturation": {
                    "field_name": "Soil Moisture Content Percent at Saturation",
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
                "evapotranspiration_ground_cover_parameter": {
                    "field_name": "Evapotranspiration Ground Cover Parameter",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "inlet_node_name",
                "outlet_node_name",
                "design_flow_rate",
                "trench_length_in_pipe_axial_direction",
                "number_of_trenches",
                "horizontal_spacing_between_pipes",
                "pipe_inner_diameter",
                "pipe_outer_diameter",
                "burial_depth",
                "soil_thermal_conductivity",
                "soil_density",
                "soil_specific_heat",
                "pipe_thermal_conductivity",
                "pipe_density",
                "pipe_specific_heat",
                "soil_moisture_content_percent",
                "soil_moisture_content_percent_at_saturation",
                "undisturbed_ground_temperature_model_type",
                "undisturbed_ground_temperature_model_name",
                "evapotranspiration_ground_cover_parameter"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "inlet_node_name",
                    "outlet_node_name",
                    "undisturbed_ground_temperature_model_type",
                    "undisturbed_ground_temperature_model_name"
                ]
            },
            "numerics": {
                "fields": [
                    "design_flow_rate",
                    "trench_length_in_pipe_axial_direction",
                    "number_of_trenches",
                    "horizontal_spacing_between_pipes",
                    "pipe_inner_diameter",
                    "pipe_outer_diameter",
                    "burial_depth",
                    "soil_thermal_conductivity",
                    "soil_density",
                    "soil_specific_heat",
                    "pipe_thermal_conductivity",
                    "pipe_density",
                    "pipe_specific_heat",
                    "soil_moisture_content_percent",
                    "soil_moisture_content_percent_at_saturation",
                    "evapotranspiration_ground_cover_parameter"
                ]
            }
        },
        "type": "object",
        "memo": "This models a horizontal heat exchanger placed in a series of trenches The model uses the PipingSystem:Underground underlying algorithms, but provides a more usable input interface.",
        "min_fields": 20.0
    }
}
```
