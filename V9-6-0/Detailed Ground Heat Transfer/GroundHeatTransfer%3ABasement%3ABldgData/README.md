```
{
    "GroundHeatTransfer:Basement:BldgData": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "dwall_wall_thickness": {
                        "type": "number",
                        "units": "m",
                        "minimum": 0.2,
                        "default": 0.2
                    },
                    "dslab_floor_slab_thickness": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "maximum": 0.25,
                        "default": 0.1
                    },
                    "dgravxy_width_of_gravel_pit_beside_basement_wall": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "m",
                        "default": 0.3
                    },
                    "dgravzn_gravel_depth_extending_above_the_floor_slab": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "m",
                        "default": 0.2
                    },
                    "dgravzp_gravel_depth_below_the_floor_slab": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "m",
                        "default": 0.1
                    }
                }
            }
        },
        "group": "Detailed Ground Heat Transfer",
        "legacy_idd": {
            "field_info": {
                "dwall_wall_thickness": {
                    "field_name": "DWALL: Wall thickness",
                    "field_type": "n"
                },
                "dslab_floor_slab_thickness": {
                    "field_name": "DSLAB: Floor slab thickness",
                    "field_type": "n"
                },
                "dgravxy_width_of_gravel_pit_beside_basement_wall": {
                    "field_name": "DGRAVXY: Width of gravel pit beside basement wall",
                    "field_type": "n"
                },
                "dgravzn_gravel_depth_extending_above_the_floor_slab": {
                    "field_name": "DGRAVZN: Gravel depth extending above the floor slab",
                    "field_type": "n"
                },
                "dgravzp_gravel_depth_below_the_floor_slab": {
                    "field_name": "DGRAVZP: Gravel depth below the floor slab",
                    "field_type": "n"
                }
            },
            "fields": [
                "dwall_wall_thickness",
                "dslab_floor_slab_thickness",
                "dgravxy_width_of_gravel_pit_beside_basement_wall",
                "dgravzn_gravel_depth_extending_above_the_floor_slab",
                "dgravzp_gravel_depth_below_the_floor_slab"
            ],
            "alphas": {
                "fields": []
            },
            "numerics": {
                "fields": [
                    "dwall_wall_thickness",
                    "dslab_floor_slab_thickness",
                    "dgravxy_width_of_gravel_pit_beside_basement_wall",
                    "dgravzn_gravel_depth_extending_above_the_floor_slab",
                    "dgravzp_gravel_depth_below_the_floor_slab"
                ]
            }
        },
        "type": "object",
        "memo": "Specifies the surface and gravel thicknesses used for the Basement preprocessor ground heat transfer simulation."
    }
}
```
