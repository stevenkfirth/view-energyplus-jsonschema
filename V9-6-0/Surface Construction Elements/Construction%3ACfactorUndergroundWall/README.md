```
{
    "Construction:CfactorUndergroundWall": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "c_factor": {
                        "type": "number",
                        "units": "W/m2-K",
                        "exclusiveMinimum": 0.0,
                        "note": "Enter C-Factor without film coefficients or soil"
                    },
                    "height": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "note": "Enter height of the underground wall"
                    }
                },
                "required": [
                    "c_factor",
                    "height"
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
                "c_factor": {
                    "field_name": "C-Factor",
                    "field_type": "n"
                },
                "height": {
                    "field_name": "Height",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "c_factor",
                "height"
            ],
            "alphas": {
                "fields": [
                    "name"
                ]
            },
            "numerics": {
                "fields": [
                    "c_factor",
                    "height"
                ]
            }
        },
        "type": "object",
        "memo": "Alternate method of describing underground wall constructions"
    }
}
```
