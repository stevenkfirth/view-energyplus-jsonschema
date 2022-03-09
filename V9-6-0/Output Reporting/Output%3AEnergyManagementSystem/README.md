```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "actuator_availability_dictionary_reporting": {
                    "type": "string",
                    "enum": [
                        "",
                        "None",
                        "NotByUniqueKeyNames",
                        "Verbose"
                    ],
                    "default": "None"
                },
                "internal_variable_availability_dictionary_reporting": {
                    "type": "string",
                    "enum": [
                        "",
                        "None",
                        "NotByUniqueKeyNames",
                        "Verbose"
                    ],
                    "default": "None"
                },
                "ems_runtime_language_debug_output_level": {
                    "type": "string",
                    "enum": [
                        "",
                        "ErrorsOnly",
                        "None",
                        "Verbose"
                    ],
                    "default": "None"
                }
            }
        }
    },
    "group": "Output Reporting",
    "legacy_idd": {
        "field_info": {
            "actuator_availability_dictionary_reporting": {
                "field_name": "Actuator Availability Dictionary Reporting",
                "field_type": "a"
            },
            "internal_variable_availability_dictionary_reporting": {
                "field_name": "Internal Variable Availability Dictionary Reporting",
                "field_type": "a"
            },
            "ems_runtime_language_debug_output_level": {
                "field_name": "EMS Runtime Language Debug Output Level",
                "field_type": "a"
            }
        },
        "fields": [
            "actuator_availability_dictionary_reporting",
            "internal_variable_availability_dictionary_reporting",
            "ems_runtime_language_debug_output_level"
        ],
        "alphas": {
            "fields": [
                "actuator_availability_dictionary_reporting",
                "internal_variable_availability_dictionary_reporting",
                "ems_runtime_language_debug_output_level"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "maxProperties": 1,
    "memo": "This object is used to control the output produced by the Energy Management System"
}
```
