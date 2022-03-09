```
{
    "WindowGap:SupportPillar": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "spacing": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "default": 0.04
                    },
                    "radius": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "default": 0.0004
                    }
                }
            }
        },
        "group": "Surface Construction Elements",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "WindowGapSupportPillars"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "spacing": {
                    "field_name": "Spacing",
                    "field_type": "n"
                },
                "radius": {
                    "field_name": "Radius",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "spacing",
                "radius"
            ],
            "alphas": {
                "fields": [
                    "name"
                ]
            },
            "numerics": {
                "fields": [
                    "spacing",
                    "radius"
                ]
            }
        },
        "type": "object",
        "memo": "used to define pillar geometry for support pillars"
    }
}
```
