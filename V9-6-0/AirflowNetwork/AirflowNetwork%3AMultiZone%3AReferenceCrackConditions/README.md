```
{
    "AirflowNetwork:MultiZone:ReferenceCrackConditions": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "reference_temperature": {
                        "type": "number",
                        "units": "C",
                        "note": "Enter the reference temperature under which the surface crack data were obtained.  Suggested value 20C."
                    },
                    "reference_barometric_pressure": {
                        "type": "number",
                        "units": "Pa",
                        "default": 101325.0,
                        "minimum": 31000.0,
                        "maximum": 120000.0,
                        "ip-units": "inHg",
                        "note": "Enter the reference barometric pressure under which the surface crack data were obtained."
                    },
                    "reference_humidity_ratio": {
                        "type": "number",
                        "units": "kgWater/kgDryAir",
                        "default": 0.0,
                        "note": "Enter the reference humidity ratio under which the surface crack data were obtained."
                    }
                },
                "required": [
                    "reference_temperature"
                ]
            }
        },
        "group": "AirflowNetwork",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "ReferenceCrackConditions"
            ],
            "note": "Enter a unique name for this object."
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "reference_temperature": {
                    "field_name": "Reference Temperature",
                    "field_type": "n"
                },
                "reference_barometric_pressure": {
                    "field_name": "Reference Barometric Pressure",
                    "field_type": "n"
                },
                "reference_humidity_ratio": {
                    "field_name": "Reference Humidity Ratio",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "reference_temperature",
                "reference_barometric_pressure",
                "reference_humidity_ratio"
            ],
            "alphas": {
                "fields": [
                    "name"
                ]
            },
            "numerics": {
                "fields": [
                    "reference_temperature",
                    "reference_barometric_pressure",
                    "reference_humidity_ratio"
                ]
            }
        },
        "type": "object",
        "memo": "This object specifies the conditions under which the air mass flow coefficient was measured.",
        "min_fields": 4.0
    }
}
```
