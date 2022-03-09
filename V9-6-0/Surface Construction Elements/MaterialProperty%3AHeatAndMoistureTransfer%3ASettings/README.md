```
{
    "MaterialProperty:HeatAndMoistureTransfer:Settings": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "material_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "MaterialName"
                        ],
                        "note": "Material Name that the moisture properties will be added to. This augments material properties needed for combined heat and moisture transfer for surfaces."
                    },
                    "porosity": {
                        "type": "number",
                        "units": "m3/m3",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "initial_water_content_ratio": {
                        "type": "number",
                        "note": "units are the water/material density ratio at the beginning of each run period.",
                        "units": "kg/kg",
                        "minimum": 0.0,
                        "default": 0.2
                    }
                },
                "required": [
                    "material_name",
                    "porosity"
                ]
            }
        },
        "group": "Surface Construction Elements",
        "legacy_idd": {
            "field_info": {
                "material_name": {
                    "field_name": "Material Name",
                    "field_type": "a"
                },
                "porosity": {
                    "field_name": "Porosity",
                    "field_type": "n"
                },
                "initial_water_content_ratio": {
                    "field_name": "Initial Water Content Ratio",
                    "field_type": "n"
                }
            },
            "fields": [
                "material_name",
                "porosity",
                "initial_water_content_ratio"
            ],
            "alphas": {
                "fields": [
                    "material_name"
                ]
            },
            "numerics": {
                "fields": [
                    "porosity",
                    "initial_water_content_ratio"
                ]
            }
        },
        "type": "object",
        "memo": "HeatBalanceAlgorithm = CombinedHeatAndMoistureFiniteElement solution algorithm only. Additional material properties for surfaces. Has no effect with other HeatBalanceAlgorithm solution algorithms",
        "min_fields": 3.0
    }
}
```
