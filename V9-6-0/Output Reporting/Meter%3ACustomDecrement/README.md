```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "resource_type": {
                    "type": "string",
                    "enum": [
                        "Coal",
                        "Diesel",
                        "DistrictCooling",
                        "DistrictHeating",
                        "Electricity",
                        "FuelOilNo1",
                        "FuelOilNo2",
                        "Gasoline",
                        "Generic",
                        "NaturalGas",
                        "OtherFuel1",
                        "OtherFuel2",
                        "Propane",
                        "Steam",
                        "Water"
                    ]
                },
                "source_meter_name": {
                    "type": "string"
                },
                "variable_details": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "key_name": {
                                "type": "string"
                            },
                            "output_variable_or_meter_name": {
                                "type": "string"
                            }
                        },
                        "type": "object"
                    }
                }
            },
            "required": [
                "source_meter_name"
            ]
        }
    },
    "group": "Output Reporting",
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
            "resource_type": {
                "field_name": "Resource Type",
                "field_type": "a"
            },
            "source_meter_name": {
                "field_name": "Source Meter Name",
                "field_type": "a"
            },
            "key_name": {
                "field_name": "Key Name",
                "field_type": "a"
            },
            "output_variable_or_meter_name": {
                "field_name": "Output Variable or Meter Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "resource_type",
            "source_meter_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "resource_type",
                "source_meter_name"
            ],
            "extensions": [
                "key_name",
                "output_variable_or_meter_name"
            ]
        },
        "numerics": {
            "fields": []
        },
        "extensibles": [
            "key_name",
            "output_variable_or_meter_name"
        ],
        "extension": "variable_details"
    },
    "type": "object",
    "memo": "Used to allow users to combine specific variables and/or meters into \"custom\" meter configurations. To access these meters by name, one must first run a simulation to generate the RDD/MDD files and names.",
    "extensible_size": 2.0
}
```
