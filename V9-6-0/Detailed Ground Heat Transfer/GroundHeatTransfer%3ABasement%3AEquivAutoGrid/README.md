```
{
    "GroundHeatTransfer:Basement:EquivAutoGrid": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "clearance_distance_from_outside_of_wall_to_edge_of_3_d_ground_domain": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m",
                        "default": 15.0
                    },
                    "slabdepth_thickness_of_the_floor_slab": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m",
                        "default": 0.1
                    },
                    "basedepth_depth_of_the_basement_wall_below_grade": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m",
                        "default": 2.0
                    }
                }
            }
        },
        "group": "Detailed Ground Heat Transfer",
        "legacy_idd": {
            "field_info": {
                "clearance_distance_from_outside_of_wall_to_edge_of_3_d_ground_domain": {
                    "field_name": "CLEARANCE: Distance from outside of wall to edge of 3-D ground domain",
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
                "clearance_distance_from_outside_of_wall_to_edge_of_3_d_ground_domain",
                "slabdepth_thickness_of_the_floor_slab",
                "basedepth_depth_of_the_basement_wall_below_grade"
            ],
            "alphas": {
                "fields": []
            },
            "numerics": {
                "fields": [
                    "clearance_distance_from_outside_of_wall_to_edge_of_3_d_ground_domain",
                    "slabdepth_thickness_of_the_floor_slab",
                    "basedepth_depth_of_the_basement_wall_below_grade"
                ]
            }
        },
        "type": "object",
        "memo": "EquivAutoGrid necessary when EquivSizing=TRUE, TRUE is is the normal case."
    }
}
```
