```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "glycol_type": {
                    "type": "string",
                    "enum": [
                        "EthyleneGlycol",
                        "PropyleneGlycol",
                        "UserDefinedGlycolType"
                    ],
                    "note": "or UserDefined Fluid (must show up as a glycol in FluidProperties:Name object)"
                },
                "user_defined_glycol_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "FluidAndGlycolNames"
                    ]
                },
                "glycol_concentration": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                }
            },
            "required": [
                "glycol_type"
            ]
        }
    },
    "group": "Fluid Properties",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "FluidAndGlycolNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "glycol_type": {
                "field_name": "Glycol Type",
                "field_type": "a"
            },
            "user_defined_glycol_name": {
                "field_name": "User Defined Glycol Name",
                "field_type": "a"
            },
            "glycol_concentration": {
                "field_name": "Glycol Concentration",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "glycol_type",
            "user_defined_glycol_name",
            "glycol_concentration"
        ],
        "alphas": {
            "fields": [
                "name",
                "glycol_type",
                "user_defined_glycol_name"
            ]
        },
        "numerics": {
            "fields": [
                "glycol_concentration"
            ]
        }
    },
    "type": "object",
    "memo": "glycol and what concentration it is"
}
```
