```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "surface_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "SurfaceNames"
                    ]
                },
                "inside_face_heat_source_term_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "The value of this schedule is the source term value for the inside face of this surface If this field is left blank, no inside surface source term will be applied. The schedule values are heat rate per surface area (W/m2), when positive schedule values indicate heat gain and negative values indicates loss."
                },
                "outside_face_heat_source_term_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "The value of this schedule is the source term value for the outside face of this surface If this field is left blank, no outside surface source term will be applied. The schedule values are heat rate per surface area (W/m2), when positive schedule values indicate heat gain and negative values indicates loss."
                }
            },
            "required": [
                "surface_name"
            ]
        }
    },
    "group": "Advanced Construction, Surface, Zone Concepts",
    "legacy_idd": {
        "field_info": {
            "surface_name": {
                "field_name": "Surface Name",
                "field_type": "a"
            },
            "inside_face_heat_source_term_schedule_name": {
                "field_name": "Inside Face Heat Source Term Schedule Name",
                "field_type": "a"
            },
            "outside_face_heat_source_term_schedule_name": {
                "field_name": "Outside Face Heat Source Term Schedule Name",
                "field_type": "a"
            }
        },
        "fields": [
            "surface_name",
            "inside_face_heat_source_term_schedule_name",
            "outside_face_heat_source_term_schedule_name"
        ],
        "alphas": {
            "fields": [
                "surface_name",
                "inside_face_heat_source_term_schedule_name",
                "outside_face_heat_source_term_schedule_name"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "Allows an additional heat source term to be added to the inside or outside surface boundary. A heat source can be added to either or both the inside and outside of the same surface.",
    "min_fields": 3.0
}
```
