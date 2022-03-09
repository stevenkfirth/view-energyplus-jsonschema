```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "x_position": {
                    "type": "number",
                    "units": "m",
                    "exclusiveMinimum": 0.0,
                    "note": "This segment will be centered at this distance from the x=0 domain surface or the basement wall surface, based on whether a basement exists in this domain and the selection of the shift input field found in the domain object."
                },
                "y_position": {
                    "type": "number",
                    "units": "m",
                    "exclusiveMinimum": 0.0,
                    "note": "This segment will be centered at this distance away from the ground surface; thus this value represents the burial depth of this pipe segment."
                },
                "flow_direction": {
                    "type": "string",
                    "enum": [
                        "DecreasingZ",
                        "IncreasingZ"
                    ],
                    "note": "This segment will be simulated such that the flow is in the selected direction. This can allow for detailed analysis of circuiting effects in a single domain."
                }
            },
            "required": [
                "x_position",
                "y_position",
                "flow_direction"
            ]
        }
    },
    "group": "Node-Branch Management",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "PipingSystemUndergroundSegmentNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "x_position": {
                "field_name": "X Position",
                "field_type": "n"
            },
            "y_position": {
                "field_name": "Y Position",
                "field_type": "n"
            },
            "flow_direction": {
                "field_name": "Flow Direction",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "x_position",
            "y_position",
            "flow_direction"
        ],
        "alphas": {
            "fields": [
                "name",
                "flow_direction"
            ]
        },
        "numerics": {
            "fields": [
                "x_position",
                "y_position"
            ]
        }
    },
    "type": "object",
    "memo": "The pipe segment to be used in an underground piping system This object represents a single pipe leg positioned axially in the local z-direction, at a given x, y location in the domain",
    "min_fields": 4.0
}
```
