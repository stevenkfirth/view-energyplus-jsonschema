```
{
    "Material:AirGap": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "thermal_resistance": {
                        "type": "number",
                        "units": "m2-K/W",
                        "exclusiveMinimum": 0.0
                    }
                },
                "required": [
                    "thermal_resistance"
                ]
            }
        },
        "group": "Surface Construction Elements",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "MaterialName"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "thermal_resistance": {
                    "field_name": "Thermal Resistance",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "thermal_resistance"
            ],
            "alphas": {
                "fields": [
                    "name"
                ]
            },
            "numerics": {
                "fields": [
                    "thermal_resistance"
                ]
            }
        },
        "type": "object",
        "memo": "Air Space in Opaque Construction",
        "min_fields": 2.0
    }
}
```
