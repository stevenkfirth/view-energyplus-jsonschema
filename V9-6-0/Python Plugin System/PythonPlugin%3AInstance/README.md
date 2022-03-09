```
{
    "PythonPlugin:Instance": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "run_during_warmup_days": {
                        "type": "string",
                        "note": "If this field is enabled, the plugin will be executed during warmup days, otherwise it will only be executed once warmup is completed and the actual run period begins",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No"
                    },
                    "python_module_name": {
                        "type": "string",
                        "note": "This is the name of the Python file, without a file extension. For \"plugin_b.py\", use just \"plugin_b\". The Python plugin file must be on the plugin system search path to be found during a simulation Additional directories can be added to the search path using the PythonPlugin:SearchPaths object"
                    },
                    "plugin_class_name": {
                        "type": "string",
                        "note": "This is the name of the class to be executed as a plugin during a simulation The class must inherit the EnergyPlusPlugin base class"
                    }
                },
                "required": [
                    "python_module_name",
                    "plugin_class_name"
                ]
            }
        },
        "group": "Python Plugin System",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "ProgramNames"
            ],
            "note": "This is the name used to represent this plugin in traditional EMS fields"
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "run_during_warmup_days": {
                    "field_name": "Run During Warmup Days",
                    "field_type": "a"
                },
                "python_module_name": {
                    "field_name": "Python Module Name",
                    "field_type": "a"
                },
                "plugin_class_name": {
                    "field_name": "Plugin Class Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "run_during_warmup_days",
                "python_module_name",
                "plugin_class_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "run_during_warmup_days",
                    "python_module_name",
                    "plugin_class_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "A single plugin to be executed during the simulation, which can contain multiple calling points for the same class instance by overriding multiple calling point methods.",
        "min_fields": 4.0
    }
}
```
