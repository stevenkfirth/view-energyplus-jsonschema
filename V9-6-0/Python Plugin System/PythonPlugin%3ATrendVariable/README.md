```
{
    "PythonPlugin:TrendVariable": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "name_of_a_python_plugin_variable": {
                        "type": "string"
                    },
                    "number_of_timesteps_to_be_logged": {
                        "type": "number",
                        "minimum": 1.0
                    }
                },
                "required": [
                    "name_of_a_python_plugin_variable",
                    "number_of_timesteps_to_be_logged"
                ]
            }
        },
        "group": "Python Plugin System",
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
                "name_of_a_python_plugin_variable": {
                    "field_name": "Name of a Python Plugin Variable",
                    "field_type": "a"
                },
                "number_of_timesteps_to_be_logged": {
                    "field_name": "Number of Timesteps to be Logged",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "name_of_a_python_plugin_variable",
                "number_of_timesteps_to_be_logged"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "name_of_a_python_plugin_variable"
                ]
            },
            "numerics": {
                "fields": [
                    "number_of_timesteps_to_be_logged"
                ]
            }
        },
        "type": "object",
        "memo": "This object sets up a Python plugin trend variable from an Python plugin variable A trend variable logs values across timesteps",
        "min_fields": 3.0
    }
}
```
