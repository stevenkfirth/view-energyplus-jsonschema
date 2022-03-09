```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "fuel_use_type": {
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
                        "NaturalGas",
                        "OtherFuel1",
                        "OtherFuel2",
                        "Propane",
                        "Steam",
                        "Water"
                    ]
                },
                "schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "units in schedule should be fraction applied to capacity of the exterior fuel equipment, generally (0.0 - 1.0)"
                },
                "design_level": {
                    "type": "number",
                    "units": "W",
                    "minimum": 0.0,
                    "ip-units": "W"
                },
                "end_use_subcategory": {
                    "type": "string",
                    "note": "Any text may be used here to categorize the end-uses in the ABUPS End Uses by Subcategory table.",
                    "retaincase": true,
                    "default": "General"
                }
            },
            "required": [
                "fuel_use_type",
                "schedule_name",
                "design_level"
            ]
        }
    },
    "group": "Exterior Equipment",
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
            "fuel_use_type": {
                "field_name": "Fuel Use Type",
                "field_type": "a"
            },
            "schedule_name": {
                "field_name": "Schedule Name",
                "field_type": "a"
            },
            "design_level": {
                "field_name": "Design Level",
                "field_type": "n"
            },
            "end_use_subcategory": {
                "field_name": "End-Use Subcategory",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "fuel_use_type",
            "schedule_name",
            "design_level",
            "end_use_subcategory"
        ],
        "alphas": {
            "fields": [
                "name",
                "fuel_use_type",
                "schedule_name",
                "end_use_subcategory"
            ]
        },
        "numerics": {
            "fields": [
                "design_level"
            ]
        }
    },
    "type": "object",
    "memo": "only used for Meter type reporting, does not affect building loads"
}
```
