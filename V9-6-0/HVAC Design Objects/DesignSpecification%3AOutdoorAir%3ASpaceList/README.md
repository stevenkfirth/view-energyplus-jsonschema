```
{
    "DesignSpecification:OutdoorAir:SpaceList": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "space_specs": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "space_name": {
                                    "type": "string",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "SpaceNames"
                                    ]
                                },
                                "space_design_specification_outdoor_air_object_name": {
                                    "type": "string",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "DesignSpecificationOutdoorAirNames"
                                    ]
                                }
                            },
                            "type": "object",
                            "required": [
                                "space_design_specification_outdoor_air_object_name",
                                "space_name"
                            ]
                        }
                    }
                }
            }
        },
        "group": "HVAC Design Objects",
        "name": {
            "type": "string",
            "note": "Name of the List",
            "is_required": true,
            "reference": [
                "DSOASpaceListNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "space_name": {
                    "field_name": "Space Name",
                    "field_type": "a"
                },
                "space_design_specification_outdoor_air_object_name": {
                    "field_name": "Space Design Specification Outdoor Air Object Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name"
            ],
            "alphas": {
                "fields": [
                    "name"
                ],
                "extensions": [
                    "space_name",
                    "space_design_specification_outdoor_air_object_name"
                ]
            },
            "numerics": {
                "fields": []
            },
            "extensibles": [
                "space_name",
                "space_design_specification_outdoor_air_object_name"
            ],
            "extension": "space_specs"
        },
        "type": "object",
        "memo": "Defines a list of DesignSpecification:OutdoorAir names which can be referenced as a group.  The DesignSpecification:OutdoorAir:SpaceList name may be used in Sizing:Zone and  Controller:MechanicalVentilation to specify space-by-space OA requirements and anywhere else that accepts a DesignSpecification:OutdoorAir object name.",
        "min_fields": 3.0,
        "extensible_size": 2.0
    }
}
```
