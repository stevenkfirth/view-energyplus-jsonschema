```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "availability_schedule_name": {
                    "type": "string",
                    "note": "If this field is blank, the controller uses the values from the associated Controller:OutdoorAir. Schedule values greater than 0 indicate mechanical ventilation is enabled",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "demand_controlled_ventilation": {
                    "type": "string",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "No"
                },
                "system_outdoor_air_method": {
                    "type": "string",
                    "enum": [
                        "",
                        "IndoorAirQualityProcedure",
                        "IndoorAirQualityProcedureCombined",
                        "IndoorAirQualityProcedureGenericContaminant",
                        "ProportionalControlBasedOnDesignOARate",
                        "ProportionalControlBasedOnDesignOccupancy",
                        "ProportionalControlBasedOnOccupancySchedule",
                        "Standard62.1VentilationRateProcedure",
                        "Standard62.1VentilationRateProcedureWithLimit",
                        "ZoneSum"
                    ],
                    "default": "Standard62.1VentilationRateProcedure"
                },
                "zone_maximum_outdoor_air_fraction": {
                    "type": "number",
                    "default": 1.0,
                    "exclusiveMinimum": 0.0,
                    "units": "dimensionless"
                },
                "zone_specifications": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "zone_or_zonelist_name": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "ZoneAndZoneListNames"
                                ],
                                "note": "A zone name or a zone list name may be used here"
                            },
                            "design_specification_outdoor_air_object_name": {
                                "type": "string",
                                "note": "Specify the name of a DesignSpecification:OutdoorAir object to specify one set of requirements for the Zone. Use a DesignSpecification:OutdoorAir:SpaceList object name to specify different  requirements for Spaces within the Zone. If left blank, the name will be taken from the Sizing:Zone object for this zone. If no specification is found for this zone, then the default of 0.00944 m3/s-person will be used.",
                                "data_type": "object_list",
                                "object_list": [
                                    "DSOASpaceListNames",
                                    "DesignSpecificationOutdoorAirNames"
                                ]
                            },
                            "design_specification_zone_air_distribution_object_name": {
                                "type": "string",
                                "note": "If left blank, the name will be taken from the Sizing:Zone object for this zone. If no specification is found for this zone, then effectivness will be 1.0 and and secondary recirculation will be zero.",
                                "data_type": "object_list",
                                "object_list": [
                                    "DesignSpecificationZoneAirDistributionNames"
                                ]
                            }
                        },
                        "type": "object",
                        "required": [
                            "zone_or_zonelist_name"
                        ]
                    }
                }
            }
        }
    },
    "group": "Controllers",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "ControllerMechanicalVentNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "availability_schedule_name": {
                "field_name": "Availability Schedule Name",
                "field_type": "a"
            },
            "demand_controlled_ventilation": {
                "field_name": "Demand Controlled Ventilation",
                "field_type": "a"
            },
            "system_outdoor_air_method": {
                "field_name": "System Outdoor Air Method",
                "field_type": "a"
            },
            "zone_maximum_outdoor_air_fraction": {
                "field_name": "Zone Maximum Outdoor Air Fraction",
                "field_type": "n"
            },
            "zone_or_zonelist_name": {
                "field_name": "Zone or ZoneList Name",
                "field_type": "a"
            },
            "design_specification_outdoor_air_object_name": {
                "field_name": "Design Specification Outdoor Air Object Name",
                "field_type": "a"
            },
            "design_specification_zone_air_distribution_object_name": {
                "field_name": "Design Specification Zone Air Distribution Object Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "demand_controlled_ventilation",
            "system_outdoor_air_method",
            "zone_maximum_outdoor_air_fraction"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "demand_controlled_ventilation",
                "system_outdoor_air_method"
            ],
            "extensions": [
                "zone_or_zonelist_name",
                "design_specification_outdoor_air_object_name",
                "design_specification_zone_air_distribution_object_name"
            ]
        },
        "numerics": {
            "fields": [
                "zone_maximum_outdoor_air_fraction"
            ]
        },
        "extensibles": [
            "zone_or_zonelist_name",
            "design_specification_outdoor_air_object_name",
            "design_specification_zone_air_distribution_object_name"
        ],
        "extension": "zone_specifications"
    },
    "type": "object",
    "memo": "This object is used in conjunction with Controller:OutdoorAir to specify outdoor ventilation air based on outdoor air specified in the DesignSpecification:OutdoorAir object The Controller:OutdoorAir object is associated with a specific air loop, so the outdoor air flow rates specified in Controller:MechanicalVentilation correspond to the zones attached to that specific air loop. Duplicate groups of Zone name, Design Specification Outdoor Air Object Name, and Design Specification Zone Air Distribution Object Name to increase allowable number of entries",
    "min_fields": 8.0,
    "extensible_size": 3.0
}
```
