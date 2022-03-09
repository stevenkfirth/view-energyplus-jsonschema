```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "ems_variable_name": {
                    "type": "string",
                    "note": "must be an acceptable EMS variable"
                },
                "type_of_data_in_variable": {
                    "type": "string",
                    "enum": [
                        "Averaged",
                        "Summed"
                    ]
                },
                "update_frequency": {
                    "type": "string",
                    "enum": [
                        "SystemTimestep",
                        "ZoneTimestep"
                    ]
                },
                "ems_program_or_subroutine_name": {
                    "type": "string",
                    "note": "optional for global scope variables, required for local scope variables"
                },
                "units": {
                    "type": "string",
                    "note": "optional but will result in dimensionless units for blank EnergyPlus units are standard SI units"
                }
            },
            "required": [
                "ems_variable_name",
                "type_of_data_in_variable",
                "update_frequency"
            ]
        }
    },
    "group": "Energy Management System (EMS)",
    "name": {
        "type": "string",
        "is_required": true,
        "retaincase": true
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "ems_variable_name": {
                "field_name": "EMS Variable Name",
                "field_type": "a"
            },
            "type_of_data_in_variable": {
                "field_name": "Type of Data in Variable",
                "field_type": "a"
            },
            "update_frequency": {
                "field_name": "Update Frequency",
                "field_type": "a"
            },
            "ems_program_or_subroutine_name": {
                "field_name": "EMS Program or Subroutine Name",
                "field_type": "a"
            },
            "units": {
                "field_name": "Units",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "ems_variable_name",
            "type_of_data_in_variable",
            "update_frequency",
            "ems_program_or_subroutine_name",
            "units"
        ],
        "alphas": {
            "fields": [
                "name",
                "ems_variable_name",
                "type_of_data_in_variable",
                "update_frequency",
                "ems_program_or_subroutine_name",
                "units"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "This object sets up an EnergyPlus output variable from an Erl variable",
    "min_fields": 4.0
}
```
