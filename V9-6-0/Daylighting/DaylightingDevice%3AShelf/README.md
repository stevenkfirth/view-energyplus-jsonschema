```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "window_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "SubSurfNames"
                    ]
                },
                "inside_shelf_name": {
                    "type": "string",
                    "note": "This must refer to a BuildingSurface:Detailed or equivalent object This surface must be its own Surface for other side boundary conditions.",
                    "data_type": "object_list",
                    "object_list": [
                        "SurfaceNames"
                    ]
                },
                "outside_shelf_name": {
                    "type": "string",
                    "note": "This must refer to a Shading:Zone:Detailed object",
                    "data_type": "object_list",
                    "object_list": [
                        "AttachedShadingSurfNames"
                    ]
                },
                "outside_shelf_construction_name": {
                    "type": "string",
                    "note": "Required if outside shelf is specified",
                    "data_type": "object_list",
                    "object_list": [
                        "ConstructionNames"
                    ]
                },
                "view_factor_to_outside_shelf": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                }
            },
            "required": [
                "window_name"
            ]
        }
    },
    "group": "Daylighting",
    "name": {
        "type": "string",
        "is_required": true
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "window_name": {
                "field_name": "Window Name",
                "field_type": "a"
            },
            "inside_shelf_name": {
                "field_name": "Inside Shelf Name",
                "field_type": "a"
            },
            "outside_shelf_name": {
                "field_name": "Outside Shelf Name",
                "field_type": "a"
            },
            "outside_shelf_construction_name": {
                "field_name": "Outside Shelf Construction Name",
                "field_type": "a"
            },
            "view_factor_to_outside_shelf": {
                "field_name": "View Factor to Outside Shelf",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "window_name",
            "inside_shelf_name",
            "outside_shelf_name",
            "outside_shelf_construction_name",
            "view_factor_to_outside_shelf"
        ],
        "alphas": {
            "fields": [
                "name",
                "window_name",
                "inside_shelf_name",
                "outside_shelf_name",
                "outside_shelf_construction_name"
            ]
        },
        "numerics": {
            "fields": [
                "view_factor_to_outside_shelf"
            ]
        }
    },
    "type": "object",
    "memo": "Defines a daylighting which can have an inside shelf, an outside shelf, or both. The inside shelf is defined as a building surface and the outside shelf is defined as a shading surface."
}
```
