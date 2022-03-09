```
{
    "SurfaceProperty:ExposedFoundationPerimeter": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "surface_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "FloorSurfaceNames"
                        ]
                    },
                    "exposed_perimeter_calculation_method": {
                        "type": "string",
                        "note": "Choices: TotalExposedPerimeter => total exposed perimeter in meters ExposedPerimeterFraction => fraction of total perimeter that is exposed. Value * Fraction = Total exposed perimeter BySegment => define whether the segment between each set of consecutive vertices of the floor surface is exposed. SUM(exposed segement lengths) = Total exposed perimeter",
                        "enum": [
                            "BySegment",
                            "ExposedPerimeterFraction",
                            "TotalExposedPerimeter"
                        ]
                    },
                    "total_exposed_perimeter": {
                        "type": "number",
                        "units": "m",
                        "minimum": 0.0
                    },
                    "exposed_perimeter_fraction": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 1.0
                    },
                    "surfaces": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "surface_segment_exposed": {
                                    "type": "string",
                                    "note": "Surface Segment N is the perimeter between the Nth and (N+1)th vertices",
                                    "default": "Yes",
                                    "enum": [
                                        "",
                                        "No",
                                        "Yes"
                                    ]
                                }
                            },
                            "type": "object"
                        }
                    }
                },
                "required": [
                    "surface_name",
                    "exposed_perimeter_calculation_method"
                ]
            }
        },
        "group": "Advanced Construction, Surface, Zone Concepts",
        "legacy_idd": {
            "field_info": {
                "surface_name": {
                    "field_name": "Surface Name",
                    "field_type": "a"
                },
                "exposed_perimeter_calculation_method": {
                    "field_name": "Exposed Perimeter Calculation Method",
                    "field_type": "a"
                },
                "total_exposed_perimeter": {
                    "field_name": "Total Exposed Perimeter",
                    "field_type": "n"
                },
                "exposed_perimeter_fraction": {
                    "field_name": "Exposed Perimeter Fraction",
                    "field_type": "n"
                },
                "surface_segment_exposed": {
                    "field_name": "Surface Segment Exposed",
                    "field_type": "a"
                }
            },
            "fields": [
                "surface_name",
                "exposed_perimeter_calculation_method",
                "total_exposed_perimeter",
                "exposed_perimeter_fraction"
            ],
            "alphas": {
                "fields": [
                    "surface_name",
                    "exposed_perimeter_calculation_method"
                ],
                "extensions": [
                    "surface_segment_exposed"
                ]
            },
            "numerics": {
                "fields": [
                    "total_exposed_perimeter",
                    "exposed_perimeter_fraction"
                ]
            },
            "extensibles": [
                "surface_segment_exposed"
            ],
            "extension": "surfaces"
        },
        "type": "object",
        "memo": "Defines the perimeter of a foundation floor that is exposed to the exterior environment through the floor. User may either define the total exposed perimeter, fraction of perimeter exposed or individually define which segments of the floor surface perimeter are exposed.",
        "extensible_size": 1.0
    }
}
```
