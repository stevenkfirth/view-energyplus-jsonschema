```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "add_current_working_directory_to_search_path": {
                    "type": "string",
                    "note": "Adding the current working directory allows Python to find plugin scripts in the current directory.",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "Yes"
                },
                "add_input_file_directory_to_search_path": {
                    "type": "string",
                    "note": "Enabling this will allow Python to find plugin scripts in the same directory as the running input file, even if that is not the current working directory.",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "Yes"
                },
                "py_search_paths": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "search_path": {
                                "type": "string",
                                "retaincase": true
                            }
                        },
                        "type": "object"
                    }
                }
            }
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
            "add_current_working_directory_to_search_path": {
                "field_name": "Add Current Working Directory to Search Path",
                "field_type": "a"
            },
            "add_input_file_directory_to_search_path": {
                "field_name": "Add Input File Directory to Search Path",
                "field_type": "a"
            },
            "search_path": {
                "field_name": "Search Path",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "add_current_working_directory_to_search_path",
            "add_input_file_directory_to_search_path"
        ],
        "alphas": {
            "fields": [
                "name",
                "add_current_working_directory_to_search_path",
                "add_input_file_directory_to_search_path"
            ],
            "extensions": [
                "search_path"
            ]
        },
        "numerics": {
            "fields": []
        },
        "extensibles": [
            "search_path"
        ],
        "extension": "py_search_paths"
    },
    "type": "object",
    "maxProperties": 1,
    "memo": "Add directories to the search path for Python plugin modules The directory containing the EnergyPlus executable file is automatically added so that the Python interpreter can find the packaged up pyenergyplus Python package. By default, the current working directory and input file directory are also added to the search path. However, this object allows modifying this behavior. With this object, searching these directories can be disabled, and users can add supplemental search paths that point to libraries of plugin scripts.",
    "min_fields": 1.0,
    "extensible_size": 1.0
}
```
