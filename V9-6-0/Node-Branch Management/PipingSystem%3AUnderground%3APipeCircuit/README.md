```
{
    "PipingSystem:Underground:PipeCircuit": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "pipe_thermal_conductivity": {
                        "type": "number",
                        "units": "W/m-K",
                        "exclusiveMinimum": 0.0
                    },
                    "pipe_density": {
                        "type": "number",
                        "units": "kg/m3",
                        "exclusiveMinimum": 0.0
                    },
                    "pipe_specific_heat": {
                        "type": "number",
                        "units": "J/kg-K",
                        "exclusiveMinimum": 0.0
                    },
                    "pipe_inner_diameter": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0
                    },
                    "pipe_outer_diameter": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0
                    },
                    "design_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "ip-units": "gal/min",
                        "exclusiveMinimum": 0.0
                    },
                    "circuit_inlet_node": {
                        "type": "string"
                    },
                    "circuit_outlet_node": {
                        "type": "string"
                    },
                    "convergence_criterion_for_the_inner_radial_iteration_loop": {
                        "type": "number",
                        "units": "deltaC",
                        "minimum": 1e-06,
                        "maximum": 0.5,
                        "default": 0.001
                    },
                    "maximum_iterations_in_the_inner_radial_iteration_loop": {
                        "type": "number",
                        "minimum": 3.0,
                        "maximum": 10000.0,
                        "default": 500.0
                    },
                    "number_of_soil_nodes_in_the_inner_radial_near_pipe_mesh_region": {
                        "type": "number",
                        "minimum": 1.0,
                        "maximum": 15.0,
                        "default": 3.0
                    },
                    "radial_thickness_of_inner_radial_near_pipe_mesh_region": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "note": "Required because it must be selected by user instead of being inferred from circuit/domain object inputs."
                    },
                    "number_of_pipe_segments_entered_for_this_pipe_circuit": {
                        "type": "number",
                        "minimum": 1.0
                    },
                    "pipe_segments": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "pipe_segment": {
                                    "type": "string",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "PipingSystemUndergroundSegmentNames"
                                    ],
                                    "note": "Name of a pipe segment to be included in this pipe circuit"
                                }
                            },
                            "type": "object",
                            "required": [
                                "pipe_segment"
                            ]
                        }
                    }
                },
                "required": [
                    "pipe_thermal_conductivity",
                    "pipe_density",
                    "pipe_specific_heat",
                    "pipe_inner_diameter",
                    "pipe_outer_diameter",
                    "design_flow_rate",
                    "circuit_inlet_node",
                    "circuit_outlet_node",
                    "radial_thickness_of_inner_radial_near_pipe_mesh_region",
                    "number_of_pipe_segments_entered_for_this_pipe_circuit"
                ]
            }
        },
        "group": "Node-Branch Management",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "PipingSystemUndergroundCircuitNames",
                "validBranchEquipmentNames",
                "validCondenserEquipmentNames",
                "validPlantEquipmentNames"
            ],
            "reference-class-name": [
                "validBranchEquipmentTypes",
                "validCondenserEquipmentTypes",
                "validPlantEquipmentTypes"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
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
                "pipe_inner_diameter": {
                    "field_name": "Pipe Inner Diameter",
                    "field_type": "n"
                },
                "pipe_outer_diameter": {
                    "field_name": "Pipe Outer Diameter",
                    "field_type": "n"
                },
                "design_flow_rate": {
                    "field_name": "Design Flow Rate",
                    "field_type": "n"
                },
                "circuit_inlet_node": {
                    "field_name": "Circuit Inlet Node",
                    "field_type": "a"
                },
                "circuit_outlet_node": {
                    "field_name": "Circuit Outlet Node",
                    "field_type": "a"
                },
                "convergence_criterion_for_the_inner_radial_iteration_loop": {
                    "field_name": "Convergence Criterion for the Inner Radial Iteration Loop",
                    "field_type": "n"
                },
                "maximum_iterations_in_the_inner_radial_iteration_loop": {
                    "field_name": "Maximum Iterations in the Inner Radial Iteration Loop",
                    "field_type": "n"
                },
                "number_of_soil_nodes_in_the_inner_radial_near_pipe_mesh_region": {
                    "field_name": "Number of Soil Nodes in the Inner Radial Near Pipe Mesh Region",
                    "field_type": "n"
                },
                "radial_thickness_of_inner_radial_near_pipe_mesh_region": {
                    "field_name": "Radial Thickness of Inner Radial Near Pipe Mesh Region",
                    "field_type": "n"
                },
                "number_of_pipe_segments_entered_for_this_pipe_circuit": {
                    "field_name": "Number of Pipe Segments Entered for this Pipe Circuit",
                    "field_type": "n"
                },
                "pipe_segment": {
                    "field_name": "Pipe Segment",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "pipe_thermal_conductivity",
                "pipe_density",
                "pipe_specific_heat",
                "pipe_inner_diameter",
                "pipe_outer_diameter",
                "design_flow_rate",
                "circuit_inlet_node",
                "circuit_outlet_node",
                "convergence_criterion_for_the_inner_radial_iteration_loop",
                "maximum_iterations_in_the_inner_radial_iteration_loop",
                "number_of_soil_nodes_in_the_inner_radial_near_pipe_mesh_region",
                "radial_thickness_of_inner_radial_near_pipe_mesh_region",
                "number_of_pipe_segments_entered_for_this_pipe_circuit"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "circuit_inlet_node",
                    "circuit_outlet_node"
                ],
                "extensions": [
                    "pipe_segment"
                ]
            },
            "numerics": {
                "fields": [
                    "pipe_thermal_conductivity",
                    "pipe_density",
                    "pipe_specific_heat",
                    "pipe_inner_diameter",
                    "pipe_outer_diameter",
                    "design_flow_rate",
                    "convergence_criterion_for_the_inner_radial_iteration_loop",
                    "maximum_iterations_in_the_inner_radial_iteration_loop",
                    "number_of_soil_nodes_in_the_inner_radial_near_pipe_mesh_region",
                    "radial_thickness_of_inner_radial_near_pipe_mesh_region",
                    "number_of_pipe_segments_entered_for_this_pipe_circuit"
                ]
            },
            "extensibles": [
                "pipe_segment"
            ],
            "extension": "pipe_segments"
        },
        "type": "object",
        "memo": "The pipe circuit object in an underground piping system. This object is simulated within an underground piping domain object and connected on a branch on a plant loop.",
        "min_fields": 15.0,
        "extensible_size": 1.0
    }
}
```
