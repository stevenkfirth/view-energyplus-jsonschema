```
{
    "Construction:FfactorGroundFloor": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "f_factor": {
                        "type": "number",
                        "units": "W/m-K",
                        "ip-units": "Btu/h-ft-F",
                        "exclusiveMinimum": 0.0
                    },
                    "area": {
                        "type": "number",
                        "units": "m2",
                        "exclusiveMinimum": 0.0,
                        "note": "Enter area of the floor"
                    },
                    "perimeterexposed": {
                        "type": "number",
                        "units": "m",
                        "minimum": 0.0,
                        "note": "Enter exposed perimeter of the floor"
                    }
                },
                "required": [
                    "f_factor",
                    "area",
                    "perimeterexposed"
                ]
            }
        },
        "group": "Surface Construction Elements",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "ConstructionNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "f_factor": {
                    "field_name": "F-Factor",
                    "field_type": "n"
                },
                "area": {
                    "field_name": "Area",
                    "field_type": "n"
                },
                "perimeterexposed": {
                    "field_name": "PerimeterExposed",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "f_factor",
                "area",
                "perimeterexposed"
            ],
            "alphas": {
                "fields": [
                    "name"
                ]
            },
            "numerics": {
                "fields": [
                    "f_factor",
                    "area",
                    "perimeterexposed"
                ]
            }
        },
        "type": "object",
        "memo": "Alternate method of describing slab-on-grade or underground floor constructions"
    }
}
```
