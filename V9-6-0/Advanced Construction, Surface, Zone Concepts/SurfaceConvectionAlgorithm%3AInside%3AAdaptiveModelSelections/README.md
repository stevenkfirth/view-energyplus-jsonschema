```
{
    "SurfaceConvectionAlgorithm:Inside:AdaptiveModelSelections": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "simple_buoyancy_vertical_wall_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with no HVAC or when HVAC is off This is for vertical walls",
                        "default": "FohannoPolidoriVerticalWall",
                        "enum": [
                            "",
                            "ASHRAEVerticalWall",
                            "AlamdariHammondVerticalWall",
                            "FohannoPolidoriVerticalWall",
                            "ISO15099Windows",
                            "KhalifaEq3WallAwayFromHeat",
                            "KhalifaEq6NonHeatedWalls",
                            "UserCurve"
                        ]
                    },
                    "simple_buoyancy_vertical_wall_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "simple_buoyancy_stable_horizontal_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with no HVAC or when HVAC is off This is for horizontal surfaces with heat flow directed for stable thermal stratification",
                        "default": "AlamdariHammondStableHorizontal",
                        "enum": [
                            "",
                            "AlamdariHammondStableHorizontal",
                            "UserCurve",
                            "WaltonStableHorizontalOrTilt"
                        ]
                    },
                    "simple_buoyancy_stable_horizontal_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "simple_buoyancy_unstable_horizontal_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with no HVAC or when HVAC is off This is for passive horizontal surfaces with heat flow for unstable thermal stratification",
                        "default": "AlamdariHammondUnstableHorizontal",
                        "enum": [
                            "",
                            "AlamdariHammondUnstableHorizontal",
                            "UserCurve",
                            "WaltonUnstableHorizontalOrTilt"
                        ]
                    },
                    "simple_buoyancy_unstable_horizontal_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "simple_buoyancy_stable_tilted_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with no HVAC or when HVAC is off This is for tilted surfaces with heat flow for stable thermal stratification",
                        "default": "WaltonStableHorizontalOrTilt",
                        "enum": [
                            "",
                            "AlamdariHammondStableHorizontal",
                            "UserCurve",
                            "WaltonStableHorizontalOrTilt"
                        ]
                    },
                    "simple_buoyancy_stable_tilted_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "simple_buoyancy_unstable_tilted_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with no HVAC or when HVAC is off This is for tilted surfaces with heat flow for unstable thermal stratification",
                        "default": "WaltonUnstableHorizontalOrTilt",
                        "enum": [
                            "",
                            "AlamdariHammondUnstableHorizontal",
                            "UserCurve",
                            "WaltonUnstableHorizontalOrTilt"
                        ]
                    },
                    "simple_buoyancy_unstable_tilted_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "simple_buoyancy_windows_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with no HVAC or when HVAC is off This is for all window surfaces",
                        "default": "ISO15099Windows",
                        "enum": [
                            "",
                            "ASHRAEVerticalWall",
                            "AlamdariHammondVerticalWall",
                            "FohannoPolidoriVerticalWall",
                            "ISO15099Windows",
                            "KaradagChilledCeiling",
                            "UserCurve"
                        ]
                    },
                    "simple_buoyancy_windows_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "floor_heat_ceiling_cool_vertical_wall_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with in-floor heating and/or in-ceiling cooling This is for vertical walls",
                        "default": "KhalifaEq3WallAwayFromHeat",
                        "enum": [
                            "",
                            "ASHRAEVerticalWall",
                            "AlamdariHammondVerticalWall",
                            "FohannoPolidoriVerticalWall",
                            "ISO15099Windows",
                            "KhalifaEq3WallAwayFromHeat",
                            "UserCurve"
                        ]
                    },
                    "floor_heat_ceiling_cool_vertical_wall_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "floor_heat_ceiling_cool_stable_horizontal_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with in-floor heating and/or in-ceiling cooling This is for passive horizontal surfaces with heat flow for stable thermal stratification",
                        "default": "AlamdariHammondStableHorizontal",
                        "enum": [
                            "",
                            "AlamdariHammondStableHorizontal",
                            "UserCurve",
                            "WaltonStableHorizontalOrTilt"
                        ]
                    },
                    "floor_heat_ceiling_cool_stable_horizontal_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "floor_heat_ceiling_cool_unstable_horizontal_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with in-floor heating and/or in-ceiling cooling This is for passive horizontal surfaces with heat flow for unstable thermal stratification",
                        "default": "KhalifaEq4CeilingAwayFromHeat",
                        "enum": [
                            "",
                            "AlamdariHammondUnstableHorizontal",
                            "KhalifaEq4CeilingAwayFromHeat",
                            "UserCurve",
                            "WaltonUnstableHorizontalOrTilt"
                        ]
                    },
                    "floor_heat_ceiling_cool_unstable_horizontal_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "floor_heat_ceiling_cool_heated_floor_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with in-floor heating and/or in-ceiling cooling This is for a floor with active heating elements",
                        "default": "AwbiHattonHeatedFloor",
                        "enum": [
                            "",
                            "AlamdariHammondUnstableHorizontal",
                            "AwbiHattonHeatedFloor",
                            "UserCurve",
                            "WaltonUnstableHorizontalOrTilt"
                        ]
                    },
                    "floor_heat_ceiling_cool_heated_floor_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "floor_heat_ceiling_cool_chilled_ceiling_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with in-floor heating and/or in-ceiling cooling This is for a ceiling with active cooling elements",
                        "default": "KaradagChilledCeiling",
                        "enum": [
                            "",
                            "AlamdariHammondUnstableHorizontal",
                            "KaradagChilledCeiling",
                            "UserCurve",
                            "WaltonUnstableHorizontalOrTilt"
                        ]
                    },
                    "floor_heat_ceiling_cool_chilled_ceiling_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "floor_heat_ceiling_cool_stable_tilted_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with in-floor heating and/or in-ceiling cooling This is for tilted surfaces with heat flow for stable thermal stratification",
                        "default": "WaltonStableHorizontalOrTilt",
                        "enum": [
                            "",
                            "AlamdariHammondStableHorizontal",
                            "ISO15099Windows",
                            "UserCurve",
                            "WaltonStableHorizontalOrTilt"
                        ]
                    },
                    "floor_heat_ceiling_cool_stable_tilted_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "floor_heat_ceiling_cool_unstable_tilted_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with in-floor heating and/or in-ceiling cooling This is for tilted surfaces with heat flow for unstable thermal stratification",
                        "default": "WaltonUnstableHorizontalOrTilt",
                        "enum": [
                            "",
                            "AlamdariHammondUnstableHorizontal",
                            "ISO15099Windows",
                            "UserCurve",
                            "WaltonUnstableHorizontalOrTilt"
                        ]
                    },
                    "floor_heat_ceiling_cool_unstable_tilted_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "floor_heat_ceiling_cool_window_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with in-floor heating and/or in-ceiling cooling This is for all window surfaces",
                        "default": "ISO15099Windows",
                        "enum": [
                            "",
                            "ASHRAEVerticalWall",
                            "AlamdariHammondVerticalWall",
                            "ISO15099Windows",
                            "UserCurve"
                        ]
                    },
                    "floor_heat_ceiling_cool_window_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "wall_panel_heating_vertical_wall_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with in-wall panel heating This is for vertical walls that are not actively heated",
                        "default": "KhalifaEq6NonHeatedWalls",
                        "enum": [
                            "",
                            "ASHRAEVerticalWall",
                            "AlamdariHammondVerticalWall",
                            "FohannoPolidoriVerticalWall",
                            "ISO15099Windows",
                            "KhalifaEq6NonHeatedWalls",
                            "UserCurve"
                        ]
                    },
                    "wall_panel_heating_vertical_wall_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "wall_panel_heating_heated_wall_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with in-wall panel heating This is for vertical walls that are being actively heated",
                        "default": "AwbiHattonHeatedWall",
                        "enum": [
                            "",
                            "ASHRAEVerticalWall",
                            "AlamdariHammondVerticalWall",
                            "AwbiHattonHeatedWall",
                            "FohannoPolidoriVerticalWall",
                            "ISO15099Windows",
                            "KhalifaEq5WallNearHeat",
                            "UserCurve"
                        ]
                    },
                    "wall_panel_heating_heated_wall_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "wall_panel_heating_stable_horizontal_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with in-wall panel heating This is for horizontal surfaces with heat flow directed for stable thermal stratification",
                        "default": "AlamdariHammondStableHorizontal",
                        "enum": [
                            "",
                            "AlamdariHammondStableHorizontal",
                            "UserCurve",
                            "WaltonStableHorizontalOrTilt"
                        ]
                    },
                    "wall_panel_heating_stable_horizontal_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "wall_panel_heating_unstable_horizontal_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with in-wall panel heating This is for horizontal surfaces with heat flow directed for unstable thermal stratification",
                        "default": "KhalifaEq7Ceiling",
                        "enum": [
                            "",
                            "ASHRAEVerticalWall",
                            "AlamdariHammondUnstableHorizontal",
                            "KaradagChilledCeiling",
                            "KhalifaEq7Ceiling",
                            "UserCurve",
                            "WaltonUnstableHorizontalOrTilt"
                        ]
                    },
                    "wall_panel_heating_unstable_horizontal_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "wall_panel_heating_stable_tilted_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with in-wall panel heating This is for tilted surfaces with heat flow for stable thermal stratification",
                        "default": "WaltonStableHorizontalOrTilt",
                        "enum": [
                            "",
                            "AlamdariHammondStableHorizontal",
                            "ISO15099Windows",
                            "UserCurve",
                            "WaltonStableHorizontalOrTilt"
                        ]
                    },
                    "wall_panel_heating_stable_tilted_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "wall_panel_heating_unstable_tilted_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with in-wall panel heating This is for tilted surfaces with heat flow for unstable thermal stratification",
                        "default": "WaltonUnstableHorizontalOrTilt",
                        "enum": [
                            "",
                            "AlamdariHammondUnstableHorizontal",
                            "ISO15099Windows",
                            "UserCurve",
                            "WaltonUnstableHorizontalOrTilt"
                        ]
                    },
                    "wall_panel_heating_unstable_tilted_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "wall_panel_heating_window_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with in-wall panel heating This is for all window surfaces",
                        "default": "ISO15099Windows",
                        "enum": [
                            "",
                            "ASHRAEVerticalWall",
                            "AlamdariHammondVerticalWall",
                            "FohannoPolidoriVerticalWall",
                            "ISO15099Windows",
                            "UserCurve"
                        ]
                    },
                    "wall_panel_heating_window_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "convective_zone_heater_vertical_wall_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with convective heater This is for vertical walls not directly affected by heater",
                        "default": "FohannoPolidoriVerticalWall",
                        "enum": [
                            "",
                            "ASHRAEVerticalWall",
                            "AlamdariHammondVerticalWall",
                            "FohannoPolidoriVerticalWall",
                            "ISO15099Windows",
                            "KhalifaEq3WallAwayFromHeat",
                            "KhalifaEq6NonHeatedWalls",
                            "UserCurve"
                        ]
                    },
                    "convective_zone_heater_vertical_wall_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "convective_zone_heater_vertical_walls_near_heater_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with convective heater This is for vertical walls that are directly affected by heater Walls are considered \"near\" when listed in field set for Fraction of Radiant Energy to Surface",
                        "default": "KhalifaEq5WallNearHeat",
                        "enum": [
                            "",
                            "ASHRAEVerticalWall",
                            "AlamdariHammondVerticalWall",
                            "AwbiHattonHeatedWall",
                            "FohannoPolidoriVerticalWall",
                            "ISO15099Windows",
                            "KhalifaEq5WallNearHeat",
                            "UserCurve"
                        ]
                    },
                    "convective_zone_heater_vertical_walls_near_heater_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "convective_zone_heater_stable_horizontal_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with convective heater This is for horizontal surfaces with heat flow directed for stable thermal stratification",
                        "default": "AlamdariHammondStableHorizontal",
                        "enum": [
                            "",
                            "AlamdariHammondStableHorizontal",
                            "UserCurve",
                            "WaltonStableHorizontalOrTilt"
                        ]
                    },
                    "convective_zone_heater_stable_horizontal_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "convective_zone_heater_unstable_horizontal_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with convective heater This is for horizontal surfaces with heat flow directed for unstable thermal stratification",
                        "default": "KhalifaEq7Ceiling",
                        "enum": [
                            "",
                            "AlamdariHammondUnstableHorizontal",
                            "KhalifaEq4CeilingAwayFromHeat",
                            "KhalifaEq7Ceiling",
                            "UserCurve",
                            "WaltonUnstableHorizontalOrTilt"
                        ]
                    },
                    "convective_zone_heater_unstable_horizontal_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "convective_zone_heater_stable_tilted_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with convective heater This is for tilted surfaces with heat flow for stable thermal stratification",
                        "default": "WaltonStableHorizontalOrTilt",
                        "enum": [
                            "",
                            "AlamdariHammondStableHorizontal",
                            "UserCurve",
                            "WaltonStableHorizontalOrTilt"
                        ]
                    },
                    "convective_zone_heater_stable_tilted_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "convective_zone_heater_unstable_tilted_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with convective heater This is for tilted surfaces with heat flow for unstable thermal stratification",
                        "default": "WaltonUnstableHorizontalOrTilt",
                        "enum": [
                            "",
                            "AlamdariHammondUnstableHorizontal",
                            "UserCurve",
                            "WaltonUnstableHorizontalOrTilt"
                        ]
                    },
                    "convective_zone_heater_unstable_tilted_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "convective_zone_heater_windows_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with convective heater This is for all window surfaces",
                        "default": "ISO15099Windows",
                        "enum": [
                            "",
                            "ASHRAEVerticalWall",
                            "AlamdariHammondVerticalWall",
                            "FohannoPolidoriVerticalWall",
                            "ISO15099Windows",
                            "KhalifaEq3WallAwayFromHeat",
                            "UserCurve"
                        ]
                    },
                    "convective_zone_heater_windows_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "central_air_diffuser_wall_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with mechanical forced central air with diffusers This is for all wall surfaces",
                        "default": "GoldsteinNovoselacCeilingDiffuserWalls",
                        "enum": [
                            "",
                            "ASHRAEVerticalWall",
                            "AlamdariHammondVerticalWall",
                            "BeausoleilMorrisonMixedAssistedWall",
                            "BeausoleilMorrisonMixedOpposingWall",
                            "FisherPedersenCeilingDiffuserWalls",
                            "FohannoPolidoriVerticalWall",
                            "GoldsteinNovoselacCeilingDiffuserWalls",
                            "ISO15099Windows",
                            "UserCurve"
                        ]
                    },
                    "central_air_diffuser_wall_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "central_air_diffuser_ceiling_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with mechanical forced central air with diffusers This is for all ceiling surfaces",
                        "default": "FisherPedersenCeilingDiffuserCeiling",
                        "enum": [
                            "",
                            "BeausoleilMorrisonMixedStableCeiling",
                            "BeausoleilMorrisonMixedUnstableCeiling",
                            "FisherPedersenCeilingDiffuserCeiling",
                            "UserCurve"
                        ]
                    },
                    "central_air_diffuser_ceiling_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "central_air_diffuser_floor_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with mechanical forced central air with diffusers This is for all floor surfaces",
                        "default": "GoldsteinNovoselacCeilingDiffuserFloor",
                        "enum": [
                            "",
                            "BeausoleilMorrisonMixedStableFloor",
                            "BeausoleilMorrisonMixedUnstableFloor",
                            "FisherPedersenCeilingDiffuserFloor",
                            "GoldsteinNovoselacCeilingDiffuserFloor",
                            "UserCurve"
                        ]
                    },
                    "central_air_diffuser_floor_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "central_air_diffuser_window_equation_source": {
                        "type": "string",
                        "note": "Applies to zone with mechanical forced central air with diffusers This is for all window surfaces",
                        "default": "GoldsteinNovoselacCeilingDiffuserWindow",
                        "enum": [
                            "",
                            "ASHRAEVerticalWall",
                            "AlamdariHammondVerticalWall",
                            "BeausoleilMorrisonMixedAssistedWall",
                            "BeausoleilMorrisonMixedOpposingWall",
                            "FisherPedersenCeilingDiffuserWalls",
                            "FohannoPolidoriVerticalWall",
                            "GoldsteinNovoselacCeilingDiffuserWindow",
                            "ISO15099Windows",
                            "UserCurve"
                        ]
                    },
                    "central_air_diffuser_window_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "mechanical_zone_fan_circulation_vertical_wall_equation_source": {
                        "type": "string",
                        "note": "reference choice fields",
                        "default": "KhalifaEq3WallAwayFromHeat",
                        "enum": [
                            "",
                            "ASHRAEVerticalWall",
                            "AlamdariHammondVerticalWall",
                            "BeausoleilMorrisonMixedAssistedWall",
                            "BeausoleilMorrisonMixedOpposingWall",
                            "FisherPedersenCeilingDiffuserWalls",
                            "FohannoPolidoriVerticalWall",
                            "GoldsteinNovoselacCeilingDiffuserWalls",
                            "ISO15099Windows",
                            "KhalifaEq3WallAwayFromHeat",
                            "UserCurve"
                        ]
                    },
                    "mechanical_zone_fan_circulation_vertical_wall_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "mechanical_zone_fan_circulation_stable_horizontal_equation_source": {
                        "type": "string",
                        "note": "reference choice fields",
                        "default": "AlamdariHammondStableHorizontal",
                        "enum": [
                            "",
                            "AlamdariHammondStableHorizontal",
                            "UserCurve",
                            "WaltonStableHorizontalOrTilt"
                        ]
                    },
                    "mechanical_zone_fan_circulation_stable_horizontal_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "mechanical_zone_fan_circulation_unstable_horizontal_equation_source": {
                        "type": "string",
                        "note": "reference choice fields",
                        "default": "KhalifaEq4CeilingAwayFromHeat",
                        "enum": [
                            "",
                            "AlamdariHammondUnstableHorizontal",
                            "KhalifaEq4CeilingAwayFromHeat",
                            "UserCurve",
                            "WaltonUnstableHorizontalOrTilt"
                        ]
                    },
                    "mechanical_zone_fan_circulation_unstable_horizontal_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "mechanical_zone_fan_circulation_stable_tilted_equation_source": {
                        "type": "string",
                        "note": "reference choice fields",
                        "default": "WaltonStableHorizontalOrTilt",
                        "enum": [
                            "",
                            "UserCurve",
                            "WaltonStableHorizontalOrTilt"
                        ]
                    },
                    "mechanical_zone_fan_circulation_stable_tilted_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "mechanical_zone_fan_circulation_unstable_tilted_equation_source": {
                        "type": "string",
                        "note": "reference choice fields",
                        "default": "WaltonUnstableHorizontalOrTilt",
                        "enum": [
                            "",
                            "AlamdariHammondUnstableHorizontal",
                            "UserCurve",
                            "WaltonUnstableHorizontalOrTilt"
                        ]
                    },
                    "mechanical_zone_fan_circulation_unstable_tilted_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "mechanical_zone_fan_circulation_window_equation_source": {
                        "type": "string",
                        "note": "reference choice fields",
                        "default": "ISO15099Windows",
                        "enum": [
                            "",
                            "ASHRAEVerticalWall",
                            "AlamdariHammondVerticalWall",
                            "FohannoPolidoriVerticalWall",
                            "GoldsteinNovoselacCeilingDiffuserWindow",
                            "ISO15099Windows",
                            "UserCurve"
                        ]
                    },
                    "mechanical_zone_fan_circulation_window_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "mixed_regime_buoyancy_assisting_flow_on_walls_equation_source": {
                        "type": "string",
                        "note": "reference choice fields",
                        "default": "BeausoleilMorrisonMixedAssistedWall",
                        "enum": [
                            "",
                            "ASHRAEVerticalWall",
                            "AlamdariHammondVerticalWall",
                            "BeausoleilMorrisonMixedAssistedWall",
                            "FisherPedersenCeilingDiffuserWalls",
                            "FohannoPolidoriVerticalWall",
                            "GoldsteinNovoselacCeilingDiffuserWalls",
                            "UserCurve"
                        ]
                    },
                    "mixed_regime_buoyancy_assisting_flow_on_walls_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "mixed_regime_buoyancy_opposing_flow_on_walls_equation_source": {
                        "type": "string",
                        "note": "reference choice fields",
                        "default": "BeausoleilMorrisonMixedOpposingWall",
                        "enum": [
                            "",
                            "ASHRAEVerticalWall",
                            "AlamdariHammondVerticalWall",
                            "BeausoleilMorrisonMixedOpposingWall",
                            "FisherPedersenCeilingDiffuserWalls",
                            "FohannoPolidoriVerticalWall",
                            "GoldsteinNovoselacCeilingDiffuserWalls",
                            "UserCurve"
                        ]
                    },
                    "mixed_regime_buoyancy_opposing_flow_on_walls_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "mixed_regime_stable_floor_equation_source": {
                        "type": "string",
                        "note": "reference choice fields",
                        "default": "BeausoleilMorrisonMixedStableFloor",
                        "enum": [
                            "",
                            "AlamdariHammondStableHorizontal",
                            "BeausoleilMorrisonMixedStableFloor",
                            "UserCurve",
                            "WaltonStableHorizontalOrTilt"
                        ]
                    },
                    "mixed_regime_stable_floor_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "mixed_regime_unstable_floor_equation_source": {
                        "type": "string",
                        "note": "reference choice fields",
                        "default": "BeausoleilMorrisonMixedUnstableFloor",
                        "enum": [
                            "",
                            "AlamdariHammondUnstableHorizontal",
                            "BeausoleilMorrisonMixedUnstableFloor",
                            "UserCurve",
                            "WaltonUnstableHorizontalOrTilt"
                        ]
                    },
                    "mixed_regime_unstable_floor_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "mixed_regime_stable_ceiling_equation_source": {
                        "type": "string",
                        "note": "reference choice fields",
                        "default": "BeausoleilMorrisonMixedStableCeiling",
                        "enum": [
                            "",
                            "AlamdariHammondStableHorizontal",
                            "BeausoleilMorrisonMixedStableCeiling",
                            "UserCurve",
                            "WaltonStableHorizontalOrTilt"
                        ]
                    },
                    "mixed_regime_stable_ceiling_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "mixed_regime_unstable_ceiling_equation_source": {
                        "type": "string",
                        "note": "reference choice fields",
                        "default": "BeausoleilMorrisonMixedUnstableCeiling",
                        "enum": [
                            "",
                            "AlamdariHammondUnstableHorizontal",
                            "BeausoleilMorrisonMixedUnstableCeiling",
                            "UserCurve",
                            "WaltonUnstableHorizontalOrTilt"
                        ]
                    },
                    "mixed_regime_unstable_ceiling_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
                        ]
                    },
                    "mixed_regime_window_equation_source": {
                        "type": "string",
                        "note": "reference choice fields",
                        "default": "GoldsteinNovoselacCeilingDiffuserWindow",
                        "enum": [
                            "",
                            "GoldsteinNovoselacCeilingDiffuserWindow",
                            "ISO15099Windows",
                            "UserCurve"
                        ]
                    },
                    "mixed_regime_window_equation_user_curve_name": {
                        "type": "string",
                        "note": "The SurfaceConvectionAlgorithm:Inside:UserCurve named in this field is used when the previous field is set to UserCurve",
                        "data_type": "object_list",
                        "object_list": [
                            "UserConvectionInsideModels"
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
                "simple_buoyancy_vertical_wall_equation_source": {
                    "field_name": "Simple Buoyancy Vertical Wall Equation Source",
                    "field_type": "a"
                },
                "simple_buoyancy_vertical_wall_user_curve_name": {
                    "field_name": "Simple Buoyancy Vertical Wall User Curve Name",
                    "field_type": "a"
                },
                "simple_buoyancy_stable_horizontal_equation_source": {
                    "field_name": "Simple Buoyancy Stable Horizontal Equation Source",
                    "field_type": "a"
                },
                "simple_buoyancy_stable_horizontal_equation_user_curve_name": {
                    "field_name": "Simple Buoyancy Stable Horizontal Equation User Curve Name",
                    "field_type": "a"
                },
                "simple_buoyancy_unstable_horizontal_equation_source": {
                    "field_name": "Simple Buoyancy Unstable Horizontal Equation Source",
                    "field_type": "a"
                },
                "simple_buoyancy_unstable_horizontal_equation_user_curve_name": {
                    "field_name": "Simple Buoyancy Unstable Horizontal Equation User Curve Name",
                    "field_type": "a"
                },
                "simple_buoyancy_stable_tilted_equation_source": {
                    "field_name": "Simple Buoyancy Stable Tilted Equation Source",
                    "field_type": "a"
                },
                "simple_buoyancy_stable_tilted_equation_user_curve_name": {
                    "field_name": "Simple Buoyancy Stable Tilted Equation User Curve Name",
                    "field_type": "a"
                },
                "simple_buoyancy_unstable_tilted_equation_source": {
                    "field_name": "Simple Buoyancy Unstable Tilted Equation Source",
                    "field_type": "a"
                },
                "simple_buoyancy_unstable_tilted_equation_user_curve_name": {
                    "field_name": "Simple Buoyancy Unstable Tilted Equation User Curve Name",
                    "field_type": "a"
                },
                "simple_buoyancy_windows_equation_source": {
                    "field_name": "Simple Buoyancy Windows Equation Source",
                    "field_type": "a"
                },
                "simple_buoyancy_windows_equation_user_curve_name": {
                    "field_name": "Simple Buoyancy Windows Equation User Curve Name",
                    "field_type": "a"
                },
                "floor_heat_ceiling_cool_vertical_wall_equation_source": {
                    "field_name": "Floor Heat Ceiling Cool Vertical Wall Equation Source",
                    "field_type": "a"
                },
                "floor_heat_ceiling_cool_vertical_wall_equation_user_curve_name": {
                    "field_name": "Floor Heat Ceiling Cool Vertical Wall Equation User Curve Name",
                    "field_type": "a"
                },
                "floor_heat_ceiling_cool_stable_horizontal_equation_source": {
                    "field_name": "Floor Heat Ceiling Cool Stable Horizontal Equation Source",
                    "field_type": "a"
                },
                "floor_heat_ceiling_cool_stable_horizontal_equation_user_curve_name": {
                    "field_name": "Floor Heat Ceiling Cool Stable Horizontal Equation User Curve Name",
                    "field_type": "a"
                },
                "floor_heat_ceiling_cool_unstable_horizontal_equation_source": {
                    "field_name": "Floor Heat Ceiling Cool Unstable Horizontal Equation Source",
                    "field_type": "a"
                },
                "floor_heat_ceiling_cool_unstable_horizontal_equation_user_curve_name": {
                    "field_name": "Floor Heat Ceiling Cool Unstable Horizontal Equation User Curve Name",
                    "field_type": "a"
                },
                "floor_heat_ceiling_cool_heated_floor_equation_source": {
                    "field_name": "Floor Heat Ceiling Cool Heated Floor Equation Source",
                    "field_type": "a"
                },
                "floor_heat_ceiling_cool_heated_floor_equation_user_curve_name": {
                    "field_name": "Floor Heat Ceiling Cool Heated Floor Equation User Curve Name",
                    "field_type": "a"
                },
                "floor_heat_ceiling_cool_chilled_ceiling_equation_source": {
                    "field_name": "Floor Heat Ceiling Cool Chilled Ceiling Equation Source",
                    "field_type": "a"
                },
                "floor_heat_ceiling_cool_chilled_ceiling_equation_user_curve_name": {
                    "field_name": "Floor Heat Ceiling Cool Chilled Ceiling Equation User Curve Name",
                    "field_type": "a"
                },
                "floor_heat_ceiling_cool_stable_tilted_equation_source": {
                    "field_name": "Floor Heat Ceiling Cool Stable Tilted Equation Source",
                    "field_type": "a"
                },
                "floor_heat_ceiling_cool_stable_tilted_equation_user_curve_name": {
                    "field_name": "Floor Heat Ceiling Cool Stable Tilted Equation User Curve Name",
                    "field_type": "a"
                },
                "floor_heat_ceiling_cool_unstable_tilted_equation_source": {
                    "field_name": "Floor Heat Ceiling Cool Unstable Tilted Equation Source",
                    "field_type": "a"
                },
                "floor_heat_ceiling_cool_unstable_tilted_equation_user_curve_name": {
                    "field_name": "Floor Heat Ceiling Cool Unstable Tilted Equation User Curve Name",
                    "field_type": "a"
                },
                "floor_heat_ceiling_cool_window_equation_source": {
                    "field_name": "Floor Heat Ceiling Cool Window Equation Source",
                    "field_type": "a"
                },
                "floor_heat_ceiling_cool_window_equation_user_curve_name": {
                    "field_name": "Floor Heat Ceiling Cool Window Equation User Curve Name",
                    "field_type": "a"
                },
                "wall_panel_heating_vertical_wall_equation_source": {
                    "field_name": "Wall Panel Heating Vertical Wall Equation Source",
                    "field_type": "a"
                },
                "wall_panel_heating_vertical_wall_equation_user_curve_name": {
                    "field_name": "Wall Panel Heating Vertical Wall Equation User Curve Name",
                    "field_type": "a"
                },
                "wall_panel_heating_heated_wall_equation_source": {
                    "field_name": "Wall Panel Heating Heated Wall Equation Source",
                    "field_type": "a"
                },
                "wall_panel_heating_heated_wall_equation_user_curve_name": {
                    "field_name": "Wall Panel Heating Heated Wall Equation User Curve Name",
                    "field_type": "a"
                },
                "wall_panel_heating_stable_horizontal_equation_source": {
                    "field_name": "Wall Panel Heating Stable Horizontal Equation Source",
                    "field_type": "a"
                },
                "wall_panel_heating_stable_horizontal_equation_user_curve_name": {
                    "field_name": "Wall Panel Heating Stable Horizontal Equation User Curve Name",
                    "field_type": "a"
                },
                "wall_panel_heating_unstable_horizontal_equation_source": {
                    "field_name": "Wall Panel Heating Unstable Horizontal Equation Source",
                    "field_type": "a"
                },
                "wall_panel_heating_unstable_horizontal_equation_user_curve_name": {
                    "field_name": "Wall Panel Heating Unstable Horizontal Equation User Curve Name",
                    "field_type": "a"
                },
                "wall_panel_heating_stable_tilted_equation_source": {
                    "field_name": "Wall Panel Heating Stable Tilted Equation Source",
                    "field_type": "a"
                },
                "wall_panel_heating_stable_tilted_equation_user_curve_name": {
                    "field_name": "Wall Panel Heating Stable Tilted Equation User Curve Name",
                    "field_type": "a"
                },
                "wall_panel_heating_unstable_tilted_equation_source": {
                    "field_name": "Wall Panel Heating Unstable Tilted Equation Source",
                    "field_type": "a"
                },
                "wall_panel_heating_unstable_tilted_equation_user_curve_name": {
                    "field_name": "Wall Panel Heating Unstable Tilted Equation User Curve Name",
                    "field_type": "a"
                },
                "wall_panel_heating_window_equation_source": {
                    "field_name": "Wall Panel Heating Window Equation Source",
                    "field_type": "a"
                },
                "wall_panel_heating_window_equation_user_curve_name": {
                    "field_name": "Wall Panel Heating Window Equation User Curve Name",
                    "field_type": "a"
                },
                "convective_zone_heater_vertical_wall_equation_source": {
                    "field_name": "Convective Zone Heater Vertical Wall Equation Source",
                    "field_type": "a"
                },
                "convective_zone_heater_vertical_wall_equation_user_curve_name": {
                    "field_name": "Convective Zone Heater Vertical Wall Equation User Curve Name",
                    "field_type": "a"
                },
                "convective_zone_heater_vertical_walls_near_heater_equation_source": {
                    "field_name": "Convective Zone Heater Vertical Walls Near Heater Equation Source",
                    "field_type": "a"
                },
                "convective_zone_heater_vertical_walls_near_heater_equation_user_curve_name": {
                    "field_name": "Convective Zone Heater Vertical Walls Near Heater Equation User Curve Name",
                    "field_type": "a"
                },
                "convective_zone_heater_stable_horizontal_equation_source": {
                    "field_name": "Convective Zone Heater Stable Horizontal Equation Source",
                    "field_type": "a"
                },
                "convective_zone_heater_stable_horizontal_equation_user_curve_name": {
                    "field_name": "Convective Zone Heater Stable Horizontal Equation User Curve Name",
                    "field_type": "a"
                },
                "convective_zone_heater_unstable_horizontal_equation_source": {
                    "field_name": "Convective Zone Heater Unstable Horizontal Equation Source",
                    "field_type": "a"
                },
                "convective_zone_heater_unstable_horizontal_equation_user_curve_name": {
                    "field_name": "Convective Zone Heater Unstable Horizontal Equation User Curve Name",
                    "field_type": "a"
                },
                "convective_zone_heater_stable_tilted_equation_source": {
                    "field_name": "Convective Zone Heater Stable Tilted Equation Source",
                    "field_type": "a"
                },
                "convective_zone_heater_stable_tilted_equation_user_curve_name": {
                    "field_name": "Convective Zone Heater Stable Tilted Equation User Curve Name",
                    "field_type": "a"
                },
                "convective_zone_heater_unstable_tilted_equation_source": {
                    "field_name": "Convective Zone Heater Unstable Tilted Equation Source",
                    "field_type": "a"
                },
                "convective_zone_heater_unstable_tilted_equation_user_curve_name": {
                    "field_name": "Convective Zone Heater Unstable Tilted Equation User Curve Name",
                    "field_type": "a"
                },
                "convective_zone_heater_windows_equation_source": {
                    "field_name": "Convective Zone Heater Windows Equation Source",
                    "field_type": "a"
                },
                "convective_zone_heater_windows_equation_user_curve_name": {
                    "field_name": "Convective Zone Heater Windows Equation User Curve Name",
                    "field_type": "a"
                },
                "central_air_diffuser_wall_equation_source": {
                    "field_name": "Central Air Diffuser Wall Equation Source",
                    "field_type": "a"
                },
                "central_air_diffuser_wall_equation_user_curve_name": {
                    "field_name": "Central Air Diffuser Wall Equation User Curve Name",
                    "field_type": "a"
                },
                "central_air_diffuser_ceiling_equation_source": {
                    "field_name": "Central Air Diffuser Ceiling Equation Source",
                    "field_type": "a"
                },
                "central_air_diffuser_ceiling_equation_user_curve_name": {
                    "field_name": "Central Air Diffuser Ceiling Equation User Curve Name",
                    "field_type": "a"
                },
                "central_air_diffuser_floor_equation_source": {
                    "field_name": "Central Air Diffuser Floor Equation Source",
                    "field_type": "a"
                },
                "central_air_diffuser_floor_equation_user_curve_name": {
                    "field_name": "Central Air Diffuser Floor Equation User Curve Name",
                    "field_type": "a"
                },
                "central_air_diffuser_window_equation_source": {
                    "field_name": "Central Air Diffuser Window Equation Source",
                    "field_type": "a"
                },
                "central_air_diffuser_window_equation_user_curve_name": {
                    "field_name": "Central Air Diffuser Window Equation User Curve Name",
                    "field_type": "a"
                },
                "mechanical_zone_fan_circulation_vertical_wall_equation_source": {
                    "field_name": "Mechanical Zone Fan Circulation Vertical Wall Equation Source",
                    "field_type": "a"
                },
                "mechanical_zone_fan_circulation_vertical_wall_equation_user_curve_name": {
                    "field_name": "Mechanical Zone Fan Circulation Vertical Wall Equation User Curve Name",
                    "field_type": "a"
                },
                "mechanical_zone_fan_circulation_stable_horizontal_equation_source": {
                    "field_name": "Mechanical Zone Fan Circulation Stable Horizontal Equation Source",
                    "field_type": "a"
                },
                "mechanical_zone_fan_circulation_stable_horizontal_equation_user_curve_name": {
                    "field_name": "Mechanical Zone Fan Circulation Stable Horizontal Equation User Curve Name",
                    "field_type": "a"
                },
                "mechanical_zone_fan_circulation_unstable_horizontal_equation_source": {
                    "field_name": "Mechanical Zone Fan Circulation Unstable Horizontal Equation Source",
                    "field_type": "a"
                },
                "mechanical_zone_fan_circulation_unstable_horizontal_equation_user_curve_name": {
                    "field_name": "Mechanical Zone Fan Circulation Unstable Horizontal Equation User Curve Name",
                    "field_type": "a"
                },
                "mechanical_zone_fan_circulation_stable_tilted_equation_source": {
                    "field_name": "Mechanical Zone Fan Circulation Stable Tilted Equation Source",
                    "field_type": "a"
                },
                "mechanical_zone_fan_circulation_stable_tilted_equation_user_curve_name": {
                    "field_name": "Mechanical Zone Fan Circulation Stable Tilted Equation User Curve Name",
                    "field_type": "a"
                },
                "mechanical_zone_fan_circulation_unstable_tilted_equation_source": {
                    "field_name": "Mechanical Zone Fan Circulation Unstable Tilted Equation Source",
                    "field_type": "a"
                },
                "mechanical_zone_fan_circulation_unstable_tilted_equation_user_curve_name": {
                    "field_name": "Mechanical Zone Fan Circulation Unstable Tilted Equation User Curve Name",
                    "field_type": "a"
                },
                "mechanical_zone_fan_circulation_window_equation_source": {
                    "field_name": "Mechanical Zone Fan Circulation Window Equation Source",
                    "field_type": "a"
                },
                "mechanical_zone_fan_circulation_window_equation_user_curve_name": {
                    "field_name": "Mechanical Zone Fan Circulation Window Equation User Curve Name",
                    "field_type": "a"
                },
                "mixed_regime_buoyancy_assisting_flow_on_walls_equation_source": {
                    "field_name": "Mixed Regime Buoyancy Assisting Flow on Walls Equation Source",
                    "field_type": "a"
                },
                "mixed_regime_buoyancy_assisting_flow_on_walls_equation_user_curve_name": {
                    "field_name": "Mixed Regime Buoyancy Assisting Flow on Walls Equation User Curve Name",
                    "field_type": "a"
                },
                "mixed_regime_buoyancy_opposing_flow_on_walls_equation_source": {
                    "field_name": "Mixed Regime Buoyancy Opposing Flow on Walls Equation Source",
                    "field_type": "a"
                },
                "mixed_regime_buoyancy_opposing_flow_on_walls_equation_user_curve_name": {
                    "field_name": "Mixed Regime Buoyancy Opposing Flow on Walls Equation User Curve Name",
                    "field_type": "a"
                },
                "mixed_regime_stable_floor_equation_source": {
                    "field_name": "Mixed Regime Stable Floor Equation Source",
                    "field_type": "a"
                },
                "mixed_regime_stable_floor_equation_user_curve_name": {
                    "field_name": "Mixed Regime Stable Floor Equation User Curve Name",
                    "field_type": "a"
                },
                "mixed_regime_unstable_floor_equation_source": {
                    "field_name": "Mixed Regime Unstable Floor Equation Source",
                    "field_type": "a"
                },
                "mixed_regime_unstable_floor_equation_user_curve_name": {
                    "field_name": "Mixed Regime Unstable Floor Equation User Curve Name",
                    "field_type": "a"
                },
                "mixed_regime_stable_ceiling_equation_source": {
                    "field_name": "Mixed Regime Stable Ceiling Equation Source",
                    "field_type": "a"
                },
                "mixed_regime_stable_ceiling_equation_user_curve_name": {
                    "field_name": "Mixed Regime Stable Ceiling Equation User Curve Name",
                    "field_type": "a"
                },
                "mixed_regime_unstable_ceiling_equation_source": {
                    "field_name": "Mixed Regime Unstable Ceiling Equation Source",
                    "field_type": "a"
                },
                "mixed_regime_unstable_ceiling_equation_user_curve_name": {
                    "field_name": "Mixed Regime Unstable Ceiling Equation User Curve Name",
                    "field_type": "a"
                },
                "mixed_regime_window_equation_source": {
                    "field_name": "Mixed Regime Window Equation Source",
                    "field_type": "a"
                },
                "mixed_regime_window_equation_user_curve_name": {
                    "field_name": "Mixed Regime Window Equation User Curve Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "simple_buoyancy_vertical_wall_equation_source",
                "simple_buoyancy_vertical_wall_user_curve_name",
                "simple_buoyancy_stable_horizontal_equation_source",
                "simple_buoyancy_stable_horizontal_equation_user_curve_name",
                "simple_buoyancy_unstable_horizontal_equation_source",
                "simple_buoyancy_unstable_horizontal_equation_user_curve_name",
                "simple_buoyancy_stable_tilted_equation_source",
                "simple_buoyancy_stable_tilted_equation_user_curve_name",
                "simple_buoyancy_unstable_tilted_equation_source",
                "simple_buoyancy_unstable_tilted_equation_user_curve_name",
                "simple_buoyancy_windows_equation_source",
                "simple_buoyancy_windows_equation_user_curve_name",
                "floor_heat_ceiling_cool_vertical_wall_equation_source",
                "floor_heat_ceiling_cool_vertical_wall_equation_user_curve_name",
                "floor_heat_ceiling_cool_stable_horizontal_equation_source",
                "floor_heat_ceiling_cool_stable_horizontal_equation_user_curve_name",
                "floor_heat_ceiling_cool_unstable_horizontal_equation_source",
                "floor_heat_ceiling_cool_unstable_horizontal_equation_user_curve_name",
                "floor_heat_ceiling_cool_heated_floor_equation_source",
                "floor_heat_ceiling_cool_heated_floor_equation_user_curve_name",
                "floor_heat_ceiling_cool_chilled_ceiling_equation_source",
                "floor_heat_ceiling_cool_chilled_ceiling_equation_user_curve_name",
                "floor_heat_ceiling_cool_stable_tilted_equation_source",
                "floor_heat_ceiling_cool_stable_tilted_equation_user_curve_name",
                "floor_heat_ceiling_cool_unstable_tilted_equation_source",
                "floor_heat_ceiling_cool_unstable_tilted_equation_user_curve_name",
                "floor_heat_ceiling_cool_window_equation_source",
                "floor_heat_ceiling_cool_window_equation_user_curve_name",
                "wall_panel_heating_vertical_wall_equation_source",
                "wall_panel_heating_vertical_wall_equation_user_curve_name",
                "wall_panel_heating_heated_wall_equation_source",
                "wall_panel_heating_heated_wall_equation_user_curve_name",
                "wall_panel_heating_stable_horizontal_equation_source",
                "wall_panel_heating_stable_horizontal_equation_user_curve_name",
                "wall_panel_heating_unstable_horizontal_equation_source",
                "wall_panel_heating_unstable_horizontal_equation_user_curve_name",
                "wall_panel_heating_stable_tilted_equation_source",
                "wall_panel_heating_stable_tilted_equation_user_curve_name",
                "wall_panel_heating_unstable_tilted_equation_source",
                "wall_panel_heating_unstable_tilted_equation_user_curve_name",
                "wall_panel_heating_window_equation_source",
                "wall_panel_heating_window_equation_user_curve_name",
                "convective_zone_heater_vertical_wall_equation_source",
                "convective_zone_heater_vertical_wall_equation_user_curve_name",
                "convective_zone_heater_vertical_walls_near_heater_equation_source",
                "convective_zone_heater_vertical_walls_near_heater_equation_user_curve_name",
                "convective_zone_heater_stable_horizontal_equation_source",
                "convective_zone_heater_stable_horizontal_equation_user_curve_name",
                "convective_zone_heater_unstable_horizontal_equation_source",
                "convective_zone_heater_unstable_horizontal_equation_user_curve_name",
                "convective_zone_heater_stable_tilted_equation_source",
                "convective_zone_heater_stable_tilted_equation_user_curve_name",
                "convective_zone_heater_unstable_tilted_equation_source",
                "convective_zone_heater_unstable_tilted_equation_user_curve_name",
                "convective_zone_heater_windows_equation_source",
                "convective_zone_heater_windows_equation_user_curve_name",
                "central_air_diffuser_wall_equation_source",
                "central_air_diffuser_wall_equation_user_curve_name",
                "central_air_diffuser_ceiling_equation_source",
                "central_air_diffuser_ceiling_equation_user_curve_name",
                "central_air_diffuser_floor_equation_source",
                "central_air_diffuser_floor_equation_user_curve_name",
                "central_air_diffuser_window_equation_source",
                "central_air_diffuser_window_equation_user_curve_name",
                "mechanical_zone_fan_circulation_vertical_wall_equation_source",
                "mechanical_zone_fan_circulation_vertical_wall_equation_user_curve_name",
                "mechanical_zone_fan_circulation_stable_horizontal_equation_source",
                "mechanical_zone_fan_circulation_stable_horizontal_equation_user_curve_name",
                "mechanical_zone_fan_circulation_unstable_horizontal_equation_source",
                "mechanical_zone_fan_circulation_unstable_horizontal_equation_user_curve_name",
                "mechanical_zone_fan_circulation_stable_tilted_equation_source",
                "mechanical_zone_fan_circulation_stable_tilted_equation_user_curve_name",
                "mechanical_zone_fan_circulation_unstable_tilted_equation_source",
                "mechanical_zone_fan_circulation_unstable_tilted_equation_user_curve_name",
                "mechanical_zone_fan_circulation_window_equation_source",
                "mechanical_zone_fan_circulation_window_equation_user_curve_name",
                "mixed_regime_buoyancy_assisting_flow_on_walls_equation_source",
                "mixed_regime_buoyancy_assisting_flow_on_walls_equation_user_curve_name",
                "mixed_regime_buoyancy_opposing_flow_on_walls_equation_source",
                "mixed_regime_buoyancy_opposing_flow_on_walls_equation_user_curve_name",
                "mixed_regime_stable_floor_equation_source",
                "mixed_regime_stable_floor_equation_user_curve_name",
                "mixed_regime_unstable_floor_equation_source",
                "mixed_regime_unstable_floor_equation_user_curve_name",
                "mixed_regime_stable_ceiling_equation_source",
                "mixed_regime_stable_ceiling_equation_user_curve_name",
                "mixed_regime_unstable_ceiling_equation_source",
                "mixed_regime_unstable_ceiling_equation_user_curve_name",
                "mixed_regime_window_equation_source",
                "mixed_regime_window_equation_user_curve_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "simple_buoyancy_vertical_wall_equation_source",
                    "simple_buoyancy_vertical_wall_user_curve_name",
                    "simple_buoyancy_stable_horizontal_equation_source",
                    "simple_buoyancy_stable_horizontal_equation_user_curve_name",
                    "simple_buoyancy_unstable_horizontal_equation_source",
                    "simple_buoyancy_unstable_horizontal_equation_user_curve_name",
                    "simple_buoyancy_stable_tilted_equation_source",
                    "simple_buoyancy_stable_tilted_equation_user_curve_name",
                    "simple_buoyancy_unstable_tilted_equation_source",
                    "simple_buoyancy_unstable_tilted_equation_user_curve_name",
                    "simple_buoyancy_windows_equation_source",
                    "simple_buoyancy_windows_equation_user_curve_name",
                    "floor_heat_ceiling_cool_vertical_wall_equation_source",
                    "floor_heat_ceiling_cool_vertical_wall_equation_user_curve_name",
                    "floor_heat_ceiling_cool_stable_horizontal_equation_source",
                    "floor_heat_ceiling_cool_stable_horizontal_equation_user_curve_name",
                    "floor_heat_ceiling_cool_unstable_horizontal_equation_source",
                    "floor_heat_ceiling_cool_unstable_horizontal_equation_user_curve_name",
                    "floor_heat_ceiling_cool_heated_floor_equation_source",
                    "floor_heat_ceiling_cool_heated_floor_equation_user_curve_name",
                    "floor_heat_ceiling_cool_chilled_ceiling_equation_source",
                    "floor_heat_ceiling_cool_chilled_ceiling_equation_user_curve_name",
                    "floor_heat_ceiling_cool_stable_tilted_equation_source",
                    "floor_heat_ceiling_cool_stable_tilted_equation_user_curve_name",
                    "floor_heat_ceiling_cool_unstable_tilted_equation_source",
                    "floor_heat_ceiling_cool_unstable_tilted_equation_user_curve_name",
                    "floor_heat_ceiling_cool_window_equation_source",
                    "floor_heat_ceiling_cool_window_equation_user_curve_name",
                    "wall_panel_heating_vertical_wall_equation_source",
                    "wall_panel_heating_vertical_wall_equation_user_curve_name",
                    "wall_panel_heating_heated_wall_equation_source",
                    "wall_panel_heating_heated_wall_equation_user_curve_name",
                    "wall_panel_heating_stable_horizontal_equation_source",
                    "wall_panel_heating_stable_horizontal_equation_user_curve_name",
                    "wall_panel_heating_unstable_horizontal_equation_source",
                    "wall_panel_heating_unstable_horizontal_equation_user_curve_name",
                    "wall_panel_heating_stable_tilted_equation_source",
                    "wall_panel_heating_stable_tilted_equation_user_curve_name",
                    "wall_panel_heating_unstable_tilted_equation_source",
                    "wall_panel_heating_unstable_tilted_equation_user_curve_name",
                    "wall_panel_heating_window_equation_source",
                    "wall_panel_heating_window_equation_user_curve_name",
                    "convective_zone_heater_vertical_wall_equation_source",
                    "convective_zone_heater_vertical_wall_equation_user_curve_name",
                    "convective_zone_heater_vertical_walls_near_heater_equation_source",
                    "convective_zone_heater_vertical_walls_near_heater_equation_user_curve_name",
                    "convective_zone_heater_stable_horizontal_equation_source",
                    "convective_zone_heater_stable_horizontal_equation_user_curve_name",
                    "convective_zone_heater_unstable_horizontal_equation_source",
                    "convective_zone_heater_unstable_horizontal_equation_user_curve_name",
                    "convective_zone_heater_stable_tilted_equation_source",
                    "convective_zone_heater_stable_tilted_equation_user_curve_name",
                    "convective_zone_heater_unstable_tilted_equation_source",
                    "convective_zone_heater_unstable_tilted_equation_user_curve_name",
                    "convective_zone_heater_windows_equation_source",
                    "convective_zone_heater_windows_equation_user_curve_name",
                    "central_air_diffuser_wall_equation_source",
                    "central_air_diffuser_wall_equation_user_curve_name",
                    "central_air_diffuser_ceiling_equation_source",
                    "central_air_diffuser_ceiling_equation_user_curve_name",
                    "central_air_diffuser_floor_equation_source",
                    "central_air_diffuser_floor_equation_user_curve_name",
                    "central_air_diffuser_window_equation_source",
                    "central_air_diffuser_window_equation_user_curve_name",
                    "mechanical_zone_fan_circulation_vertical_wall_equation_source",
                    "mechanical_zone_fan_circulation_vertical_wall_equation_user_curve_name",
                    "mechanical_zone_fan_circulation_stable_horizontal_equation_source",
                    "mechanical_zone_fan_circulation_stable_horizontal_equation_user_curve_name",
                    "mechanical_zone_fan_circulation_unstable_horizontal_equation_source",
                    "mechanical_zone_fan_circulation_unstable_horizontal_equation_user_curve_name",
                    "mechanical_zone_fan_circulation_stable_tilted_equation_source",
                    "mechanical_zone_fan_circulation_stable_tilted_equation_user_curve_name",
                    "mechanical_zone_fan_circulation_unstable_tilted_equation_source",
                    "mechanical_zone_fan_circulation_unstable_tilted_equation_user_curve_name",
                    "mechanical_zone_fan_circulation_window_equation_source",
                    "mechanical_zone_fan_circulation_window_equation_user_curve_name",
                    "mixed_regime_buoyancy_assisting_flow_on_walls_equation_source",
                    "mixed_regime_buoyancy_assisting_flow_on_walls_equation_user_curve_name",
                    "mixed_regime_buoyancy_opposing_flow_on_walls_equation_source",
                    "mixed_regime_buoyancy_opposing_flow_on_walls_equation_user_curve_name",
                    "mixed_regime_stable_floor_equation_source",
                    "mixed_regime_stable_floor_equation_user_curve_name",
                    "mixed_regime_unstable_floor_equation_source",
                    "mixed_regime_unstable_floor_equation_user_curve_name",
                    "mixed_regime_stable_ceiling_equation_source",
                    "mixed_regime_stable_ceiling_equation_user_curve_name",
                    "mixed_regime_unstable_ceiling_equation_source",
                    "mixed_regime_unstable_ceiling_equation_user_curve_name",
                    "mixed_regime_window_equation_source",
                    "mixed_regime_window_equation_user_curve_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "maxProperties": 1,
        "memo": "Options to change the individual convection model equations for dynamic selection when using AdaptiveConvectiongAlgorithm This object is only needed to make changes to the default model selections for any or all of the surface categories. This object is for the inside face, the side of the surface facing a thermal zone.",
        "min_fields": 91.0
    }
}
```
