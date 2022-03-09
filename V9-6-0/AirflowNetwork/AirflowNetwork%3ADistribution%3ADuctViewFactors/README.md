```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "linkage_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "AirflowNetworkComponentNames"
                    ]
                },
                "duct_surface_exposure_fraction": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0
                },
                "duct_surface_emittance": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.9
                },
                "surfaces": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "surface_name": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "AllHeatTranSurfNames"
                                ]
                            },
                            "surface_view_factor": {
                                "type": "number",
                                "minimum": 0.0,
                                "maximum": 1.0
                            }
                        },
                        "type": "object"
                    }
                }
            },
            "required": [
                "linkage_name"
            ]
        }
    },
    "group": "AirflowNetwork",
    "legacy_idd": {
        "field_info": {
            "linkage_name": {
                "field_name": "Linkage Name",
                "field_type": "a"
            },
            "duct_surface_exposure_fraction": {
                "field_name": "Duct Surface Exposure Fraction",
                "field_type": "n"
            },
            "duct_surface_emittance": {
                "field_name": "Duct Surface Emittance",
                "field_type": "n"
            },
            "surface_name": {
                "field_name": "Surface Name",
                "field_type": "a"
            },
            "surface_view_factor": {
                "field_name": "Surface View Factor",
                "field_type": "n"
            }
        },
        "fields": [
            "linkage_name",
            "duct_surface_exposure_fraction",
            "duct_surface_emittance"
        ],
        "alphas": {
            "fields": [
                "linkage_name"
            ],
            "extensions": [
                "surface_name"
            ]
        },
        "numerics": {
            "fields": [
                "duct_surface_exposure_fraction",
                "duct_surface_emittance"
            ],
            "extensions": [
                "surface_view_factor"
            ]
        },
        "extensibles": [
            "surface_name",
            "surface_view_factor"
        ],
        "extension": "surfaces"
    },
    "type": "object",
    "memo": "This object is used to allow user-defined view factors to be used for duct-surface radiation calculations.",
    "extensible_size": 2.0
}
```
