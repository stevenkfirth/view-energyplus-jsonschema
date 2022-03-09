```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "insulation_type": {
                    "type": "string",
                    "enum": [
                        "Inside",
                        "Outside"
                    ]
                },
                "surface_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "SurfaceNames"
                    ]
                },
                "material_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "MaterialName"
                    ]
                },
                "schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                }
            },
            "required": [
                "insulation_type",
                "surface_name",
                "material_name",
                "schedule_name"
            ]
        }
    },
    "group": "Advanced Construction, Surface, Zone Concepts",
    "legacy_idd": {
        "field_info": {
            "insulation_type": {
                "field_name": "Insulation Type",
                "field_type": "a"
            },
            "surface_name": {
                "field_name": "Surface Name",
                "field_type": "a"
            },
            "material_name": {
                "field_name": "Material Name",
                "field_type": "a"
            },
            "schedule_name": {
                "field_name": "Schedule Name",
                "field_type": "a"
            }
        },
        "fields": [
            "insulation_type",
            "surface_name",
            "material_name",
            "schedule_name"
        ],
        "alphas": {
            "fields": [
                "insulation_type",
                "surface_name",
                "material_name",
                "schedule_name"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "Exterior or Interior Insulation on opaque surfaces"
}
```
