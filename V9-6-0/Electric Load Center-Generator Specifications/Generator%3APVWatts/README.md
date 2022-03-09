```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "pvwatts_version": {
                    "type": "string",
                    "enum": [
                        "5"
                    ]
                },
                "dc_system_capacity": {
                    "type": "number",
                    "note": "Nameplate rated DC system capacity in watts",
                    "units": "W",
                    "exclusiveMinimum": 0.0
                },
                "module_type": {
                    "type": "string",
                    "enum": [
                        "Premium",
                        "Standard",
                        "ThinFilm"
                    ]
                },
                "array_type": {
                    "type": "string",
                    "enum": [
                        "FixedOpenRack",
                        "FixedRoofMounted",
                        "OneAxis",
                        "OneAxisBacktracking",
                        "TwoAxis"
                    ]
                },
                "system_losses": {
                    "type": "number",
                    "default": 0.14,
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "array_geometry_type": {
                    "type": "string",
                    "note": "TiltAzimuth - The tilt and azimuth angles are specified in the next two fields. An unshaded array is assumed. Surface - The array geometry (tilt and azimuth) as well as shading is determined from surface referenced.",
                    "default": "TiltAzimuth",
                    "enum": [
                        "",
                        "Surface",
                        "TiltAzimuth"
                    ]
                },
                "tilt_angle": {
                    "type": "number",
                    "note": "The tilt angle is the angle from horizontal of the photovoltaic modules in the array.",
                    "units": "deg",
                    "default": 20.0,
                    "minimum": 0.0,
                    "maximum": 90.0
                },
                "azimuth_angle": {
                    "type": "number",
                    "note": "For a fixed array, the azimuth angle is the angle clockwise from true north describing the direction that the array faces. For an array with one-axis tracking, the azimuth angle is the angle clockwise from true north of the axis of rotation.",
                    "units": "deg",
                    "default": 180.0,
                    "minimum": 0.0,
                    "exclusiveMaximum": 360.0
                },
                "surface_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "AllShadingAndHTSurfNames"
                    ]
                },
                "ground_coverage_ratio": {
                    "type": "number",
                    "note": "Applies only to arrays with one-axis tracking and is the ratio of module surface area to area of the ground or roof occupied by the array.",
                    "default": 0.4,
                    "minimum": 0.0,
                    "maximum": 1.0
                }
            },
            "required": [
                "dc_system_capacity",
                "module_type",
                "array_type"
            ]
        }
    },
    "group": "Electric Load Center-Generator Specifications",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "GeneratorNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "pvwatts_version": {
                "field_name": "PVWatts Version",
                "field_type": "a"
            },
            "dc_system_capacity": {
                "field_name": "DC System Capacity",
                "field_type": "n"
            },
            "module_type": {
                "field_name": "Module Type",
                "field_type": "a"
            },
            "array_type": {
                "field_name": "Array Type",
                "field_type": "a"
            },
            "system_losses": {
                "field_name": "System Losses",
                "field_type": "n"
            },
            "array_geometry_type": {
                "field_name": "Array Geometry Type",
                "field_type": "a"
            },
            "tilt_angle": {
                "field_name": "Tilt Angle",
                "field_type": "n"
            },
            "azimuth_angle": {
                "field_name": "Azimuth Angle",
                "field_type": "n"
            },
            "surface_name": {
                "field_name": "Surface Name",
                "field_type": "a"
            },
            "ground_coverage_ratio": {
                "field_name": "Ground Coverage Ratio",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "pvwatts_version",
            "dc_system_capacity",
            "module_type",
            "array_type",
            "system_losses",
            "array_geometry_type",
            "tilt_angle",
            "azimuth_angle",
            "surface_name",
            "ground_coverage_ratio"
        ],
        "alphas": {
            "fields": [
                "name",
                "pvwatts_version",
                "module_type",
                "array_type",
                "array_geometry_type",
                "surface_name"
            ]
        },
        "numerics": {
            "fields": [
                "dc_system_capacity",
                "system_losses",
                "tilt_angle",
                "azimuth_angle",
                "ground_coverage_ratio"
            ]
        }
    },
    "type": "object",
    "memo": "Describes a simple set of inputs for an array of photovoltaic (PV) modules as described in the PVWatts software. A series of different PVWatts arrays can be connected to a single electric load center (preferably through an ElectricLoadCenter:Inverter:PVWatts). Array tilt and azimuth can be either specified on this object or taken from a referenced building surface or shading surface. If a surface is specified, the array participates normally in all shading calculations.",
    "min_fields": 9.0
}
```
