```
{
    "GroundHeatTransfer:Basement:ManualGrid": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "nx_number_of_cells_in_the_x_direction_20_": {
                        "type": "number",
                        "minimum": 1.0
                    },
                    "ny_number_of_cells_in_the_y_direction_20_": {
                        "type": "number",
                        "minimum": 1.0
                    },
                    "nzag_number_of_cells_in_the_z_direction_above_grade_4_always_": {
                        "type": "number",
                        "minimum": 1.0
                    },
                    "nzbg_number_of_cells_in_z_direction_below_grade_10_35_": {
                        "type": "number",
                        "minimum": 1.0
                    },
                    "ibase_x_direction_cell_indicator_of_slab_edge_5_20_": {
                        "type": "number"
                    },
                    "jbase_y_direction_cell_indicator_of_slab_edge_5_20_": {
                        "type": "number"
                    },
                    "kbase_z_direction_cell_indicator_of_the_top_of_the_floor_slab_5_20_": {
                        "type": "number"
                    }
                },
                "required": [
                    "nx_number_of_cells_in_the_x_direction_20_",
                    "ny_number_of_cells_in_the_y_direction_20_",
                    "nzag_number_of_cells_in_the_z_direction_above_grade_4_always_",
                    "nzbg_number_of_cells_in_z_direction_below_grade_10_35_",
                    "ibase_x_direction_cell_indicator_of_slab_edge_5_20_",
                    "jbase_y_direction_cell_indicator_of_slab_edge_5_20_",
                    "kbase_z_direction_cell_indicator_of_the_top_of_the_floor_slab_5_20_"
                ]
            }
        },
        "group": "Detailed Ground Heat Transfer",
        "legacy_idd": {
            "field_info": {
                "nx_number_of_cells_in_the_x_direction_20_": {
                    "field_name": "NX: Number of cells in the X direction: 20]",
                    "field_type": "n"
                },
                "ny_number_of_cells_in_the_y_direction_20_": {
                    "field_name": "NY: Number of cells in the Y direction: 20]",
                    "field_type": "n"
                },
                "nzag_number_of_cells_in_the_z_direction_above_grade_4_always_": {
                    "field_name": "NZAG: Number of cells in the Z direction. above grade: 4 Always]",
                    "field_type": "n"
                },
                "nzbg_number_of_cells_in_z_direction_below_grade_10_35_": {
                    "field_name": "NZBG: Number of cells in Z direction. below grade: 10-35]",
                    "field_type": "n"
                },
                "ibase_x_direction_cell_indicator_of_slab_edge_5_20_": {
                    "field_name": "IBASE: X direction cell indicator of slab edge: 5-20]",
                    "field_type": "n"
                },
                "jbase_y_direction_cell_indicator_of_slab_edge_5_20_": {
                    "field_name": "JBASE: Y direction cell indicator of slab edge: 5-20]",
                    "field_type": "n"
                },
                "kbase_z_direction_cell_indicator_of_the_top_of_the_floor_slab_5_20_": {
                    "field_name": "KBASE: Z direction cell indicator of the top of the floor slab: 5-20]",
                    "field_type": "n"
                }
            },
            "fields": [
                "nx_number_of_cells_in_the_x_direction_20_",
                "ny_number_of_cells_in_the_y_direction_20_",
                "nzag_number_of_cells_in_the_z_direction_above_grade_4_always_",
                "nzbg_number_of_cells_in_z_direction_below_grade_10_35_",
                "ibase_x_direction_cell_indicator_of_slab_edge_5_20_",
                "jbase_y_direction_cell_indicator_of_slab_edge_5_20_",
                "kbase_z_direction_cell_indicator_of_the_top_of_the_floor_slab_5_20_"
            ],
            "alphas": {
                "fields": []
            },
            "numerics": {
                "fields": [
                    "nx_number_of_cells_in_the_x_direction_20_",
                    "ny_number_of_cells_in_the_y_direction_20_",
                    "nzag_number_of_cells_in_the_z_direction_above_grade_4_always_",
                    "nzbg_number_of_cells_in_z_direction_below_grade_10_35_",
                    "ibase_x_direction_cell_indicator_of_slab_edge_5_20_",
                    "jbase_y_direction_cell_indicator_of_slab_edge_5_20_",
                    "kbase_z_direction_cell_indicator_of_the_top_of_the_floor_slab_5_20_"
                ]
            }
        },
        "type": "object",
        "memo": "Manual Grid only necessary using manual gridding (not recommended)"
    }
}
```
