```
{
    "SurfaceProperty:ConvectionCoefficients:MultipleSurface": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "surface_type": {
                        "type": "string",
                        "enum": [
                            "AllExteriorFloors",
                            "AllExteriorRoofs",
                            "AllExteriorSurfaces",
                            "AllExteriorWalls",
                            "AllExteriorWindows",
                            "AllInteriorCeilings",
                            "AllInteriorFloors",
                            "AllInteriorSurfaces",
                            "AllInteriorWalls",
                            "AllInteriorWindows"
                        ]
                    },
                    "convection_coefficient_1_location": {
                        "type": "string",
                        "enum": [
                            "Inside",
                            "Outside"
                        ]
                    },
                    "convection_coefficient_1_type": {
                        "type": "string",
                        "enum": [
                            "ASHRAEVerticalWall",
                            "ASTMC1340",
                            "AdaptiveConvectionAlgorithm",
                            "AlamdariHammondStableHorizontal",
                            "AlamdariHammondUnstableHorizontal",
                            "AlamdariHammondVerticalWall",
                            "AwbiHattonHeatedFloor",
                            "AwbiHattonHeatedWall",
                            "BeausoleilMorrisonMixedAssistedWall",
                            "BeausoleilMorrisonMixedOpposingWall",
                            "BeausoleilMorrisonMixedStableCeiling",
                            "BeausoleilMorrisonMixedStableFloor",
                            "BeausoleilMorrisonMixedUnstableCeiling",
                            "BeausoleilMorrisonMixedUnstableFloor",
                            "BlockenWindard",
                            "ClearRoof",
                            "DOE-2",
                            "EmmelRoof",
                            "EmmelVertical",
                            "FisherPedersenCeilingDiffuserCeiling",
                            "FisherPedersenCeilingDiffuserFloor",
                            "FisherPedersenCeilingDiffuserWalls",
                            "FohannoPolidoriVerticalWall",
                            "GoldsteinNovoselacCeilingDiffuserFloor",
                            "GoldsteinNovoselacCeilingDiffuserWalls",
                            "GoldsteinNovoselacCeilingDiffuserWindow",
                            "ISO15099Windows",
                            "KaradagChilledCeiling",
                            "KhalifaEq3WallAwayFromHeat",
                            "KhalifaEq4CeilingAwayFromHeat",
                            "KhalifaEq5WallNearHeat",
                            "KhalifaEq6NonHeatedWalls",
                            "KhalifaEq7Ceiling",
                            "McAdams",
                            "Mitchell",
                            "MoWitt",
                            "NusseltJurges",
                            "Schedule",
                            "Simple",
                            "SimpleCombined",
                            "TARP",
                            "UserCurve",
                            "Value",
                            "WaltonStableHorizontalOrTilt",
                            "WaltonUnstableHorizontalOrTilt"
                        ]
                    },
                    "convection_coefficient_1": {
                        "type": "number",
                        "note": "used if Convection Type=Value, min and max limits are set in HeatBalanceAlgorithm object. Default limits are Minimum >= 0.1 and Maximum <= 1000",
                        "units": "W/m2-K"
                    },
                    "convection_coefficient_1_schedule_name": {
                        "type": "string",
                        "note": "used if Convection Type=Schedule,  min and max limits are set in HeatBalanceAlgorithm object. Default limits are Minimum >= 0.1 and Maximum <= 1000",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "convection_coefficient_1_user_curve_name": {
                        "type": "string",
                        "note": "used if Convection Type = UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionModels"
                        ]
                    },
                    "convection_coefficient_2_location": {
                        "type": "string",
                        "enum": [
                            "Inside",
                            "Outside"
                        ]
                    },
                    "convection_coefficient_2_type": {
                        "type": "string",
                        "enum": [
                            "ASHRAEVerticalWall",
                            "ASTMC1340",
                            "AdaptiveConvectionAlgorithm",
                            "AlamdariHammondStableHorizontal",
                            "AlamdariHammondUnstableHorizontal",
                            "AlamdariHammondVerticalWall",
                            "AwbiHattonHeatedFloor",
                            "AwbiHattonHeatedWall",
                            "BeausoleilMorrisonMixedAssistedWall",
                            "BeausoleilMorrisonMixedOpposingWall",
                            "BeausoleilMorrisonMixedStableCeiling",
                            "BeausoleilMorrisonMixedStableFloor",
                            "BeausoleilMorrisonMixedUnstableCeiling",
                            "BeausoleilMorrisonMixedUnstableFloor",
                            "BlockenWindard",
                            "ClearRoof",
                            "DOE-2",
                            "EmmelRoof",
                            "EmmelVertical",
                            "FisherPedersenCeilingDiffuserCeiling",
                            "FisherPedersenCeilingDiffuserFloor",
                            "FisherPedersenCeilingDiffuserWalls",
                            "FohannoPolidoriVerticalWall",
                            "GoldsteinNovoselacCeilingDiffuserFloor",
                            "GoldsteinNovoselacCeilingDiffuserWalls",
                            "GoldsteinNovoselacCeilingDiffuserWindow",
                            "ISO15099Windows",
                            "KaradagChilledCeiling",
                            "KhalifaEq3WallAwayFromHeat",
                            "KhalifaEq4CeilingAwayFromHeat",
                            "KhalifaEq5WallNearHeat",
                            "KhalifaEq6NonHeatedWalls",
                            "KhalifaEq7Ceiling",
                            "McAdams",
                            "Mitchell",
                            "MoWitt",
                            "NusseltJurges",
                            "Schedule",
                            "Simple",
                            "SimpleCombined",
                            "TARP",
                            "UserCurve",
                            "Value",
                            "WaltonStableHorizontalOrTilt",
                            "WaltonUnstableHorizontalOrTilt"
                        ]
                    },
                    "convection_coefficient_2": {
                        "type": "number",
                        "note": "used if Convection Type=Value, min and max limits are set in HeatBalanceAlgorithm object. Default limits are Minimum >= 0.1 and Maximum <= 1000",
                        "default": 0.1,
                        "units": "W/m2-K"
                    },
                    "convection_coefficient_2_schedule_name": {
                        "type": "string",
                        "note": "used if Convection Type=Schedule,  min and max limits are set in HeatBalanceAlgorithm object. Default limits are Minimum >= 0.1 and Maximum <= 1000",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "convection_coefficient_2_user_curve_name": {
                        "type": "string",
                        "note": "used if Convection Type = UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionModels"
                        ]
                    }
                },
                "required": [
                    "surface_type",
                    "convection_coefficient_1_location",
                    "convection_coefficient_1_type"
                ]
            }
        },
        "group": "Advanced Construction, Surface, Zone Concepts",
        "legacy_idd": {
            "field_info": {
                "surface_type": {
                    "field_name": "Surface Type",
                    "field_type": "a"
                },
                "convection_coefficient_1_location": {
                    "field_name": "Convection Coefficient 1 Location",
                    "field_type": "a"
                },
                "convection_coefficient_1_type": {
                    "field_name": "Convection Coefficient 1 Type",
                    "field_type": "a"
                },
                "convection_coefficient_1": {
                    "field_name": "Convection Coefficient 1",
                    "field_type": "n"
                },
                "convection_coefficient_1_schedule_name": {
                    "field_name": "Convection Coefficient 1 Schedule Name",
                    "field_type": "a"
                },
                "convection_coefficient_1_user_curve_name": {
                    "field_name": "Convection Coefficient 1 User Curve Name",
                    "field_type": "a"
                },
                "convection_coefficient_2_location": {
                    "field_name": "Convection Coefficient 2 Location",
                    "field_type": "a"
                },
                "convection_coefficient_2_type": {
                    "field_name": "Convection Coefficient 2 Type",
                    "field_type": "a"
                },
                "convection_coefficient_2": {
                    "field_name": "Convection Coefficient 2",
                    "field_type": "n"
                },
                "convection_coefficient_2_schedule_name": {
                    "field_name": "Convection Coefficient 2 Schedule Name",
                    "field_type": "a"
                },
                "convection_coefficient_2_user_curve_name": {
                    "field_name": "Convection Coefficient 2 User Curve Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "surface_type",
                "convection_coefficient_1_location",
                "convection_coefficient_1_type",
                "convection_coefficient_1",
                "convection_coefficient_1_schedule_name",
                "convection_coefficient_1_user_curve_name",
                "convection_coefficient_2_location",
                "convection_coefficient_2_type",
                "convection_coefficient_2",
                "convection_coefficient_2_schedule_name",
                "convection_coefficient_2_user_curve_name"
            ],
            "alphas": {
                "fields": [
                    "surface_type",
                    "convection_coefficient_1_location",
                    "convection_coefficient_1_type",
                    "convection_coefficient_1_schedule_name",
                    "convection_coefficient_1_user_curve_name",
                    "convection_coefficient_2_location",
                    "convection_coefficient_2_type",
                    "convection_coefficient_2_schedule_name",
                    "convection_coefficient_2_user_curve_name"
                ]
            },
            "numerics": {
                "fields": [
                    "convection_coefficient_1",
                    "convection_coefficient_2"
                ]
            }
        },
        "type": "object",
        "memo": "Allow user settable interior and/or exterior convection coefficients. Note that some other factors may limit the lower bounds for these values, such as for windows, the interior convection coefficient must be >.28, for trombe wall algorithm selection (zone), the interior convection coefficient must be >.1 for TARP interior convection, the lower limit is also .1 Minimum and maximum limits are set in HeatBalanceAlgorithm object. Defaults in HeatBalanceAlgorithm object are [.1,1000]."
    }
}
```
