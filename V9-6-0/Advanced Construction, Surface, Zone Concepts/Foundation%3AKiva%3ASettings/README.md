```
{
    "Foundation:Kiva:Settings": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "soil_conductivity": {
                        "type": "number",
                        "default": 1.73,
                        "units": "W/m-K",
                        "exclusiveMinimum": 0.0
                    },
                    "soil_density": {
                        "type": "number",
                        "default": 1842.0,
                        "units": "kg/m3",
                        "exclusiveMinimum": 0.0
                    },
                    "soil_specific_heat": {
                        "type": "number",
                        "default": 419.0,
                        "units": "J/kg-K",
                        "exclusiveMinimum": 0.0
                    },
                    "ground_solar_absorptivity": {
                        "type": "number",
                        "default": 0.9,
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "ground_thermal_absorptivity": {
                        "type": "number",
                        "default": 0.9,
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "ground_surface_roughness": {
                        "type": "number",
                        "default": 0.03,
                        "units": "m",
                        "exclusiveMinimum": 0.0
                    },
                    "far_field_width": {
                        "type": "number",
                        "default": 40.0,
                        "units": "m",
                        "exclusiveMinimum": 0.0
                    },
                    "deep_ground_boundary_condition": {
                        "type": "string",
                        "enum": [
                            "",
                            "Autoselect",
                            "GroundWater",
                            "ZeroFlux"
                        ],
                        "default": "Autoselect"
                    },
                    "deep_ground_depth": {
                        "units": "m",
                        "default": "Autocalculate",
                        "anyOf": [
                            {
                                "type": "number",
                                "exclusiveMinimum": 0.0
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
                    "minimum_cell_dimension": {
                        "type": "number",
                        "default": 0.02,
                        "units": "m",
                        "exclusiveMinimum": 0.0
                    },
                    "maximum_cell_growth_coefficient": {
                        "type": "number",
                        "default": 1.5,
                        "units": "dimensionless",
                        "minimum": 1.0
                    },
                    "simulation_timestep": {
                        "type": "string",
                        "enum": [
                            "",
                            "Hourly",
                            "Timestep"
                        ],
                        "default": "Hourly"
                    }
                }
            }
        },
        "group": "Advanced Construction, Surface, Zone Concepts",
        "legacy_idd": {
            "field_info": {
                "soil_conductivity": {
                    "field_name": "Soil Conductivity",
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
                "ground_solar_absorptivity": {
                    "field_name": "Ground Solar Absorptivity",
                    "field_type": "n"
                },
                "ground_thermal_absorptivity": {
                    "field_name": "Ground Thermal Absorptivity",
                    "field_type": "n"
                },
                "ground_surface_roughness": {
                    "field_name": "Ground Surface Roughness",
                    "field_type": "n"
                },
                "far_field_width": {
                    "field_name": "Far-Field Width",
                    "field_type": "n"
                },
                "deep_ground_boundary_condition": {
                    "field_name": "Deep-Ground Boundary Condition",
                    "field_type": "a"
                },
                "deep_ground_depth": {
                    "field_name": "Deep-Ground Depth",
                    "field_type": "n"
                },
                "minimum_cell_dimension": {
                    "field_name": "Minimum Cell Dimension",
                    "field_type": "n"
                },
                "maximum_cell_growth_coefficient": {
                    "field_name": "Maximum Cell Growth Coefficient",
                    "field_type": "n"
                },
                "simulation_timestep": {
                    "field_name": "Simulation Timestep",
                    "field_type": "a"
                }
            },
            "fields": [
                "soil_conductivity",
                "soil_density",
                "soil_specific_heat",
                "ground_solar_absorptivity",
                "ground_thermal_absorptivity",
                "ground_surface_roughness",
                "far_field_width",
                "deep_ground_boundary_condition",
                "deep_ground_depth",
                "minimum_cell_dimension",
                "maximum_cell_growth_coefficient",
                "simulation_timestep"
            ],
            "alphas": {
                "fields": [
                    "deep_ground_boundary_condition",
                    "simulation_timestep"
                ]
            },
            "numerics": {
                "fields": [
                    "soil_conductivity",
                    "soil_density",
                    "soil_specific_heat",
                    "ground_solar_absorptivity",
                    "ground_thermal_absorptivity",
                    "ground_surface_roughness",
                    "far_field_width",
                    "deep_ground_depth",
                    "minimum_cell_dimension",
                    "maximum_cell_growth_coefficient"
                ]
            }
        },
        "type": "object",
        "memo": "Settings applied across all Kiva foundation calculations. Object is not required. If not defined, defaults will be applied."
    }
}
```
