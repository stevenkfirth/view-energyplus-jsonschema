```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "distance_from_surface_centroid_to_leading_edge_of_boundary_layer": {
                    "type": "number",
                    "note": "This is the distance from the leading edge of the boundary layer development to the centroid of the surface of interest. The value of this field is used as the distance in the Reynolds number for evaluating the local convection coefficient.",
                    "units": "m"
                },
                "free_stream_water_temperature_schedule": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "units": "C"
                },
                "free_stream_water_velocity_schedule": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "units": "m/s"
                }
            },
            "required": [
                "distance_from_surface_centroid_to_leading_edge_of_boundary_layer",
                "free_stream_water_temperature_schedule"
            ]
        }
    },
    "group": "Advanced Construction, Surface, Zone Concepts",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "SurfacePropUnderWaterNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "distance_from_surface_centroid_to_leading_edge_of_boundary_layer": {
                "field_name": "Distance from Surface Centroid to Leading Edge of Boundary Layer",
                "field_type": "n"
            },
            "free_stream_water_temperature_schedule": {
                "field_name": "Free Stream Water Temperature Schedule",
                "field_type": "a"
            },
            "free_stream_water_velocity_schedule": {
                "field_name": "Free Stream Water Velocity Schedule",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "distance_from_surface_centroid_to_leading_edge_of_boundary_layer",
            "free_stream_water_temperature_schedule",
            "free_stream_water_velocity_schedule"
        ],
        "alphas": {
            "fields": [
                "name",
                "free_stream_water_temperature_schedule",
                "free_stream_water_velocity_schedule"
            ]
        },
        "numerics": {
            "fields": [
                "distance_from_surface_centroid_to_leading_edge_of_boundary_layer"
            ]
        }
    },
    "type": "object",
    "memo": "This object sets up a convective water boundary condition for a surface The free stream temperature and velocity are scheduled. If the free stream velocity is zero, the surface will naturally convect with the surrounding water.",
    "min_fields": 3.0
}
```
