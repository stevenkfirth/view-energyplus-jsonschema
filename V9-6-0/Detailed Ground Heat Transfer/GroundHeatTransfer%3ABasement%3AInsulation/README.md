```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "rext_r_value_of_any_exterior_insulation": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "units": "m2-K/W"
                },
                "insfull_flag_is_the_wall_fully_insulated_": {
                    "type": "string",
                    "enum": [
                        "FALSE",
                        "TRUE"
                    ],
                    "note": "True for full insulation False for insulation half way down side wall from grade line"
                }
            },
            "required": [
                "insfull_flag_is_the_wall_fully_insulated_"
            ]
        }
    },
    "group": "Detailed Ground Heat Transfer",
    "legacy_idd": {
        "field_info": {
            "rext_r_value_of_any_exterior_insulation": {
                "field_name": "REXT: R Value of any exterior insulation",
                "field_type": "n"
            },
            "insfull_flag_is_the_wall_fully_insulated_": {
                "field_name": "INSFULL: Flag: Is the wall fully insulated?",
                "field_type": "a"
            }
        },
        "fields": [
            "rext_r_value_of_any_exterior_insulation",
            "insfull_flag_is_the_wall_fully_insulated_"
        ],
        "alphas": {
            "fields": [
                "insfull_flag_is_the_wall_fully_insulated_"
            ]
        },
        "numerics": {
            "fields": [
                "rext_r_value_of_any_exterior_insulation"
            ]
        }
    },
    "type": "object",
    "memo": "Describes the insulation used on an exterior basement wall for the Basement preprocessor ground heat transfer simulation."
}
```
