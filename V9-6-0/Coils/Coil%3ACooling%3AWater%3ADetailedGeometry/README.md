```
{
    "Coil:Cooling:Water:DetailedGeometry": {
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
                    "maximum_water_flow_rate": {
                        "units": "m3/s",
                        "default": "Autosize",
                        "ip-units": "gal/min",
                        "anyOf": [
                            {
                                "type": "number"
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
                    "tube_outside_surface_area": {
                        "units": "m2",
                        "default": "Autosize",
                        "note": "Tube Primary Surface Area",
                        "anyOf": [
                            {
                                "type": "number"
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
                    "total_tube_inside_area": {
                        "units": "m2",
                        "default": "Autosize",
                        "note": "Total tube inside surface area",
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
                    "fin_surface_area": {
                        "units": "m2",
                        "default": "Autosize",
                        "anyOf": [
                            {
                                "type": "number"
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
                    "minimum_airflow_area": {
                        "units": "m2",
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
                    "coil_depth": {
                        "default": "Autosize",
                        "units": "m",
                        "ip-units": "in",
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
                    "fin_diameter": {
                        "units": "m",
                        "default": "Autosize",
                        "note": "Fin diameter or the coil height",
                        "ip-units": "in",
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
                    "fin_thickness": {
                        "type": "number",
                        "units": "m",
                        "ip-units": "in",
                        "exclusiveMinimum": 0.0,
                        "default": 0.0015
                    },
                    "tube_inside_diameter": {
                        "type": "number",
                        "units": "m",
                        "note": "Inner diameter of tubes",
                        "ip-units": "in",
                        "default": 0.01445,
                        "exclusiveMinimum": 0.0
                    },
                    "tube_outside_diameter": {
                        "type": "number",
                        "units": "m",
                        "note": "Outer diameter of tubes",
                        "ip-units": "in",
                        "default": 0.0159,
                        "exclusiveMinimum": 0.0
                    },
                    "tube_thermal_conductivity": {
                        "type": "number",
                        "units": "W/m-K",
                        "minimum": 1.0,
                        "default": 386.0
                    },
                    "fin_thermal_conductivity": {
                        "type": "number",
                        "units": "W/m-K",
                        "minimum": 1.0,
                        "default": 204.0
                    },
                    "fin_spacing": {
                        "type": "number",
                        "units": "m",
                        "note": "Fin spacing or distance",
                        "ip-units": "in",
                        "default": 0.0018,
                        "exclusiveMinimum": 0.0
                    },
                    "tube_depth_spacing": {
                        "type": "number",
                        "units": "m",
                        "ip-units": "in",
                        "default": 0.026,
                        "exclusiveMinimum": 0.0
                    },
                    "number_of_tube_rows": {
                        "type": "number",
                        "default": 4.0,
                        "exclusiveMinimum": 0.0
                    },
                    "number_of_tubes_per_row": {
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
                    "water_inlet_node_name": {
                        "type": "string"
                    },
                    "water_outlet_node_name": {
                        "type": "string"
                    },
                    "air_inlet_node_name": {
                        "type": "string"
                    },
                    "air_outlet_node_name": {
                        "type": "string"
                    },
                    "condensate_collection_water_storage_tank_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "WaterStorageTankNames"
                        ]
                    },
                    "design_water_temperature_difference": {
                        "type": "number",
                        "units": "deltaC",
                        "exclusiveMinimum": 0.0,
                        "note": "This input field is optional. If specified, it is used for sizing the Design Water Flow Rate. If blank or omitted, the Loop Design Temperature Difference value specified in Sizing:Plant object is used for sizing the Design Water Flow Rate."
                    },
                    "design_inlet_water_temperature": {
                        "units": "C",
                        "default": "Autosize",
                        "note": "This input field is optional. If specified, it is used for sizing the coil Design Geomtery Parameters. If autosized, the Design Loop Exit Temperature value specified in Sizing:Plant object is used for sizing the coil Design Geomtery Parameters. If the autosized value is  higher than the coil design outlet air temperature, then the design inlet water temperature  value is reset to coil design outlet air temperature minus 5.0 DeltaC.",
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
                    }
                },
                "required": [
                    "water_inlet_node_name",
                    "water_outlet_node_name",
                    "air_inlet_node_name",
                    "air_outlet_node_name"
                ]
            }
        },
        "group": "Coils",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "AFNCoilNames",
                "CoolingCoilName",
                "CoolingCoilsWater",
                "CoolingCoilsWaterNoHX",
                "validBranchEquipmentNames",
                "validOASysEquipmentNames"
            ],
            "reference-class-name": [
                "validBranchEquipmentTypes",
                "validOASysEquipmentTypes"
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
                "maximum_water_flow_rate": {
                    "field_name": "Maximum Water Flow Rate",
                    "field_type": "n"
                },
                "tube_outside_surface_area": {
                    "field_name": "Tube Outside Surface Area",
                    "field_type": "n"
                },
                "total_tube_inside_area": {
                    "field_name": "Total Tube Inside Area",
                    "field_type": "n"
                },
                "fin_surface_area": {
                    "field_name": "Fin Surface Area",
                    "field_type": "n"
                },
                "minimum_airflow_area": {
                    "field_name": "Minimum Airflow Area",
                    "field_type": "n"
                },
                "coil_depth": {
                    "field_name": "Coil Depth",
                    "field_type": "n"
                },
                "fin_diameter": {
                    "field_name": "Fin Diameter",
                    "field_type": "n"
                },
                "fin_thickness": {
                    "field_name": "Fin Thickness",
                    "field_type": "n"
                },
                "tube_inside_diameter": {
                    "field_name": "Tube Inside Diameter",
                    "field_type": "n"
                },
                "tube_outside_diameter": {
                    "field_name": "Tube Outside Diameter",
                    "field_type": "n"
                },
                "tube_thermal_conductivity": {
                    "field_name": "Tube Thermal Conductivity",
                    "field_type": "n"
                },
                "fin_thermal_conductivity": {
                    "field_name": "Fin Thermal Conductivity",
                    "field_type": "n"
                },
                "fin_spacing": {
                    "field_name": "Fin Spacing",
                    "field_type": "n"
                },
                "tube_depth_spacing": {
                    "field_name": "Tube Depth Spacing",
                    "field_type": "n"
                },
                "number_of_tube_rows": {
                    "field_name": "Number of Tube Rows",
                    "field_type": "n"
                },
                "number_of_tubes_per_row": {
                    "field_name": "Number of Tubes per Row",
                    "field_type": "n"
                },
                "water_inlet_node_name": {
                    "field_name": "Water Inlet Node Name",
                    "field_type": "a"
                },
                "water_outlet_node_name": {
                    "field_name": "Water Outlet Node Name",
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
                "condensate_collection_water_storage_tank_name": {
                    "field_name": "Condensate Collection Water Storage Tank Name",
                    "field_type": "a"
                },
                "design_water_temperature_difference": {
                    "field_name": "Design Water Temperature Difference",
                    "field_type": "n"
                },
                "design_inlet_water_temperature": {
                    "field_name": "Design Inlet Water Temperature",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "maximum_water_flow_rate",
                "tube_outside_surface_area",
                "total_tube_inside_area",
                "fin_surface_area",
                "minimum_airflow_area",
                "coil_depth",
                "fin_diameter",
                "fin_thickness",
                "tube_inside_diameter",
                "tube_outside_diameter",
                "tube_thermal_conductivity",
                "fin_thermal_conductivity",
                "fin_spacing",
                "tube_depth_spacing",
                "number_of_tube_rows",
                "number_of_tubes_per_row",
                "water_inlet_node_name",
                "water_outlet_node_name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "condensate_collection_water_storage_tank_name",
                "design_water_temperature_difference",
                "design_inlet_water_temperature"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "water_inlet_node_name",
                    "water_outlet_node_name",
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "condensate_collection_water_storage_tank_name"
                ]
            },
            "numerics": {
                "fields": [
                    "maximum_water_flow_rate",
                    "tube_outside_surface_area",
                    "total_tube_inside_area",
                    "fin_surface_area",
                    "minimum_airflow_area",
                    "coil_depth",
                    "fin_diameter",
                    "fin_thickness",
                    "tube_inside_diameter",
                    "tube_outside_diameter",
                    "tube_thermal_conductivity",
                    "fin_thermal_conductivity",
                    "fin_spacing",
                    "tube_depth_spacing",
                    "number_of_tube_rows",
                    "number_of_tubes_per_row",
                    "design_water_temperature_difference",
                    "design_inlet_water_temperature"
                ]
            }
        },
        "type": "object",
        "memo": "Chilled water cooling coil, detailed flat fin coil model for continuous plate fins, with inputs for detailed coil geometry specifications."
    }
}
```
