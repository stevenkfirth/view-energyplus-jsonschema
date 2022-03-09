```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "frame_width": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0,
                    "note": "Width of frame in plane of window Frame width assumed the same on all sides of window"
                },
                "frame_outside_projection": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0,
                    "maximum": 0.5,
                    "default": 0.0,
                    "note": "Amount that frame projects outward from the outside face of the glazing"
                },
                "frame_inside_projection": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0,
                    "maximum": 0.5,
                    "default": 0.0,
                    "note": "Amount that frame projects inward from the inside face of the glazing"
                },
                "frame_conductance": {
                    "type": "number",
                    "units": "W/m2-K",
                    "minimum": 0.0,
                    "note": "Effective conductance of frame Excludes air films Obtained from WINDOW 5 or other 2-D calculation"
                },
                "ratio_of_frame_edge_glass_conductance_to_center_of_glass_conductance": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "maximum": 4.0,
                    "default": 1.0,
                    "note": "Excludes air films; applies only to multipane windows Obtained from WINDOW 5 or other 2-D calculation"
                },
                "frame_solar_absorptance": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.7,
                    "note": "Assumed same on outside and inside of frame"
                },
                "frame_visible_absorptance": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.7,
                    "note": "Assumed same on outside and inside of frame"
                },
                "frame_thermal_hemispherical_emissivity": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 0.9,
                    "note": "Assumed same on outside and inside of frame"
                },
                "divider_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "DividedLite",
                        "Suspended"
                    ],
                    "default": "DividedLite"
                },
                "divider_width": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0,
                    "maximum": 0.5,
                    "default": 0.0,
                    "note": "Width of dividers in plane of window Width assumed the same for all dividers"
                },
                "number_of_horizontal_dividers": {
                    "type": "number",
                    "minimum": 0.0,
                    "default": 0.0,
                    "note": "\"Horizontal\" means parallel to local window X-axis"
                },
                "number_of_vertical_dividers": {
                    "type": "number",
                    "minimum": 0.0,
                    "default": 0.0,
                    "note": "\"Vertical\" means parallel to local window Y-axis"
                },
                "divider_outside_projection": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0,
                    "maximum": 0.5,
                    "default": 0.0,
                    "note": "Amount that divider projects outward from the outside face of the glazing Outside projection assumed the same for all divider elements"
                },
                "divider_inside_projection": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0,
                    "maximum": 0.5,
                    "default": 0.0,
                    "note": "Amount that divider projects inward from the inside face of the glazing Inside projection assumed the same for all divider elements"
                },
                "divider_conductance": {
                    "type": "number",
                    "units": "W/m2-K",
                    "minimum": 0.0,
                    "default": 0.0,
                    "note": "Effective conductance of divider Excludes air films Obtained from WINDOW 5 or other 2-D calculation"
                },
                "ratio_of_divider_edge_glass_conductance_to_center_of_glass_conductance": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "maximum": 4.0,
                    "default": 1.0,
                    "note": "Excludes air films Obtained from WINDOW 5 or other 2-D calculation"
                },
                "divider_solar_absorptance": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0,
                    "note": "Assumed same on outside and inside of divider"
                },
                "divider_visible_absorptance": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0,
                    "note": "Assumed same on outside and inside of divider"
                },
                "divider_thermal_hemispherical_emissivity": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "exclusiveMaximum": 1.0,
                    "default": 0.9,
                    "note": "Assumed same on outside and inside of divider"
                },
                "outside_reveal_solar_absorptance": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0
                },
                "inside_sill_depth": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0,
                    "maximum": 2.0,
                    "default": 0.0
                },
                "inside_sill_solar_absorptance": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0
                },
                "inside_reveal_depth": {
                    "type": "number",
                    "note": "Distance from plane of inside surface of glazing to plane of inside surface of wall. Outside reveal depth is determined from the geometry of the window and the wall it is on; it is non-zero if the plane of the outside surface of the glazing is set back from the plane of the outside surface of the wall.",
                    "units": "m",
                    "minimum": 0.0,
                    "maximum": 2.0,
                    "default": 0.0
                },
                "inside_reveal_solar_absorptance": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0
                }
            }
        }
    },
    "group": "Thermal Zones and Surfaces",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "WindowFrameAndDividerNames"
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
            "frame_width": {
                "field_name": "Frame Width",
                "field_type": "n"
            },
            "frame_outside_projection": {
                "field_name": "Frame Outside Projection",
                "field_type": "n"
            },
            "frame_inside_projection": {
                "field_name": "Frame Inside Projection",
                "field_type": "n"
            },
            "frame_conductance": {
                "field_name": "Frame Conductance",
                "field_type": "n"
            },
            "ratio_of_frame_edge_glass_conductance_to_center_of_glass_conductance": {
                "field_name": "Ratio of Frame-Edge Glass Conductance to Center-Of-Glass Conductance",
                "field_type": "n"
            },
            "frame_solar_absorptance": {
                "field_name": "Frame Solar Absorptance",
                "field_type": "n"
            },
            "frame_visible_absorptance": {
                "field_name": "Frame Visible Absorptance",
                "field_type": "n"
            },
            "frame_thermal_hemispherical_emissivity": {
                "field_name": "Frame Thermal Hemispherical Emissivity",
                "field_type": "n"
            },
            "divider_type": {
                "field_name": "Divider Type",
                "field_type": "a"
            },
            "divider_width": {
                "field_name": "Divider Width",
                "field_type": "n"
            },
            "number_of_horizontal_dividers": {
                "field_name": "Number of Horizontal Dividers",
                "field_type": "n"
            },
            "number_of_vertical_dividers": {
                "field_name": "Number of Vertical Dividers",
                "field_type": "n"
            },
            "divider_outside_projection": {
                "field_name": "Divider Outside Projection",
                "field_type": "n"
            },
            "divider_inside_projection": {
                "field_name": "Divider Inside Projection",
                "field_type": "n"
            },
            "divider_conductance": {
                "field_name": "Divider Conductance",
                "field_type": "n"
            },
            "ratio_of_divider_edge_glass_conductance_to_center_of_glass_conductance": {
                "field_name": "Ratio of Divider-Edge Glass Conductance to Center-Of-Glass Conductance",
                "field_type": "n"
            },
            "divider_solar_absorptance": {
                "field_name": "Divider Solar Absorptance",
                "field_type": "n"
            },
            "divider_visible_absorptance": {
                "field_name": "Divider Visible Absorptance",
                "field_type": "n"
            },
            "divider_thermal_hemispherical_emissivity": {
                "field_name": "Divider Thermal Hemispherical Emissivity",
                "field_type": "n"
            },
            "outside_reveal_solar_absorptance": {
                "field_name": "Outside Reveal Solar Absorptance",
                "field_type": "n"
            },
            "inside_sill_depth": {
                "field_name": "Inside Sill Depth",
                "field_type": "n"
            },
            "inside_sill_solar_absorptance": {
                "field_name": "Inside Sill Solar Absorptance",
                "field_type": "n"
            },
            "inside_reveal_depth": {
                "field_name": "Inside Reveal Depth",
                "field_type": "n"
            },
            "inside_reveal_solar_absorptance": {
                "field_name": "Inside Reveal Solar Absorptance",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "frame_width",
            "frame_outside_projection",
            "frame_inside_projection",
            "frame_conductance",
            "ratio_of_frame_edge_glass_conductance_to_center_of_glass_conductance",
            "frame_solar_absorptance",
            "frame_visible_absorptance",
            "frame_thermal_hemispherical_emissivity",
            "divider_type",
            "divider_width",
            "number_of_horizontal_dividers",
            "number_of_vertical_dividers",
            "divider_outside_projection",
            "divider_inside_projection",
            "divider_conductance",
            "ratio_of_divider_edge_glass_conductance_to_center_of_glass_conductance",
            "divider_solar_absorptance",
            "divider_visible_absorptance",
            "divider_thermal_hemispherical_emissivity",
            "outside_reveal_solar_absorptance",
            "inside_sill_depth",
            "inside_sill_solar_absorptance",
            "inside_reveal_depth",
            "inside_reveal_solar_absorptance"
        ],
        "alphas": {
            "fields": [
                "name",
                "divider_type"
            ]
        },
        "numerics": {
            "fields": [
                "frame_width",
                "frame_outside_projection",
                "frame_inside_projection",
                "frame_conductance",
                "ratio_of_frame_edge_glass_conductance_to_center_of_glass_conductance",
                "frame_solar_absorptance",
                "frame_visible_absorptance",
                "frame_thermal_hemispherical_emissivity",
                "divider_width",
                "number_of_horizontal_dividers",
                "number_of_vertical_dividers",
                "divider_outside_projection",
                "divider_inside_projection",
                "divider_conductance",
                "ratio_of_divider_edge_glass_conductance_to_center_of_glass_conductance",
                "divider_solar_absorptance",
                "divider_visible_absorptance",
                "divider_thermal_hemispherical_emissivity",
                "outside_reveal_solar_absorptance",
                "inside_sill_depth",
                "inside_sill_solar_absorptance",
                "inside_reveal_depth",
                "inside_reveal_solar_absorptance"
            ]
        }
    },
    "type": "object",
    "memo": "Specifies the dimensions of a window frame, dividers, and inside reveal surfaces. Referenced by the surface objects for exterior windows and glass doors (ref: FenestrationSurface:Detailed, Window, and GlazedDoor).",
    "min_fields": 20.0
}
```
