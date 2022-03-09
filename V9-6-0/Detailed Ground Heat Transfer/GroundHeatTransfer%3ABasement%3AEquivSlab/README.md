```
{
    "GroundHeatTransfer:Basement:EquivSlab": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "apratio_the_area_to_perimeter_ratio_for_this_slab": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "m"
                    },
                    "equivsizing_flag": {
                        "type": "string",
                        "enum": [
                            "FALSE",
                            "TRUE"
                        ],
                        "note": "Will the dimensions of an equivalent slab be calculated (TRUE) or will the dimensions be input directly? (FALSE)] Only advanced special simulations should use FALSE."
                    }
                },
                "required": [
                    "apratio_the_area_to_perimeter_ratio_for_this_slab",
                    "equivsizing_flag"
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
                "equivsizing_flag": {
                    "field_name": "EquivSizing: Flag",
                    "field_type": "a"
                }
            },
            "fields": [
                "apratio_the_area_to_perimeter_ratio_for_this_slab",
                "equivsizing_flag"
            ],
            "alphas": {
                "fields": [
                    "equivsizing_flag"
                ]
            },
            "numerics": {
                "fields": [
                    "apratio_the_area_to_perimeter_ratio_for_this_slab"
                ]
            }
        },
        "type": "object",
        "memo": "Using an equivalent slab allows non-rectangular shapes to be modeled accurately. The simulation default should be EquivSizing=True"
    }
}
```
