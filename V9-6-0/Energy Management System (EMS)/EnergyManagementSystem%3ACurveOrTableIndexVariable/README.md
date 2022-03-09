```
{
    "EnergyManagementSystem:CurveOrTableIndexVariable": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "curve_or_table_object_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions",
                            "MultivariateFunctions",
                            "QuadvariateFunctions",
                            "QuintvariateFunctions",
                            "TrivariateFunctions",
                            "UnivariateFunctions"
                        ]
                    }
                },
                "required": [
                    "curve_or_table_object_name"
                ]
            }
        },
        "group": "Energy Management System (EMS)",
        "name": {
            "type": "string",
            "is_required": true,
            "note": "This name becomes a variable for use in Erl programs no spaces allowed in name"
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "curve_or_table_object_name": {
                    "field_name": "Curve or Table Object Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "curve_or_table_object_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "curve_or_table_object_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "Declares EMS variable that identifies a curve or table",
        "min_fields": 2.0
    }
}
```
