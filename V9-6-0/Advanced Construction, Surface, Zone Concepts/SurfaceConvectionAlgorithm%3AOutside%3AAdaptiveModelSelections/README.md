```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "wind_convection_windward_vertical_wall_equation_source": {
                    "type": "string",
                    "default": "TARPWindward",
                    "enum": [
                        "",
                        "BlockenWindward",
                        "DOE2Windward",
                        "EmmelVertical",
                        "McAdams",
                        "Mitchell",
                        "MoWiTTWindward",
                        "NusseltJurges",
                        "SimpleCombined",
                        "TARPWindward",
                        "UserCurve"
                    ]
                },
                "wind_convection_windward_equation_vertical_wall_user_curve_name": {
                    "type": "string",
                    "note": "The SurfaceConvectionAlgorithm:Outside:UserCurve named in this field is used when the previous field is set to UserCurve",
                    "data_type": "object_list",
                    "object_list": [
                        "UserConvectionOutsideModels"
                    ]
                },
                "wind_convection_leeward_vertical_wall_equation_source": {
                    "type": "string",
                    "default": "TARPLeeward",
                    "enum": [
                        "",
                        "DOE2Leeward",
                        "EmmelVertical",
                        "McAdams",
                        "Mitchell",
                        "MoWiTTLeeward",
                        "NusseltJurges",
                        "SimpleCombined",
                        "TARPLeeward",
                        "UserCurve"
                    ]
                },
                "wind_convection_leeward_vertical_wall_equation_user_curve_name": {
                    "type": "string",
                    "note": "The SurfaceConvectionAlgorithm:Outside:UserCurve named in this field is used when the previous field is set to UserCurve",
                    "data_type": "object_list",
                    "object_list": [
                        "UserConvectionOutsideModels"
                    ]
                },
                "wind_convection_horizontal_roof_equation_source": {
                    "type": "string",
                    "default": "ClearRoof",
                    "enum": [
                        "",
                        "BlockenWindward",
                        "ClearRoof",
                        "DOE2Windward",
                        "EmmelRoof",
                        "McAdams",
                        "Mitchell",
                        "MoWiTTWindward",
                        "NusseltJurges",
                        "SimpleCombined",
                        "TARPWindward",
                        "UserCurve"
                    ]
                },
                "wind_convection_horizontal_roof_user_curve_name": {
                    "type": "string",
                    "note": "The SurfaceConvectionAlgorithm:Outside:UserCurve named in this field is used when the previous field is set to UserCurve",
                    "data_type": "object_list",
                    "object_list": [
                        "UserConvectionOutsideModels"
                    ]
                },
                "natural_convection_vertical_wall_equation_source": {
                    "type": "string",
                    "note": "This is for vertical walls",
                    "default": "ASHRAEVerticalWall",
                    "enum": [
                        "",
                        "ASHRAEVerticalWall",
                        "AlamdariHammondVerticalWall",
                        "FohannoPolidoriVerticalWall",
                        "ISO15099Windows",
                        "None",
                        "UserCurve"
                    ]
                },
                "natural_convection_vertical_wall_equation_user_curve_name": {
                    "type": "string",
                    "note": "The SurfaceConvectionAlgorithm:Outside:UserCurve named in this field is used when the previous field is set to UserCurve",
                    "data_type": "object_list",
                    "object_list": [
                        "UserConvectionOutsideModels"
                    ]
                },
                "natural_convection_stable_horizontal_equation_source": {
                    "type": "string",
                    "note": "This is for horizontal surfaces with heat flow directed for stable thermal stratification",
                    "default": "WaltonStableHorizontalOrTilt",
                    "enum": [
                        "",
                        "AlamdariHammondStableHorizontal",
                        "None",
                        "UserCurve",
                        "WaltonStableHorizontalOrTilt"
                    ]
                },
                "natural_convection_stable_horizontal_equation_user_curve_name": {
                    "type": "string",
                    "note": "The SurfaceConvectionAlgorithm:Outside:UserCurve named in this field is used when the previous field is set to UserCurve",
                    "data_type": "object_list",
                    "object_list": [
                        "UserConvectionOutsideModels"
                    ]
                },
                "natural_convection_unstable_horizontal_equation_source": {
                    "type": "string",
                    "default": "WaltonUnstableHorizontalOrTilt",
                    "enum": [
                        "",
                        "AlamdariHammondUnstableHorizontal",
                        "None",
                        "UserCurve",
                        "WaltonUnstableHorizontalOrTilt"
                    ]
                },
                "natural_convection_unstable_horizontal_equation_user_curve_name": {
                    "type": "string",
                    "note": "The SurfaceConvectionAlgorithm:Outside:UserCurve named in this field is used when the previous field is set to UserCurve",
                    "data_type": "object_list",
                    "object_list": [
                        "UserConvectionOutsideModels"
                    ]
                }
            }
        }
    },
    "group": "Advanced Construction, Surface, Zone Concepts",
    "name": {
        "type": "string"
    },
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "wind_convection_windward_vertical_wall_equation_source": {
                "field_name": "Wind Convection Windward Vertical Wall Equation Source",
                "field_type": "a"
            },
            "wind_convection_windward_equation_vertical_wall_user_curve_name": {
                "field_name": "Wind Convection Windward Equation Vertical Wall User Curve Name",
                "field_type": "a"
            },
            "wind_convection_leeward_vertical_wall_equation_source": {
                "field_name": "Wind Convection Leeward Vertical Wall Equation Source",
                "field_type": "a"
            },
            "wind_convection_leeward_vertical_wall_equation_user_curve_name": {
                "field_name": "Wind Convection Leeward Vertical Wall Equation User Curve Name",
                "field_type": "a"
            },
            "wind_convection_horizontal_roof_equation_source": {
                "field_name": "Wind Convection Horizontal Roof Equation Source",
                "field_type": "a"
            },
            "wind_convection_horizontal_roof_user_curve_name": {
                "field_name": "Wind Convection Horizontal Roof User Curve Name",
                "field_type": "a"
            },
            "natural_convection_vertical_wall_equation_source": {
                "field_name": "Natural Convection Vertical Wall Equation Source",
                "field_type": "a"
            },
            "natural_convection_vertical_wall_equation_user_curve_name": {
                "field_name": "Natural Convection Vertical Wall Equation User Curve Name",
                "field_type": "a"
            },
            "natural_convection_stable_horizontal_equation_source": {
                "field_name": "Natural Convection Stable Horizontal Equation Source",
                "field_type": "a"
            },
            "natural_convection_stable_horizontal_equation_user_curve_name": {
                "field_name": "Natural Convection Stable Horizontal Equation User Curve Name",
                "field_type": "a"
            },
            "natural_convection_unstable_horizontal_equation_source": {
                "field_name": "Natural Convection Unstable Horizontal Equation Source",
                "field_type": "a"
            },
            "natural_convection_unstable_horizontal_equation_user_curve_name": {
                "field_name": "Natural Convection Unstable Horizontal Equation User Curve Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "wind_convection_windward_vertical_wall_equation_source",
            "wind_convection_windward_equation_vertical_wall_user_curve_name",
            "wind_convection_leeward_vertical_wall_equation_source",
            "wind_convection_leeward_vertical_wall_equation_user_curve_name",
            "wind_convection_horizontal_roof_equation_source",
            "wind_convection_horizontal_roof_user_curve_name",
            "natural_convection_vertical_wall_equation_source",
            "natural_convection_vertical_wall_equation_user_curve_name",
            "natural_convection_stable_horizontal_equation_source",
            "natural_convection_stable_horizontal_equation_user_curve_name",
            "natural_convection_unstable_horizontal_equation_source",
            "natural_convection_unstable_horizontal_equation_user_curve_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "wind_convection_windward_vertical_wall_equation_source",
                "wind_convection_windward_equation_vertical_wall_user_curve_name",
                "wind_convection_leeward_vertical_wall_equation_source",
                "wind_convection_leeward_vertical_wall_equation_user_curve_name",
                "wind_convection_horizontal_roof_equation_source",
                "wind_convection_horizontal_roof_user_curve_name",
                "natural_convection_vertical_wall_equation_source",
                "natural_convection_vertical_wall_equation_user_curve_name",
                "natural_convection_stable_horizontal_equation_source",
                "natural_convection_stable_horizontal_equation_user_curve_name",
                "natural_convection_unstable_horizontal_equation_source",
                "natural_convection_unstable_horizontal_equation_user_curve_name"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "maxProperties": 1,
    "memo": "Options to change the individual convection model equations for dynamic selection when using AdaptiveConvectiongAlgorithm This object is only needed to make changes to the default model selections for any or all of the surface categories. This object is for the outside face, the side of the surface facing away from the thermal zone.",
    "min_fields": 13.0
}
```
