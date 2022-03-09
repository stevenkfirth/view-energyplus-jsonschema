```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "building_location_latitude_schedule": {
                    "type": "string",
                    "note": "The name of a schedule that defines the latitude of the building at any time. If not entered, the latitude defined in the Site:Location, or the default latitude, will be used for the entirety of the simulation",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "building_location_longitude_schedule": {
                    "type": "string",
                    "note": "The name of a schedule that defines the longitude of the building at any time. If not entered, the longitude defined in the Site:Location, or the default longitude, will be used for the entirety of the simulation",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "building_location_orientation_schedule": {
                    "type": "string",
                    "note": "The name of a schedule that defines the orientation of the building at any time. This orientation is based on a change from the original orientation. -- NEED TO REFINE THIS If not entered, the original orientation will be used for the entirety of the simulation",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                }
            }
        }
    },
    "group": "Location and Climate",
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
            "building_location_latitude_schedule": {
                "field_name": "Building Location Latitude Schedule",
                "field_type": "a"
            },
            "building_location_longitude_schedule": {
                "field_name": "Building Location Longitude Schedule",
                "field_type": "a"
            },
            "building_location_orientation_schedule": {
                "field_name": "Building Location Orientation Schedule",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "building_location_latitude_schedule",
            "building_location_longitude_schedule",
            "building_location_orientation_schedule"
        ],
        "alphas": {
            "fields": [
                "name",
                "building_location_latitude_schedule",
                "building_location_longitude_schedule",
                "building_location_orientation_schedule"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "maxProperties": 1,
    "memo": "Captures the scheduling of a moving/reorienting building, or more likely a vessel",
    "min_fields": 1.0
}
```
