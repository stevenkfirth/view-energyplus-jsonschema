```
{
    "SurfaceProperties:VaporCoefficients": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "surface_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "SurfaceNames"
                        ]
                    },
                    "constant_external_vapor_transfer_coefficient": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No"
                    },
                    "external_vapor_coefficient_value": {
                        "type": "number",
                        "units": "kg/Pa-s-m2",
                        "default": 0.0,
                        "minimum": 0.0
                    },
                    "constant_internal_vapor_transfer_coefficient": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No"
                    },
                    "internal_vapor_coefficient_value": {
                        "type": "number",
                        "units": "kg/Pa-s-m2",
                        "default": 0.0,
                        "minimum": 0.0
                    }
                },
                "required": [
                    "surface_name"
                ]
            }
        },
        "group": "Advanced Construction, Surface, Zone Concepts",
        "legacy_idd": {
            "field_info": {
                "surface_name": {
                    "field_name": "Surface Name",
                    "field_type": "a"
                },
                "constant_external_vapor_transfer_coefficient": {
                    "field_name": "Constant External Vapor Transfer Coefficient",
                    "field_type": "a"
                },
                "external_vapor_coefficient_value": {
                    "field_name": "External Vapor Coefficient Value",
                    "field_type": "n"
                },
                "constant_internal_vapor_transfer_coefficient": {
                    "field_name": "Constant Internal vapor Transfer Coefficient",
                    "field_type": "a"
                },
                "internal_vapor_coefficient_value": {
                    "field_name": "Internal Vapor Coefficient Value",
                    "field_type": "n"
                }
            },
            "fields": [
                "surface_name",
                "constant_external_vapor_transfer_coefficient",
                "external_vapor_coefficient_value",
                "constant_internal_vapor_transfer_coefficient",
                "internal_vapor_coefficient_value"
            ],
            "alphas": {
                "fields": [
                    "surface_name",
                    "constant_external_vapor_transfer_coefficient",
                    "constant_internal_vapor_transfer_coefficient"
                ]
            },
            "numerics": {
                "fields": [
                    "external_vapor_coefficient_value",
                    "internal_vapor_coefficient_value"
                ]
            }
        },
        "type": "object",
        "memo": "The interior and external vapor transfer coefficients. Normally these value are calculated using the heat convection coefficient values. Use this object to used fixed constant values. Units are kg/Pa.s.m2 This will only work with the CombinedHeatAndMoistureFiniteElement algorithm for surfaces. Other algorithms will ignore these coefficients",
        "min_fields": 4.0
    }
}
```
