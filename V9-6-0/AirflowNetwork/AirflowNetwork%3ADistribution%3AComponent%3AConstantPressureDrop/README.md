```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "pressure_difference_across_the_component": {
                    "type": "number",
                    "units": "Pa",
                    "exclusiveMinimum": 0.0,
                    "note": "Enter the pressure drop across this component."
                }
            },
            "required": [
                "pressure_difference_across_the_component"
            ]
        }
    },
    "group": "AirflowNetwork",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "AirflowNetworkComponentNames"
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
            "pressure_difference_across_the_component": {
                "field_name": "Pressure Difference Across the Component",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "pressure_difference_across_the_component"
        ],
        "alphas": {
            "fields": [
                "name"
            ]
        },
        "numerics": {
            "fields": [
                "pressure_difference_across_the_component"
            ]
        }
    },
    "type": "object",
    "memo": "This object defines the characteristics of a constant pressure drop component (e.g. filter). Each node connected to this object can not be a node of mixer, splitter, a node of air primary loop, or zone equipment loop. It is recommended to connect to a duct component at both ends.",
    "min_fields": 2.0
}
```
