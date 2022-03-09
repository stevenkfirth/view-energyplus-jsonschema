```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "terminal_unit_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "reference": [
                        "AirflowNetworkComponentNames"
                    ],
                    "object_list": [
                        "AFNTerminalUnitNames"
                    ],
                    "note": "Enter the name of a terminal unit in the AirLoopHVAC."
                },
                "terminal_unit_object_type": {
                    "type": "string",
                    "enum": [
                        "AirTerminal:SingleDuct:ConstantVolume:Reheat",
                        "AirTerminal:SingleDuct:VAV:Reheat"
                    ],
                    "note": "Select the type of terminal unit corresponding to the name entered in the field above."
                },
                "air_path_length": {
                    "type": "number",
                    "units": "m",
                    "exclusiveMinimum": 0.0,
                    "note": "Enter the air path length (depth) for the terminal unit."
                },
                "air_path_hydraulic_diameter": {
                    "type": "number",
                    "units": "m",
                    "exclusiveMinimum": 0.0,
                    "note": "Enter the hydraulic diameter of this terminal unit. The hydraulic diameter is defined as 4 multiplied by the cross section area divided by perimeter."
                }
            },
            "required": [
                "terminal_unit_name",
                "terminal_unit_object_type",
                "air_path_length",
                "air_path_hydraulic_diameter"
            ]
        }
    },
    "group": "AirflowNetwork",
    "legacy_idd": {
        "field_info": {
            "terminal_unit_name": {
                "field_name": "Terminal Unit Name",
                "field_type": "a"
            },
            "terminal_unit_object_type": {
                "field_name": "Terminal Unit Object Type",
                "field_type": "a"
            },
            "air_path_length": {
                "field_name": "Air Path Length",
                "field_type": "n"
            },
            "air_path_hydraulic_diameter": {
                "field_name": "Air Path Hydraulic Diameter",
                "field_type": "n"
            }
        },
        "fields": [
            "terminal_unit_name",
            "terminal_unit_object_type",
            "air_path_length",
            "air_path_hydraulic_diameter"
        ],
        "alphas": {
            "fields": [
                "terminal_unit_name",
                "terminal_unit_object_type"
            ]
        },
        "numerics": {
            "fields": [
                "air_path_length",
                "air_path_hydraulic_diameter"
            ]
        }
    },
    "type": "object",
    "memo": "This object defines the name of a terminal unit in an air loop.",
    "min_fields": 4.0
}
```
