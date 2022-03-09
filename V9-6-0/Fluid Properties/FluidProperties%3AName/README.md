```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "fluid_name": {
                    "type": "string",
                    "reference": [
                        "FluidAndGlycolNames",
                        "FluidNames"
                    ]
                },
                "fluid_type": {
                    "type": "string",
                    "enum": [
                        "Glycol",
                        "Refrigerant"
                    ]
                }
            },
            "required": [
                "fluid_name",
                "fluid_type"
            ]
        }
    },
    "group": "Fluid Properties",
    "legacy_idd": {
        "field_info": {
            "fluid_name": {
                "field_name": "Fluid Name",
                "field_type": "a"
            },
            "fluid_type": {
                "field_name": "Fluid Type",
                "field_type": "a"
            }
        },
        "fields": [
            "fluid_name",
            "fluid_type"
        ],
        "alphas": {
            "fields": [
                "fluid_name",
                "fluid_type"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "potential fluid name/type in the input file repeat this object for each fluid"
}
```
