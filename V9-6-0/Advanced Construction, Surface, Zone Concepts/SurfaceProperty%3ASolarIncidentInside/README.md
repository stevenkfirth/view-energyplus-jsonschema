```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "surface_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "SurfaceNames"
                    ]
                },
                "construction_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ConstructionNames"
                    ]
                },
                "inside_surface_incident_sun_solar_radiation_schedule_name": {
                    "type": "string",
                    "note": "Values in schedule are expected to be in W/m2",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                }
            },
            "required": [
                "surface_name",
                "construction_name",
                "inside_surface_incident_sun_solar_radiation_schedule_name"
            ]
        }
    },
    "group": "Advanced Construction, Surface, Zone Concepts",
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
            "surface_name": {
                "field_name": "Surface Name",
                "field_type": "a"
            },
            "construction_name": {
                "field_name": "Construction Name",
                "field_type": "a"
            },
            "inside_surface_incident_sun_solar_radiation_schedule_name": {
                "field_name": "Inside Surface Incident Sun Solar Radiation Schedule Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "surface_name",
            "construction_name",
            "inside_surface_incident_sun_solar_radiation_schedule_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "surface_name",
                "construction_name",
                "inside_surface_incident_sun_solar_radiation_schedule_name"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "Used to provide incident solar radiation on the inside of the surface. Reference surface-construction pair and if that pair is used in a simulation, then program will use value provided in schedule instead of calculating it."
}
```
