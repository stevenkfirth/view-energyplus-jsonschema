```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "construction_name": {
                    "type": "string",
                    "note": "To be matched with a construction in this input file",
                    "data_type": "object_list",
                    "object_list": [
                        "ConstructionNames"
                    ]
                },
                "building_surface_name": {
                    "type": "string",
                    "note": "Name of Surface (Wall, usually) the Door is on (i.e., Base Surface) Door assumes the azimuth and tilt angles of the surface it is on.",
                    "data_type": "object_list",
                    "object_list": [
                        "SurfaceNames"
                    ]
                },
                "outside_boundary_condition_object": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "OutFaceEnvNames"
                    ],
                    "note": "Specify a surface name in an adjacent zone for known interior doors. Specify a zone name of an adjacent zone to automatically generate the interior door in the adjacent zone. a blank field will set up a Window in an adjacent zone (same zone as adjacent to base surface)"
                },
                "multiplier": {
                    "type": "number",
                    "note": "Used only for Surface Type = WINDOW, GLASSDOOR or DOOR Non-integer values will be truncated to integer",
                    "default": 1.0,
                    "minimum": 1.0
                },
                "starting_x_coordinate": {
                    "type": "number",
                    "note": "Door starting coordinate is specified relative to the Base Surface origin.",
                    "units": "m"
                },
                "starting_z_coordinate": {
                    "type": "number",
                    "note": "How far up the wall the Door starts. (in 2-d, this would be a Y Coordinate)",
                    "units": "m"
                },
                "length": {
                    "type": "number",
                    "units": "m"
                },
                "height": {
                    "type": "number",
                    "units": "m"
                }
            },
            "required": [
                "construction_name",
                "building_surface_name"
            ]
        }
    },
    "group": "Thermal Zones and Surfaces",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "AllHeatTranAngFacNames",
            "AllHeatTranSurfNames",
            "AllShadingAndHTSurfNames",
            "OutFaceEnvNames",
            "SubSurfNames",
            "SurfAndSubSurfNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "construction_name": {
                "field_name": "Construction Name",
                "field_type": "a"
            },
            "building_surface_name": {
                "field_name": "Building Surface Name",
                "field_type": "a"
            },
            "outside_boundary_condition_object": {
                "field_name": "Outside Boundary Condition Object",
                "field_type": "a"
            },
            "multiplier": {
                "field_name": "Multiplier",
                "field_type": "n"
            },
            "starting_x_coordinate": {
                "field_name": "Starting X Coordinate",
                "field_type": "n"
            },
            "starting_z_coordinate": {
                "field_name": "Starting Z Coordinate",
                "field_type": "n"
            },
            "length": {
                "field_name": "Length",
                "field_type": "n"
            },
            "height": {
                "field_name": "Height",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "construction_name",
            "building_surface_name",
            "outside_boundary_condition_object",
            "multiplier",
            "starting_x_coordinate",
            "starting_z_coordinate",
            "length",
            "height"
        ],
        "alphas": {
            "fields": [
                "name",
                "construction_name",
                "building_surface_name",
                "outside_boundary_condition_object"
            ]
        },
        "numerics": {
            "fields": [
                "multiplier",
                "starting_x_coordinate",
                "starting_z_coordinate",
                "length",
                "height"
            ]
        }
    },
    "type": "object",
    "memo": "Allows for simplified entry of interzone (glass interior) doors (adjacent to other zones)."
}
```
