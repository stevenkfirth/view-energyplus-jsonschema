```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "latitude": {
                    "type": "number",
                    "units": "deg",
                    "minimum": -90.0,
                    "maximum": 90.0,
                    "default": 0.0,
                    "note": "+ is North, - is South, degree minutes represented in decimal (i.e. 30 minutes is .5)"
                },
                "longitude": {
                    "type": "number",
                    "units": "deg",
                    "minimum": -180.0,
                    "maximum": 180.0,
                    "default": 0.0,
                    "note": "- is West, + is East, degree minutes represented in decimal (i.e. 30 minutes is .5)"
                },
                "time_zone": {
                    "type": "number",
                    "note": "basic these limits on the WorldTimeZone Map (2003) Time relative to GMT. Decimal hours.",
                    "units": "hr",
                    "minimum": -12.0,
                    "maximum": 14.0,
                    "default": 0.0
                },
                "elevation": {
                    "type": "number",
                    "units": "m",
                    "minimum": -300.0,
                    "exclusiveMaximum": 8900.0,
                    "default": 0.0
                }
            }
        }
    },
    "group": "Location and Climate",
    "name": {
        "type": "string",
        "is_required": true
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "latitude": {
                "field_name": "Latitude",
                "field_type": "n"
            },
            "longitude": {
                "field_name": "Longitude",
                "field_type": "n"
            },
            "time_zone": {
                "field_name": "Time Zone",
                "field_type": "n"
            },
            "elevation": {
                "field_name": "Elevation",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "latitude",
            "longitude",
            "time_zone",
            "elevation"
        ],
        "alphas": {
            "fields": [
                "name"
            ]
        },
        "numerics": {
            "fields": [
                "latitude",
                "longitude",
                "time_zone",
                "elevation"
            ]
        }
    },
    "type": "object",
    "maxProperties": 1,
    "memo": "Specifies the building's location. Only one location is allowed. Weather data file location, if it exists, will override this object.",
    "min_fields": 5.0
}
```
