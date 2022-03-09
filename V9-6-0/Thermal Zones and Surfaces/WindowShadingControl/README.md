```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "zone_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "shading_control_sequence_number": {
                    "type": "number",
                    "minimum": 1.0,
                    "default": 1.0,
                    "note": "If multiple WindowShadingControl objects are used than the order that they deploy the window shades can be set with this field. The first WindowShadingControl should be 1 and subsequent WindowShadingControl should 2 or 3 or higher. This is usually used when the Multiple Surface Control Type field is set to Group and groups of windows are being controlled in a certain order."
                },
                "shading_type": {
                    "type": "string",
                    "enum": [
                        "BetweenGlassBlind",
                        "BetweenGlassShade",
                        "ExteriorBlind",
                        "ExteriorScreen",
                        "ExteriorShade",
                        "InteriorBlind",
                        "InteriorShade",
                        "SwitchableGlazing"
                    ]
                },
                "construction_with_shading_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ConstructionNames"
                    ],
                    "note": "Required if Shading Type = SwitchableGlazing Required if Shading Type = interior or exterior shade or blind, or exterior screen, and \"Shading Device Material Name\" is not specified. If both \"Construction with Shading Name\" and \"Shading Device Material Name\" are entered, the former takes precedence."
                },
                "shading_control_type": {
                    "type": "string",
                    "enum": [
                        "AlwaysOff",
                        "AlwaysOn",
                        "MeetDaylightIlluminanceSetpoint",
                        "OffNightAndOnDayIfCoolingAndHighSolarOnWindow",
                        "OnIfHighGlare",
                        "OnIfHighHorizontalSolar",
                        "OnIfHighOutdoorAirTempAndHighHorizontalSolar",
                        "OnIfHighOutdoorAirTempAndHighSolarOnWindow",
                        "OnIfHighOutdoorAirTemperature",
                        "OnIfHighSolarOnWindow",
                        "OnIfHighZoneAirTempAndHighHorizontalSolar",
                        "OnIfHighZoneAirTempAndHighSolarOnWindow",
                        "OnIfHighZoneAirTemperature",
                        "OnIfHighZoneCooling",
                        "OnIfScheduleAllows",
                        "OnNightAndOnDayIfCoolingAndHighSolarOnWindow",
                        "OnNightIfHeatingAndOffDay",
                        "OnNightIfHeatingAndOnDayIfCooling",
                        "OnNightIfLowInsideTempAndOffDay",
                        "OnNightIfLowOutdoorTempAndOffDay",
                        "OnNightIfLowOutdoorTempAndOnDayIfCooling"
                    ],
                    "note": "OnIfScheduleAllows requires that Schedule Name be specified and Shading Control Is Scheduled = Yes. AlwaysOn, AlwaysOff and OnIfScheduleAllows are the only valid control types for ExteriorScreen. The following six control types are used primarily to reduce zone cooling load due to window solar gain Following entry should be used only if Shading Type = SwitchableGlazing and window is in a daylit zone The following three control types are used to reduce zone Heating load. They can be used with any Shading Type but are most appropriate for opaque interior or exterior shades with high insulating value (\"opaque movable insulation\") The following two control types are used to reduce zone heating and cooling load. They can be used with any Shading Type but are most appropriate for translucent interior or exterior shades with high insulating value (\"translucent movable insulation\") The following two control types are used to reduce zone Cooling load. They can be used with any Shading Type but are most appropriate for interior or exterior blinds,interior or exterior shades with low insulating value, or switchable glazing The following four control types require that both Setpoint and Setpoint2 be specified Setpoint will correspond to outdoor air temp or zone air temp (deg C) Setpoint2 will correspond to solar on window or horizontal solar (W/m2)"
                },
                "schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Required if Shading Control Is Scheduled = Yes. If schedule value = 1, shading control is active, i.e., shading can take place only if the control test passes. If schedule value = 0, shading is off whether or not the control test passes. Schedule Name is required if Shading Control Is Scheduled = Yes. If Schedule Name is not specified, shading control is assumed to be active at all times."
                },
                "setpoint": {
                    "type": "number",
                    "units": "W/m2, W or deg C",
                    "note": "W/m2 for solar-based controls, W for cooling- or heating-based controls, deg C for temperature-based controls. Unused for Shading Control Type = AlwaysOn, AlwaysOff, OnIfScheduleAllows, OnIfHighGlare, Glare, and DaylightIlluminance"
                },
                "shading_control_is_scheduled": {
                    "type": "string",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "No",
                    "note": "If Yes, Schedule Name is required; if No, Schedule Name is not used. Shading Control Is Scheduled = Yes is required if Shading Control Type = OnIfScheduleAllows."
                },
                "glare_control_is_active": {
                    "type": "string",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "No",
                    "note": "If Yes and window is in a daylit zone, shading is on if zone's discomfort glare index exceeds the maximum discomfort glare index specified in the Daylighting object referenced by the zone. The glare test is OR'ed with the test specified by Shading Control Type. Glare Control Is Active = Yes is required if Shading Control Type = OnIfHighGlare."
                },
                "shading_device_material_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "WindowShadesScreensAndBlinds"
                    ],
                    "note": "Enter the name of a WindowMaterial:Shade, WindowMaterial:Screen or WindowMaterial:Blind object. Required if \"Construction with Shading Name\" is not specified. Not used if Shading Control Type = SwitchableGlazing, BetweenGlassShade, or BetweenGlassBlind. If both \"Construction with Shading Name\" and \"Shading Device Material Name\" are entered, the former takes precedence."
                },
                "type_of_slat_angle_control_for_blinds": {
                    "type": "string",
                    "enum": [
                        "",
                        "BlockBeamSolar",
                        "FixedSlatAngle",
                        "ScheduledSlatAngle"
                    ],
                    "default": "FixedSlatAngle",
                    "note": "Used only if Shading Type = InteriorBlind, ExteriorBlind or BetweenGlassBlind. If choice is ScheduledSlatAngle then Slat Angle Schedule Name is required."
                },
                "slat_angle_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Used only if Shading Type = InteriorBlind, ExteriorBlind or BetweenGlassBlind. Required if Type of Slat Angle Control for Blinds = ScheduledSlatAngle Schedule values should be degrees (0 minimum, 180 maximum)"
                },
                "setpoint_2": {
                    "type": "number",
                    "units": "W/m2 or deg C",
                    "note": "W/m2 for solar-based controls, deg C for temperature-based controls. Used only as the second setpoint for the following two-setpoint control types: OnIfHighOutdoorAirTempAndHighSolarOnWindow, OnIfHighOutdoorAirTempAndHighHorizontalSolar, OnIfHighZoneAirTempAndHighSolarOnWindow, and OnIfHighZoneAirTempAndHighHorizontalSolar",
                    "ip-units": "unknown"
                },
                "daylighting_control_object_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "DaylightingControlNames"
                    ],
                    "note": "Reference to the Daylighting:Controls object that provides the glare and illuminance control to the zone."
                },
                "multiple_surface_control_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "Group",
                        "Sequential"
                    ],
                    "default": "Sequential",
                    "note": "When Sequential is used the list of fenestration surfaces are controlled individually in the order specified When Group is used the entire list is controlled simultaneously and if glare control is needed the entire group of window shades are deployed together a the same time"
                },
                "fenestration_surfaces": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "fenestration_surface_name": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "GlazedExtSubSurfNames"
                                ],
                                "note": "When Multiple Surface Control Type is set to Sequential the shades will be deployed for the referenced surface objects in order. When that field is set to Group the entire list is controlled simultaneously."
                            }
                        },
                        "type": "object",
                        "required": [
                            "fenestration_surface_name"
                        ]
                    }
                }
            },
            "required": [
                "zone_name",
                "shading_type",
                "shading_control_type"
            ]
        }
    },
    "group": "Thermal Zones and Surfaces",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "WindowShadeControlNames"
        ],
        "note": "Referenced by surfaces that are exterior windows Not used by interzone windows"
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "zone_name": {
                "field_name": "Zone Name",
                "field_type": "a"
            },
            "shading_control_sequence_number": {
                "field_name": "Shading Control Sequence Number",
                "field_type": "n"
            },
            "shading_type": {
                "field_name": "Shading Type",
                "field_type": "a"
            },
            "construction_with_shading_name": {
                "field_name": "Construction with Shading Name",
                "field_type": "a"
            },
            "shading_control_type": {
                "field_name": "Shading Control Type",
                "field_type": "a"
            },
            "schedule_name": {
                "field_name": "Schedule Name",
                "field_type": "a"
            },
            "setpoint": {
                "field_name": "Setpoint",
                "field_type": "n"
            },
            "shading_control_is_scheduled": {
                "field_name": "Shading Control Is Scheduled",
                "field_type": "a"
            },
            "glare_control_is_active": {
                "field_name": "Glare Control Is Active",
                "field_type": "a"
            },
            "shading_device_material_name": {
                "field_name": "Shading Device Material Name",
                "field_type": "a"
            },
            "type_of_slat_angle_control_for_blinds": {
                "field_name": "Type of Slat Angle Control for Blinds",
                "field_type": "a"
            },
            "slat_angle_schedule_name": {
                "field_name": "Slat Angle Schedule Name",
                "field_type": "a"
            },
            "setpoint_2": {
                "field_name": "Setpoint 2",
                "field_type": "n"
            },
            "daylighting_control_object_name": {
                "field_name": "Daylighting Control Object Name",
                "field_type": "a"
            },
            "multiple_surface_control_type": {
                "field_name": "Multiple Surface Control Type",
                "field_type": "a"
            },
            "fenestration_surface_name": {
                "field_name": "Fenestration Surface Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "zone_name",
            "shading_control_sequence_number",
            "shading_type",
            "construction_with_shading_name",
            "shading_control_type",
            "schedule_name",
            "setpoint",
            "shading_control_is_scheduled",
            "glare_control_is_active",
            "shading_device_material_name",
            "type_of_slat_angle_control_for_blinds",
            "slat_angle_schedule_name",
            "setpoint_2",
            "daylighting_control_object_name",
            "multiple_surface_control_type"
        ],
        "alphas": {
            "fields": [
                "name",
                "zone_name",
                "shading_type",
                "construction_with_shading_name",
                "shading_control_type",
                "schedule_name",
                "shading_control_is_scheduled",
                "glare_control_is_active",
                "shading_device_material_name",
                "type_of_slat_angle_control_for_blinds",
                "slat_angle_schedule_name",
                "daylighting_control_object_name",
                "multiple_surface_control_type"
            ],
            "extensions": [
                "fenestration_surface_name"
            ]
        },
        "numerics": {
            "fields": [
                "shading_control_sequence_number",
                "setpoint",
                "setpoint_2"
            ]
        },
        "extensibles": [
            "fenestration_surface_name"
        ],
        "extension": "fenestration_surfaces"
    },
    "type": "object",
    "memo": "Specifies the type, location, and controls for window shades, window blinds, and switchable glazing. Referencing the surface objects for exterior windows and glass doors (ref: FenestrationSurface:Detailed, Window, and GlazedDoor).",
    "extensible_size": 1.0
}
```
