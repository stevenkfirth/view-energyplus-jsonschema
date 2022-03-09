```
{
    "Daylighting:ReferencePoint": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "zone_or_space_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "SpaceNames",
                            "ZoneNames"
                        ]
                    },
                    "x_coordinate_of_reference_point": {
                        "type": "number",
                        "units": "m"
                    },
                    "y_coordinate_of_reference_point": {
                        "type": "number",
                        "units": "m"
                    },
                    "z_coordinate_of_reference_point": {
                        "type": "number",
                        "units": "m",
                        "default": 0.8
                    }
                },
                "required": [
                    "zone_or_space_name",
                    "x_coordinate_of_reference_point",
                    "y_coordinate_of_reference_point"
                ]
            }
        },
        "group": "Daylighting",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "DaylightReferencePointNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "zone_or_space_name": {
                    "field_name": "Zone or Space Name",
                    "field_type": "a"
                },
                "x_coordinate_of_reference_point": {
                    "field_name": "X-Coordinate of Reference Point",
                    "field_type": "n"
                },
                "y_coordinate_of_reference_point": {
                    "field_name": "Y-Coordinate of Reference Point",
                    "field_type": "n"
                },
                "z_coordinate_of_reference_point": {
                    "field_name": "Z-Coordinate of Reference Point",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "zone_or_space_name",
                "x_coordinate_of_reference_point",
                "y_coordinate_of_reference_point",
                "z_coordinate_of_reference_point"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "zone_or_space_name"
                ]
            },
            "numerics": {
                "fields": [
                    "x_coordinate_of_reference_point",
                    "y_coordinate_of_reference_point",
                    "z_coordinate_of_reference_point"
                ]
            }
        },
        "type": "object",
        "memo": "Used by Daylighting:Controls to identify the reference point coordinates for each sensor. Reference points are given in coordinates specified in the GlobalGeometryRules object Daylighting Reference Point CoordinateSystem field.",
        "min_fields": 5.0
    }
}
```
