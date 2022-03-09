```
{
    "GeometryTransform": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "plane_of_transform": {
                        "type": "string",
                        "enum": [
                            "",
                            "XY"
                        ],
                        "default": "XY",
                        "note": "only current allowed value is \"XY\""
                    },
                    "current_aspect_ratio": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "note": "Aspect ratio of building as described in idf"
                    },
                    "new_aspect_ratio": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "note": "Aspect ratio to transform to during run"
                    }
                },
                "required": [
                    "current_aspect_ratio",
                    "new_aspect_ratio"
                ]
            }
        },
        "group": "Thermal Zones and Surfaces",
        "legacy_idd": {
            "field_info": {
                "plane_of_transform": {
                    "field_name": "Plane of Transform",
                    "field_type": "a"
                },
                "current_aspect_ratio": {
                    "field_name": "Current Aspect Ratio",
                    "field_type": "n"
                },
                "new_aspect_ratio": {
                    "field_name": "New Aspect Ratio",
                    "field_type": "n"
                }
            },
            "fields": [
                "plane_of_transform",
                "current_aspect_ratio",
                "new_aspect_ratio"
            ],
            "alphas": {
                "fields": [
                    "plane_of_transform"
                ]
            },
            "numerics": {
                "fields": [
                    "current_aspect_ratio",
                    "new_aspect_ratio"
                ]
            }
        },
        "type": "object",
        "maxProperties": 1,
        "memo": "Provides a simple method of altering the footprint geometry of a model. The intent is to provide a single parameter that can be used to reshape the building description contained in the rest of the input file.",
        "min_fields": 3.0
    }
}
```
