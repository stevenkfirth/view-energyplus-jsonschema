```
{
    "GroundHeatTransfer:Basement:AutoGrid": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "clearance_distance_from_outside_of_wall_to_edge_": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m",
                        "default": 15.0
                    },
                    "slabx_x_dimension_of_the_building_slab": {
                        "type": "number",
                        "units": "m",
                        "minimum": 0.0,
                        "maximum": 60.0
                    },
                    "slaby_y_dimension_of_the_building_slab": {
                        "type": "number",
                        "units": "m",
                        "minimum": 0.0,
                        "maximum": 60.0
                    },
                    "concagheight_height_of_the_foundation_wall_above_grade": {
                        "type": "number",
                        "units": "m",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "slabdepth_thickness_of_the_floor_slab": {
                        "type": "number",
                        "units": "m",
                        "default": 0.1
                    },
                    "basedepth_depth_of_the_basement_wall_below_grade": {
                        "type": "number",
                        "units": "m",
                        "minimum": 0.0,
                        "default": 2.0
                    }
                },
                "required": [
                    "slabx_x_dimension_of_the_building_slab",
                    "slaby_y_dimension_of_the_building_slab"
                ]
            }
        },
        "group": "Detailed Ground Heat Transfer",
        "legacy_idd": {
            "field_info": {
                "clearance_distance_from_outside_of_wall_to_edge_": {
                    "field_name": "CLEARANCE: Distance from outside of wall to edge,",
                    "field_type": "n"
                },
                "slabx_x_dimension_of_the_building_slab": {
                    "field_name": "SLABX: X dimension of the building slab",
                    "field_type": "n"
                },
                "slaby_y_dimension_of_the_building_slab": {
                    "field_name": "SLABY: Y dimension of the building slab",
                    "field_type": "n"
                },
                "concagheight_height_of_the_foundation_wall_above_grade": {
                    "field_name": "ConcAGHeight: Height of the foundation wall above grade",
                    "field_type": "n"
                },
                "slabdepth_thickness_of_the_floor_slab": {
                    "field_name": "SlabDepth: Thickness of the floor slab",
                    "field_type": "n"
                },
                "basedepth_depth_of_the_basement_wall_below_grade": {
                    "field_name": "BaseDepth: Depth of the basement wall below grade",
                    "field_type": "n"
                }
            },
            "fields": [
                "clearance_distance_from_outside_of_wall_to_edge_",
                "slabx_x_dimension_of_the_building_slab",
                "slaby_y_dimension_of_the_building_slab",
                "concagheight_height_of_the_foundation_wall_above_grade",
                "slabdepth_thickness_of_the_floor_slab",
                "basedepth_depth_of_the_basement_wall_below_grade"
            ],
            "alphas": {
                "fields": []
            },
            "numerics": {
                "fields": [
                    "clearance_distance_from_outside_of_wall_to_edge_",
                    "slabx_x_dimension_of_the_building_slab",
                    "slaby_y_dimension_of_the_building_slab",
                    "concagheight_height_of_the_foundation_wall_above_grade",
                    "slabdepth_thickness_of_the_floor_slab",
                    "basedepth_depth_of_the_basement_wall_below_grade"
                ]
            }
        },
        "type": "object",
        "memo": "AutoGrid only necessary when EquivSizing is false If the modeled building is not a rectangle or square, Equivalent sizing MUST be used to get accurate results"
    }
}
```
