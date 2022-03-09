```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "air_flow_value": {
                    "type": "number",
                    "unitsBasedOnField": "air_flow_units",
                    "note": "Enter the specified flow rate."
                },
                "air_flow_units": {
                    "type": "string",
                    "enum": [
                        "",
                        "MassFlow",
                        "VolumetricFlow"
                    ],
                    "default": "MassFlow",
                    "note": "Enter the units of the air flow value. VolumetricFlow (m3/s) MassFlow (kg/s)"
                }
            },
            "required": [
                "air_flow_value"
            ]
        }
    },
    "group": "AirflowNetwork",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "SurfaceAirflowLeakageNames"
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
            "air_flow_value": {
                "field_name": "Air Flow Value",
                "field_type": "n"
            },
            "air_flow_units": {
                "field_name": "Air Flow Units",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "air_flow_value",
            "air_flow_units"
        ],
        "alphas": {
            "fields": [
                "name",
                "air_flow_units"
            ]
        },
        "numerics": {
            "fields": [
                "air_flow_value"
            ]
        }
    },
    "type": "object",
    "memo": "This object is used to define specified flow through a linkage.",
    "min_fields": 2.0
}
```
