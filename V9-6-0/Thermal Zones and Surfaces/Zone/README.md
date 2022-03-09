```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "direction_of_relative_north": {
                    "type": "number",
                    "units": "deg",
                    "default": 0.0
                },
                "x_origin": {
                    "type": "number",
                    "units": "m",
                    "default": 0.0
                },
                "y_origin": {
                    "type": "number",
                    "units": "m",
                    "default": 0.0
                },
                "z_origin": {
                    "type": "number",
                    "units": "m",
                    "default": 0.0
                },
                "type": {
                    "type": "number",
                    "maximum": 1.0,
                    "minimum": 1.0,
                    "default": 1.0
                },
                "multiplier": {
                    "type": "number",
                    "minimum": 1.0,
                    "default": 1.0
                },
                "ceiling_height": {
                    "note": "If this field is 0.0, negative or autocalculate, then the average height of the zone is automatically calculated and used in subsequent calculations. If this field is positive, then the number entered here will be used. Note that the Zone Ceiling Height is the distance from the Floor to the Ceiling in the Zone, not an absolute height from the ground.",
                    "units": "m",
                    "default": "Autocalculate",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string",
                            "enum": [
                                "",
                                "Autocalculate"
                            ]
                        }
                    ]
                },
                "volume": {
                    "note": "If this field is 0.0, negative or autocalculate, then the volume of the zone is automatically calculated and used in subsequent calculations. If this field is positive, then the number entered here will be used.",
                    "units": "m3",
                    "default": "Autocalculate",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string",
                            "enum": [
                                "",
                                "Autocalculate"
                            ]
                        }
                    ]
                },
                "floor_area": {
                    "note": "If this field is 0.0, negative or autocalculate, then the floor area of the zone is automatically calculated and used in subsequent calculations. If this field is positive, then the number entered here will be used.",
                    "units": "m2",
                    "default": "Autocalculate",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string",
                            "enum": [
                                "",
                                "Autocalculate"
                            ]
                        }
                    ]
                },
                "zone_inside_convection_algorithm": {
                    "type": "string",
                    "enum": [
                        "",
                        "ASTMC1340",
                        "AdaptiveConvectionAlgorithm",
                        "CeilingDiffuser",
                        "Simple",
                        "TARP",
                        "TrombeWall"
                    ],
                    "note": "Will default to same value as SurfaceConvectionAlgorithm:Inside object setting this field overrides the default SurfaceConvectionAlgorithm:Inside for this zone Simple = constant natural convection (ASHRAE) TARP = variable natural convection based on temperature difference (ASHRAE) CeilingDiffuser = ACH based forced and mixed convection correlations for ceiling diffuser configuration with simple natural convection limit AdaptiveConvectionAlgorithm = dynamic selection of convection models based on conditions TrombeWall = variable natural convection in an enclosed rectangular cavity ASTMC1340 = mixed convection correlations specified for attic zone"
                },
                "zone_outside_convection_algorithm": {
                    "type": "string",
                    "note": "Will default to same value as SurfaceConvectionAlgorithm:Outside object setting this field overrides the default SurfaceConvectionAlgorithm:Outside for this zone SimpleCombined = Combined radiation and convection coefficient using simple ASHRAE model TARP = correlation from models developed by ASHRAE, Walton, and Sparrow et. al. MoWiTT = correlation from measurements by Klems and Yazdanian for smooth surfaces DOE-2 = correlation from measurements by Klems and Yazdanian for rough surfaces AdaptiveConvectionAlgorithm = dynamic selection of correlations based on conditions",
                    "enum": [
                        "",
                        "AdaptiveConvectionAlgorithm",
                        "DOE-2",
                        "MoWiTT",
                        "SimpleCombined",
                        "TARP"
                    ]
                },
                "part_of_total_floor_area": {
                    "type": "string",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "Yes"
                }
            }
        }
    },
    "group": "Thermal Zones and Surfaces",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "AirflowNetworkNodeAndZoneNames",
            "OutFaceEnvNames",
            "ZoneAndZoneListNames",
            "ZoneNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "direction_of_relative_north": {
                "field_name": "Direction of Relative North",
                "field_type": "n"
            },
            "x_origin": {
                "field_name": "X Origin",
                "field_type": "n"
            },
            "y_origin": {
                "field_name": "Y Origin",
                "field_type": "n"
            },
            "z_origin": {
                "field_name": "Z Origin",
                "field_type": "n"
            },
            "type": {
                "field_name": "Type",
                "field_type": "n"
            },
            "multiplier": {
                "field_name": "Multiplier",
                "field_type": "n"
            },
            "ceiling_height": {
                "field_name": "Ceiling Height",
                "field_type": "n"
            },
            "volume": {
                "field_name": "Volume",
                "field_type": "n"
            },
            "floor_area": {
                "field_name": "Floor Area",
                "field_type": "n"
            },
            "zone_inside_convection_algorithm": {
                "field_name": "Zone Inside Convection Algorithm",
                "field_type": "a"
            },
            "zone_outside_convection_algorithm": {
                "field_name": "Zone Outside Convection Algorithm",
                "field_type": "a"
            },
            "part_of_total_floor_area": {
                "field_name": "Part of Total Floor Area",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "direction_of_relative_north",
            "x_origin",
            "y_origin",
            "z_origin",
            "type",
            "multiplier",
            "ceiling_height",
            "volume",
            "floor_area",
            "zone_inside_convection_algorithm",
            "zone_outside_convection_algorithm",
            "part_of_total_floor_area"
        ],
        "alphas": {
            "fields": [
                "name",
                "zone_inside_convection_algorithm",
                "zone_outside_convection_algorithm",
                "part_of_total_floor_area"
            ]
        },
        "numerics": {
            "fields": [
                "direction_of_relative_north",
                "x_origin",
                "y_origin",
                "z_origin",
                "type",
                "multiplier",
                "ceiling_height",
                "volume",
                "floor_area"
            ]
        }
    },
    "type": "object",
    "memo": "Defines a thermal zone of the building. Every zone contains one or more Spaces. Space is an optional input.  If a Zone has no Space(s) specified in input then a default Space named <Zone Name> will be created. If some surfaces in a Zone are assigned to a space and some are not, then a default Space named <Zone Name>-Remainder will be created.  Input references to Space Names must have a matching Space object (default space names may not be referenced except in output variable keys).",
    "format": "vertices"
}
```
