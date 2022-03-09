```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "slabx_x_dimension_of_the_building_slab": {
                    "type": "number",
                    "minimum": 6.0,
                    "note": "typical values= 6 to 60.0",
                    "units": "m"
                },
                "slaby_y_dimension_of_the_building_slab": {
                    "type": "number",
                    "minimum": 6.0,
                    "note": "typical values= 6 to 60.0",
                    "units": "m"
                },
                "slabdepth_thickness_of_slab_on_grade": {
                    "type": "number",
                    "default": 0.1,
                    "units": "m"
                },
                "clearance_distance_from_edge_of_slab_to_domain_edge": {
                    "type": "number",
                    "default": 15.0,
                    "units": "m"
                },
                "zclearance_distance_from_bottom_of_slab_to_domain_bottom": {
                    "type": "number",
                    "default": 15.0,
                    "units": "m"
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
            "slabx_x_dimension_of_the_building_slab": {
                "field_name": "SLABX: X dimension of the building slab",
                "field_type": "n"
            },
            "slaby_y_dimension_of_the_building_slab": {
                "field_name": "SLABY: Y dimension of the building slab",
                "field_type": "n"
            },
            "slabdepth_thickness_of_slab_on_grade": {
                "field_name": "SLABDEPTH: Thickness of slab on grade",
                "field_type": "n"
            },
            "clearance_distance_from_edge_of_slab_to_domain_edge": {
                "field_name": "CLEARANCE: Distance from edge of slab to domain edge",
                "field_type": "n"
            },
            "zclearance_distance_from_bottom_of_slab_to_domain_bottom": {
                "field_name": "ZCLEARANCE: Distance from bottom of slab to domain bottom",
                "field_type": "n"
            }
        },
        "fields": [
            "slabx_x_dimension_of_the_building_slab",
            "slaby_y_dimension_of_the_building_slab",
            "slabdepth_thickness_of_slab_on_grade",
            "clearance_distance_from_edge_of_slab_to_domain_edge",
            "zclearance_distance_from_bottom_of_slab_to_domain_bottom"
        ],
        "alphas": {
            "fields": []
        },
        "numerics": {
            "fields": [
                "slabx_x_dimension_of_the_building_slab",
                "slaby_y_dimension_of_the_building_slab",
                "slabdepth_thickness_of_slab_on_grade",
                "clearance_distance_from_edge_of_slab_to_domain_edge",
                "zclearance_distance_from_bottom_of_slab_to_domain_bottom"
            ]
        }
    },
    "type": "object",
    "memo": "AutoGrid only necessary when EquivalentSlab option not chosen. Not normally needed by EnergyPlus users. This object permits user selection of rectangular slab dimensions. NO SLAB DIMENSIONS LESS THAN 6 m."
}
```
