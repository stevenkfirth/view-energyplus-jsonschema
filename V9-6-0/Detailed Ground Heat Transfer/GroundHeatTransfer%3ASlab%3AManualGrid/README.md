```
{
    "GroundHeatTransfer:Slab:ManualGrid": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "nx_number_of_cells_in_the_x_direction": {
                        "type": "number",
                        "minimum": 1.0
                    },
                    "ny_number_of_cells_in_the_y_direction": {
                        "type": "number",
                        "minimum": 1.0
                    },
                    "nz_number_of_cells_in_the_z_direction": {
                        "type": "number",
                        "minimum": 1.0
                    },
                    "ibox_x_direction_cell_indicator_of_slab_edge": {
                        "type": "number",
                        "note": "typical values= 1-10"
                    },
                    "jbox_y_direction_cell_indicator_of_slab_edge": {
                        "type": "number",
                        "note": "typical values= 1-10"
                    }
                },
                "required": [
                    "nx_number_of_cells_in_the_x_direction",
                    "ny_number_of_cells_in_the_y_direction",
                    "nz_number_of_cells_in_the_z_direction",
                    "ibox_x_direction_cell_indicator_of_slab_edge",
                    "jbox_y_direction_cell_indicator_of_slab_edge"
                ]
            }
        },
        "group": "Detailed Ground Heat Transfer",
        "legacy_idd": {
            "field_info": {
                "nx_number_of_cells_in_the_x_direction": {
                    "field_name": "NX: Number of cells in the X direction",
                    "field_type": "n"
                },
                "ny_number_of_cells_in_the_y_direction": {
                    "field_name": "NY: Number of cells in the Y direction",
                    "field_type": "n"
                },
                "nz_number_of_cells_in_the_z_direction": {
                    "field_name": "NZ: Number of cells in the Z direction",
                    "field_type": "n"
                },
                "ibox_x_direction_cell_indicator_of_slab_edge": {
                    "field_name": "IBOX: X direction cell indicator of slab edge",
                    "field_type": "n"
                },
                "jbox_y_direction_cell_indicator_of_slab_edge": {
                    "field_name": "JBOX: Y direction cell indicator of slab edge",
                    "field_type": "n"
                }
            },
            "fields": [
                "nx_number_of_cells_in_the_x_direction",
                "ny_number_of_cells_in_the_y_direction",
                "nz_number_of_cells_in_the_z_direction",
                "ibox_x_direction_cell_indicator_of_slab_edge",
                "jbox_y_direction_cell_indicator_of_slab_edge"
            ],
            "alphas": {
                "fields": []
            },
            "numerics": {
                "fields": [
                    "nx_number_of_cells_in_the_x_direction",
                    "ny_number_of_cells_in_the_y_direction",
                    "nz_number_of_cells_in_the_z_direction",
                    "ibox_x_direction_cell_indicator_of_slab_edge",
                    "jbox_y_direction_cell_indicator_of_slab_edge"
                ]
            }
        },
        "type": "object",
        "memo": "Manual Grid only necessary when using manual gridding (not recommended) Used only in special cases when previous two objects are not used. User must input complete gridding information."
    }
}
```
