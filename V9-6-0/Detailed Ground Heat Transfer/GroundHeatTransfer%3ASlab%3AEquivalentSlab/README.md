```
{
    "GroundHeatTransfer:Slab:EquivalentSlab": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "apratio_the_area_to_perimeter_ratio_for_this_slab": {
                        "type": "number",
                        "note": "Equivalent square slab is simulated,  side is 4*APRatio.",
                        "units": "m",
                        "minimum": 1.5,
                        "maximum": 22.0
                    },
                    "slabdepth_thickness_of_slab_on_grade": {
                        "type": "number",
                        "note": "This field specifies the thickness of the slab. The slab top surface is level with the ground surface, so this is the depth into the ground. The slab depth has a significant effect on the temperature calculation, and it is also important for the auto-grid process. The finite difference grids are set in such a way that they use the slab thickness to determine the vertical grid spacing. Autogridding will fail if the slab thickness is specified larger than 0.25 meters.",
                        "default": 0.1,
                        "units": "m"
                    },
                    "clearance_distance_from_edge_of_slab_to_domain_edge": {
                        "type": "number",
                        "note": "This field specifies the distance from the slab to the edge of the area that will be modeled with the grid system. It is the basic size dimension that is used to set the horizontal extent of the domain. 15 meters is a reasonable value.",
                        "default": 15.0,
                        "units": "m"
                    },
                    "zclearance_distance_from_bottom_of_slab_to_domain_bottom": {
                        "type": "number",
                        "note": "This field specifies the vertical distance from the slab to the bottom edge of the area that will be modeled with the grid system. 15 meters is a reasonable value.",
                        "default": 15.0,
                        "units": "m"
                    }
                },
                "required": [
                    "apratio_the_area_to_perimeter_ratio_for_this_slab"
                ]
            }
        },
        "group": "Detailed Ground Heat Transfer",
        "legacy_idd": {
            "field_info": {
                "apratio_the_area_to_perimeter_ratio_for_this_slab": {
                    "field_name": "APRatio: The area to perimeter ratio for this slab",
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
                "apratio_the_area_to_perimeter_ratio_for_this_slab",
                "slabdepth_thickness_of_slab_on_grade",
                "clearance_distance_from_edge_of_slab_to_domain_edge",
                "zclearance_distance_from_bottom_of_slab_to_domain_bottom"
            ],
            "alphas": {
                "fields": []
            },
            "numerics": {
                "fields": [
                    "apratio_the_area_to_perimeter_ratio_for_this_slab",
                    "slabdepth_thickness_of_slab_on_grade",
                    "clearance_distance_from_edge_of_slab_to_domain_edge",
                    "zclearance_distance_from_bottom_of_slab_to_domain_bottom"
                ]
            }
        },
        "type": "object",
        "memo": "Using an equivalent slab allows non-rectangular shapes to be modeled accurately. Object uses the area - perimeter (area/perimeter) ratio to determine the size of an equivalent rectangular slab. EnergyPlus users normally use this option."
    }
}
```
