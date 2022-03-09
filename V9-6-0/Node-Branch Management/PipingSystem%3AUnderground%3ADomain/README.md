```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "xmax": {
                    "type": "number",
                    "units": "m",
                    "exclusiveMinimum": 0.0,
                    "note": "Domain extent in the local 'X' direction"
                },
                "ymax": {
                    "type": "number",
                    "units": "m",
                    "exclusiveMinimum": 0.0,
                    "note": "Domain extent in the local 'Y' direction"
                },
                "zmax": {
                    "type": "number",
                    "units": "m",
                    "exclusiveMinimum": 0.0,
                    "note": "Domain extent in the local 'Y' direction"
                },
                "x_direction_mesh_density_parameter": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 4.0,
                    "note": "If mesh type is symmetric geometric, this should be an even number."
                },
                "x_direction_mesh_type": {
                    "type": "string",
                    "enum": [
                        "SymmetricGeometric",
                        "Uniform"
                    ]
                },
                "x_direction_geometric_coefficient": {
                    "type": "number",
                    "note": "optional Only used if mesh type is symmetric geometric",
                    "minimum": 1.0,
                    "default": 1.3,
                    "maximum": 2.0
                },
                "y_direction_mesh_density_parameter": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 4.0,
                    "note": "If mesh type is symmetric geometric, this should be an even number."
                },
                "y_direction_mesh_type": {
                    "type": "string",
                    "enum": [
                        "SymmetricGeometric",
                        "Uniform"
                    ]
                },
                "y_direction_geometric_coefficient": {
                    "type": "number",
                    "note": "optional Only used if mesh type is symmetric geometric",
                    "minimum": 1.0,
                    "default": 1.3,
                    "maximum": 2.0
                },
                "z_direction_mesh_density_parameter": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 4.0,
                    "note": "If mesh type is symmetric geometric, this should be an even number."
                },
                "z_direction_mesh_type": {
                    "type": "string",
                    "enum": [
                        "SymmetricGeometric",
                        "Uniform"
                    ]
                },
                "z_direction_geometric_coefficient": {
                    "type": "number",
                    "note": "optional Only used if mesh type is symmetric geometric",
                    "minimum": 1.0,
                    "default": 1.3,
                    "maximum": 2.0
                },
                "soil_thermal_conductivity": {
                    "type": "number",
                    "units": "W/m-K",
                    "exclusiveMinimum": 0.0
                },
                "soil_density": {
                    "type": "number",
                    "units": "kg/m3",
                    "exclusiveMinimum": 0.0
                },
                "soil_specific_heat": {
                    "type": "number",
                    "units": "J/kg-K",
                    "exclusiveMinimum": 0.0,
                    "note": "This is a dry soil property, which is adjusted for freezing effects by the simulation algorithm."
                },
                "soil_moisture_content_volume_fraction": {
                    "type": "number",
                    "units": "percent",
                    "minimum": 0.0,
                    "maximum": 100.0,
                    "default": 30.0
                },
                "soil_moisture_content_volume_fraction_at_saturation": {
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
                "this_domain_includes_basement_surface_interaction": {
                    "type": "string",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "No",
                    "note": "if Yes, then the following basement inputs are used if No, then the following basement inputs are *ignored*"
                },
                "width_of_basement_floor_in_ground_domain": {
                    "type": "number",
                    "units": "m",
                    "note": "Required only if Domain Has Basement Interaction"
                },
                "depth_of_basement_wall_in_ground_domain": {
                    "type": "number",
                    "units": "m",
                    "note": "Required only if Domain Has Basement Interaction"
                },
                "shift_pipe_x_coordinates_by_basement_width": {
                    "type": "string",
                    "enum": [
                        "No",
                        "Yes"
                    ],
                    "note": "Required only if Domain Has Basement Interaction"
                },
                "name_of_basement_wall_boundary_condition_model": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "OSCMNames"
                    ],
                    "note": "Required only if Domain Has Basement Interaction"
                },
                "name_of_basement_floor_boundary_condition_model": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "OSCMNames"
                    ],
                    "note": "Required only if Domain Has Basement Interaction"
                },
                "convergence_criterion_for_the_outer_cartesian_domain_iteration_loop": {
                    "type": "number",
                    "units": "deltaC",
                    "minimum": 1e-06,
                    "maximum": 0.5,
                    "default": 0.001
                },
                "maximum_iterations_in_the_outer_cartesian_domain_iteration_loop": {
                    "type": "number",
                    "minimum": 3.0,
                    "maximum": 10000.0,
                    "default": 500.0
                },
                "evapotranspiration_ground_cover_parameter": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.5,
                    "default": 0.4,
                    "note": "This specifies the ground cover effects during evapotranspiration calculations. The value roughly represents the following cases: = 0   : concrete or other solid, non-permeable ground surface material = 0.5 : short grass, much like a manicured lawn = 1   : standard reference state (12 cm grass) = 1.5 : wild growth"
                },
                "number_of_pipe_circuits_entered_for_this_domain": {
                    "type": "number",
                    "minimum": 1.0
                },
                "pipe_circuits": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "pipe_circuit": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "PipingSystemUndergroundCircuitNames"
                                ],
                                "note": "Name of a pipe circuit to be simulated in this domain"
                            }
                        },
                        "type": "object",
                        "required": [
                            "pipe_circuit"
                        ]
                    }
                }
            },
            "required": [
                "xmax",
                "ymax",
                "zmax",
                "x_direction_mesh_type",
                "y_direction_mesh_type",
                "z_direction_mesh_type",
                "soil_thermal_conductivity",
                "soil_density",
                "soil_specific_heat",
                "undisturbed_ground_temperature_model_type",
                "undisturbed_ground_temperature_model_name",
                "number_of_pipe_circuits_entered_for_this_domain"
            ]
        }
    },
    "group": "Node-Branch Management",
    "name": {
        "type": "string",
        "is_required": true
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "xmax": {
                "field_name": "Xmax",
                "field_type": "n"
            },
            "ymax": {
                "field_name": "Ymax",
                "field_type": "n"
            },
            "zmax": {
                "field_name": "Zmax",
                "field_type": "n"
            },
            "x_direction_mesh_density_parameter": {
                "field_name": "X-Direction Mesh Density Parameter",
                "field_type": "n"
            },
            "x_direction_mesh_type": {
                "field_name": "X-Direction Mesh Type",
                "field_type": "a"
            },
            "x_direction_geometric_coefficient": {
                "field_name": "X-Direction Geometric Coefficient",
                "field_type": "n"
            },
            "y_direction_mesh_density_parameter": {
                "field_name": "Y-Direction Mesh Density Parameter",
                "field_type": "n"
            },
            "y_direction_mesh_type": {
                "field_name": "Y-Direction Mesh Type",
                "field_type": "a"
            },
            "y_direction_geometric_coefficient": {
                "field_name": "Y-Direction Geometric Coefficient",
                "field_type": "n"
            },
            "z_direction_mesh_density_parameter": {
                "field_name": "Z-Direction Mesh Density Parameter",
                "field_type": "n"
            },
            "z_direction_mesh_type": {
                "field_name": "Z-Direction Mesh Type",
                "field_type": "a"
            },
            "z_direction_geometric_coefficient": {
                "field_name": "Z-Direction Geometric Coefficient",
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
            "soil_moisture_content_volume_fraction": {
                "field_name": "Soil Moisture Content Volume Fraction",
                "field_type": "n"
            },
            "soil_moisture_content_volume_fraction_at_saturation": {
                "field_name": "Soil Moisture Content Volume Fraction at Saturation",
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
            "this_domain_includes_basement_surface_interaction": {
                "field_name": "This Domain Includes Basement Surface Interaction",
                "field_type": "a"
            },
            "width_of_basement_floor_in_ground_domain": {
                "field_name": "Width of Basement Floor in Ground Domain",
                "field_type": "n"
            },
            "depth_of_basement_wall_in_ground_domain": {
                "field_name": "Depth of Basement Wall In Ground Domain",
                "field_type": "n"
            },
            "shift_pipe_x_coordinates_by_basement_width": {
                "field_name": "Shift Pipe X Coordinates By Basement Width",
                "field_type": "a"
            },
            "name_of_basement_wall_boundary_condition_model": {
                "field_name": "Name of Basement Wall Boundary Condition Model",
                "field_type": "a"
            },
            "name_of_basement_floor_boundary_condition_model": {
                "field_name": "Name of Basement Floor Boundary Condition Model",
                "field_type": "a"
            },
            "convergence_criterion_for_the_outer_cartesian_domain_iteration_loop": {
                "field_name": "Convergence Criterion for the Outer Cartesian Domain Iteration Loop",
                "field_type": "n"
            },
            "maximum_iterations_in_the_outer_cartesian_domain_iteration_loop": {
                "field_name": "Maximum Iterations in the Outer Cartesian Domain Iteration Loop",
                "field_type": "n"
            },
            "evapotranspiration_ground_cover_parameter": {
                "field_name": "Evapotranspiration Ground Cover Parameter",
                "field_type": "n"
            },
            "number_of_pipe_circuits_entered_for_this_domain": {
                "field_name": "Number of Pipe Circuits Entered for this Domain",
                "field_type": "n"
            },
            "pipe_circuit": {
                "field_name": "Pipe Circuit",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "xmax",
            "ymax",
            "zmax",
            "x_direction_mesh_density_parameter",
            "x_direction_mesh_type",
            "x_direction_geometric_coefficient",
            "y_direction_mesh_density_parameter",
            "y_direction_mesh_type",
            "y_direction_geometric_coefficient",
            "z_direction_mesh_density_parameter",
            "z_direction_mesh_type",
            "z_direction_geometric_coefficient",
            "soil_thermal_conductivity",
            "soil_density",
            "soil_specific_heat",
            "soil_moisture_content_volume_fraction",
            "soil_moisture_content_volume_fraction_at_saturation",
            "undisturbed_ground_temperature_model_type",
            "undisturbed_ground_temperature_model_name",
            "this_domain_includes_basement_surface_interaction",
            "width_of_basement_floor_in_ground_domain",
            "depth_of_basement_wall_in_ground_domain",
            "shift_pipe_x_coordinates_by_basement_width",
            "name_of_basement_wall_boundary_condition_model",
            "name_of_basement_floor_boundary_condition_model",
            "convergence_criterion_for_the_outer_cartesian_domain_iteration_loop",
            "maximum_iterations_in_the_outer_cartesian_domain_iteration_loop",
            "evapotranspiration_ground_cover_parameter",
            "number_of_pipe_circuits_entered_for_this_domain"
        ],
        "alphas": {
            "fields": [
                "name",
                "x_direction_mesh_type",
                "y_direction_mesh_type",
                "z_direction_mesh_type",
                "undisturbed_ground_temperature_model_type",
                "undisturbed_ground_temperature_model_name",
                "this_domain_includes_basement_surface_interaction",
                "shift_pipe_x_coordinates_by_basement_width",
                "name_of_basement_wall_boundary_condition_model",
                "name_of_basement_floor_boundary_condition_model"
            ],
            "extensions": [
                "pipe_circuit"
            ]
        },
        "numerics": {
            "fields": [
                "xmax",
                "ymax",
                "zmax",
                "x_direction_mesh_density_parameter",
                "x_direction_geometric_coefficient",
                "y_direction_mesh_density_parameter",
                "y_direction_geometric_coefficient",
                "z_direction_mesh_density_parameter",
                "z_direction_geometric_coefficient",
                "soil_thermal_conductivity",
                "soil_density",
                "soil_specific_heat",
                "soil_moisture_content_volume_fraction",
                "soil_moisture_content_volume_fraction_at_saturation",
                "width_of_basement_floor_in_ground_domain",
                "depth_of_basement_wall_in_ground_domain",
                "convergence_criterion_for_the_outer_cartesian_domain_iteration_loop",
                "maximum_iterations_in_the_outer_cartesian_domain_iteration_loop",
                "evapotranspiration_ground_cover_parameter",
                "number_of_pipe_circuits_entered_for_this_domain"
            ]
        },
        "extensibles": [
            "pipe_circuit"
        ],
        "extension": "pipe_circuits"
    },
    "type": "object",
    "memo": "The ground domain object for underground piping system simulation.",
    "min_fields": 31.0,
    "extensible_size": 1.0
}
```
