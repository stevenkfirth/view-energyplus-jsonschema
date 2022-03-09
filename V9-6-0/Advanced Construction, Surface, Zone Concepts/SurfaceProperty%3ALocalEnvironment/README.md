```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "exterior_surface_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "SurfaceNames"
                    ],
                    "note": "Enter the name of an exterior surface object"
                },
                "external_shading_fraction_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Enter the name of a Schedule object"
                },
                "surrounding_surfaces_object_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "SurroundingSurfacesNames"
                    ],
                    "note": "Enter the name of a SurfaceProperty:SurroundingSurfaces object"
                },
                "outdoor_air_node_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "OutdoorAirNodeNames"
                    ],
                    "note": "Enter the name of an OutdoorAir:Node object"
                }
            }
        }
    },
    "group": "Advanced Construction, Surface, Zone Concepts",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "SurfaceLocalEnvironmentNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "exterior_surface_name": {
                "field_name": "Exterior Surface Name",
                "field_type": "a"
            },
            "external_shading_fraction_schedule_name": {
                "field_name": "External Shading Fraction Schedule Name",
                "field_type": "a"
            },
            "surrounding_surfaces_object_name": {
                "field_name": "Surrounding Surfaces Object Name",
                "field_type": "a"
            },
            "outdoor_air_node_name": {
                "field_name": "Outdoor Air Node Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "exterior_surface_name",
            "external_shading_fraction_schedule_name",
            "surrounding_surfaces_object_name",
            "outdoor_air_node_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "exterior_surface_name",
                "external_shading_fraction_schedule_name",
                "surrounding_surfaces_object_name",
                "outdoor_air_node_name"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "This object defines the local environment properties of an exterior surface. One or more environment properties have to be defined and linked to the exterior surface.",
    "min_fields": 3.0
}
```
