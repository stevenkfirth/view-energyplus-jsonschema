```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "initial_indoor_air_temperature": {
                    "type": "number",
                    "note": "Indoor air temperature used for Kiva initialization (prior to warmup period) If left blank, indoor air temperature will be determined based on zone setpoints",
                    "units": "C"
                },
                "interior_horizontal_insulation_material_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "MaterialName"
                    ]
                },
                "interior_horizontal_insulation_depth": {
                    "type": "number",
                    "note": "Distance from the slab bottom to the top of interior horizontal insulation",
                    "units": "m",
                    "minimum": 0.0,
                    "default": 0.0
                },
                "interior_horizontal_insulation_width": {
                    "type": "number",
                    "note": "Extent of insulation as measured from the wall interior",
                    "units": "m",
                    "exclusiveMinimum": 0.0
                },
                "interior_vertical_insulation_material_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "MaterialName"
                    ]
                },
                "interior_vertical_insulation_depth": {
                    "type": "number",
                    "note": "Extent of insulation as measured from the wall top to the bottom edge of the interior vertical insulation",
                    "units": "m",
                    "exclusiveMinimum": 0.0
                },
                "exterior_horizontal_insulation_material_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "MaterialName"
                    ]
                },
                "exterior_horizontal_insulation_depth": {
                    "type": "number",
                    "note": "Distance from the exterior grade to the top of exterior horizontal insulation",
                    "units": "m",
                    "minimum": 0.0
                },
                "exterior_horizontal_insulation_width": {
                    "type": "number",
                    "note": "Extent of insulation as measured from the wall exterior",
                    "units": "m",
                    "minimum": 0.0,
                    "default": 0.0
                },
                "exterior_vertical_insulation_material_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "MaterialName"
                    ]
                },
                "exterior_vertical_insulation_depth": {
                    "type": "number",
                    "note": "Extent of insulation as measured from the wall top to the bottom edge of the exterior vertical insulation",
                    "units": "m",
                    "exclusiveMinimum": 0.0
                },
                "wall_height_above_grade": {
                    "type": "number",
                    "note": "Distance from the exterior grade to the wall top",
                    "units": "m",
                    "minimum": 0.0,
                    "default": 0.2
                },
                "wall_depth_below_slab": {
                    "type": "number",
                    "note": "Distance from the slab bottom to the bottom of the foundation wall",
                    "units": "m",
                    "minimum": 0.0,
                    "default": 0.0
                },
                "footing_wall_construction_name": {
                    "type": "string",
                    "note": "Defines the below-grade surface construction for slabs. Required if foundation wall is not exposed to the zone.",
                    "data_type": "object_list",
                    "object_list": [
                        "ConstructionNames"
                    ]
                },
                "footing_material_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "MaterialName"
                    ]
                },
                "footing_depth": {
                    "type": "number",
                    "note": "Top-to-bottom dimension of the footing (not to be confused with its depth in the ground). The width of the footing is defined by the material's thickness.",
                    "units": "m",
                    "exclusiveMinimum": 0.0,
                    "default": 0.3
                },
                "blocks": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "custom_block_material_name": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "MaterialName"
                                ]
                            },
                            "custom_block_depth": {
                                "type": "number",
                                "note": "Top-to-bottom dimension of the block downward.",
                                "units": "m",
                                "exclusiveMinimum": 0.0
                            },
                            "custom_block_x_position": {
                                "type": "number",
                                "note": "Position outward (+) or inward (-) relative to the foundation wall interior",
                                "units": "m"
                            },
                            "custom_block_z_position": {
                                "type": "number",
                                "note": "Position downward (+) relative to the foundation wall top",
                                "units": "m"
                            }
                        },
                        "type": "object"
                    }
                }
            }
        }
    },
    "group": "Advanced Construction, Surface, Zone Concepts",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "OutFaceEnvNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "initial_indoor_air_temperature": {
                "field_name": "Initial Indoor Air Temperature",
                "field_type": "n"
            },
            "interior_horizontal_insulation_material_name": {
                "field_name": "Interior Horizontal Insulation Material Name",
                "field_type": "a"
            },
            "interior_horizontal_insulation_depth": {
                "field_name": "Interior Horizontal Insulation Depth",
                "field_type": "n"
            },
            "interior_horizontal_insulation_width": {
                "field_name": "Interior Horizontal Insulation Width",
                "field_type": "n"
            },
            "interior_vertical_insulation_material_name": {
                "field_name": "Interior Vertical Insulation Material Name",
                "field_type": "a"
            },
            "interior_vertical_insulation_depth": {
                "field_name": "Interior Vertical Insulation Depth",
                "field_type": "n"
            },
            "exterior_horizontal_insulation_material_name": {
                "field_name": "Exterior Horizontal Insulation Material Name",
                "field_type": "a"
            },
            "exterior_horizontal_insulation_depth": {
                "field_name": "Exterior Horizontal Insulation Depth",
                "field_type": "n"
            },
            "exterior_horizontal_insulation_width": {
                "field_name": "Exterior Horizontal Insulation Width",
                "field_type": "n"
            },
            "exterior_vertical_insulation_material_name": {
                "field_name": "Exterior Vertical Insulation Material Name",
                "field_type": "a"
            },
            "exterior_vertical_insulation_depth": {
                "field_name": "Exterior Vertical Insulation Depth",
                "field_type": "n"
            },
            "wall_height_above_grade": {
                "field_name": "Wall Height Above Grade",
                "field_type": "n"
            },
            "wall_depth_below_slab": {
                "field_name": "Wall Depth Below Slab",
                "field_type": "n"
            },
            "footing_wall_construction_name": {
                "field_name": "Footing Wall Construction Name",
                "field_type": "a"
            },
            "footing_material_name": {
                "field_name": "Footing Material Name",
                "field_type": "a"
            },
            "footing_depth": {
                "field_name": "Footing Depth",
                "field_type": "n"
            },
            "custom_block_material_name": {
                "field_name": "Custom Block Material Name",
                "field_type": "a"
            },
            "custom_block_depth": {
                "field_name": "Custom Block Depth",
                "field_type": "n"
            },
            "custom_block_x_position": {
                "field_name": "Custom Block X Position",
                "field_type": "n"
            },
            "custom_block_z_position": {
                "field_name": "Custom Block Z Position",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "initial_indoor_air_temperature",
            "interior_horizontal_insulation_material_name",
            "interior_horizontal_insulation_depth",
            "interior_horizontal_insulation_width",
            "interior_vertical_insulation_material_name",
            "interior_vertical_insulation_depth",
            "exterior_horizontal_insulation_material_name",
            "exterior_horizontal_insulation_depth",
            "exterior_horizontal_insulation_width",
            "exterior_vertical_insulation_material_name",
            "exterior_vertical_insulation_depth",
            "wall_height_above_grade",
            "wall_depth_below_slab",
            "footing_wall_construction_name",
            "footing_material_name",
            "footing_depth"
        ],
        "alphas": {
            "fields": [
                "name",
                "interior_horizontal_insulation_material_name",
                "interior_vertical_insulation_material_name",
                "exterior_horizontal_insulation_material_name",
                "exterior_vertical_insulation_material_name",
                "footing_wall_construction_name",
                "footing_material_name"
            ],
            "extensions": [
                "custom_block_material_name"
            ]
        },
        "numerics": {
            "fields": [
                "initial_indoor_air_temperature",
                "interior_horizontal_insulation_depth",
                "interior_horizontal_insulation_width",
                "interior_vertical_insulation_depth",
                "exterior_horizontal_insulation_depth",
                "exterior_horizontal_insulation_width",
                "exterior_vertical_insulation_depth",
                "wall_height_above_grade",
                "wall_depth_below_slab",
                "footing_depth"
            ],
            "extensions": [
                "custom_block_depth",
                "custom_block_x_position",
                "custom_block_z_position"
            ]
        },
        "extensibles": [
            "custom_block_material_name",
            "custom_block_depth",
            "custom_block_x_position",
            "custom_block_z_position"
        ],
        "extension": "blocks"
    },
    "type": "object",
    "memo": "Refined definition of the foundation surface construction used to inform two-dimensional heat transfer calculated using the Kiva ground heat transfer methodology.",
    "extensible_size": 4.0
}
```
