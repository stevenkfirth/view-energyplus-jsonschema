```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "algorithm": {
                    "type": "string",
                    "enum": [
                        "",
                        "Alternation",
                        "Bisection",
                        "BisectionThenRegulaFalsi",
                        "RegulaFalsi",
                        "RegulaFalsiThenBisection"
                    ],
                    "default": "RegulaFalsi"
                },
                "number_of_iterations_before_algorithm_switch": {
                    "type": "number",
                    "note": "This field is used when RegulaFalsiThenBisection or BisectionThenRegulaFalsi is entered. When iteration number is greater than the value, algorithm switches.",
                    "default": 5.0
                }
            }
        }
    },
    "group": "Simulation Parameters",
    "legacy_idd": {
        "field_info": {
            "algorithm": {
                "field_name": "Algorithm",
                "field_type": "a"
            },
            "number_of_iterations_before_algorithm_switch": {
                "field_name": "Number of Iterations Before Algorithm Switch",
                "field_type": "n"
            }
        },
        "fields": [
            "algorithm",
            "number_of_iterations_before_algorithm_switch"
        ],
        "alphas": {
            "fields": [
                "algorithm"
            ]
        },
        "numerics": {
            "fields": [
                "number_of_iterations_before_algorithm_switch"
            ]
        }
    },
    "type": "object",
    "maxProperties": 1,
    "memo": "Specifies a HVAC system solver algorithm to find a root"
}
```
