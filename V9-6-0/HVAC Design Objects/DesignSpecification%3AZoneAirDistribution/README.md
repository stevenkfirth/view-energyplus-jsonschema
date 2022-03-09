```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "zone_air_distribution_effectiveness_in_cooling_mode": {
                    "type": "number",
                    "default": 1.0,
                    "exclusiveMinimum": 0.0,
                    "units": "dimensionless"
                },
                "zone_air_distribution_effectiveness_in_heating_mode": {
                    "type": "number",
                    "default": 1.0,
                    "exclusiveMinimum": 0.0,
                    "units": "dimensionless"
                },
                "zone_air_distribution_effectiveness_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "optionally used to replace Zone Air Distribution Effectiveness in Cooling and Heating Mode"
                },
                "zone_secondary_recirculation_fraction": {
                    "type": "number",
                    "default": 0.0,
                    "minimum": 0.0,
                    "units": "dimensionless"
                },
                "minimum_zone_ventilation_efficiency": {
                    "type": "number",
                    "default": 0.0,
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "units": "dimensionless"
                }
            }
        }
    },
    "group": "HVAC Design Objects",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "DesignSpecificationZoneAirDistributionNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "zone_air_distribution_effectiveness_in_cooling_mode": {
                "field_name": "Zone Air Distribution Effectiveness in Cooling Mode",
                "field_type": "n"
            },
            "zone_air_distribution_effectiveness_in_heating_mode": {
                "field_name": "Zone Air Distribution Effectiveness in Heating Mode",
                "field_type": "n"
            },
            "zone_air_distribution_effectiveness_schedule_name": {
                "field_name": "Zone Air Distribution Effectiveness Schedule Name",
                "field_type": "a"
            },
            "zone_secondary_recirculation_fraction": {
                "field_name": "Zone Secondary Recirculation Fraction",
                "field_type": "n"
            },
            "minimum_zone_ventilation_efficiency": {
                "field_name": "Minimum Zone Ventilation Efficiency",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "zone_air_distribution_effectiveness_in_cooling_mode",
            "zone_air_distribution_effectiveness_in_heating_mode",
            "zone_air_distribution_effectiveness_schedule_name",
            "zone_secondary_recirculation_fraction",
            "minimum_zone_ventilation_efficiency"
        ],
        "alphas": {
            "fields": [
                "name",
                "zone_air_distribution_effectiveness_schedule_name"
            ]
        },
        "numerics": {
            "fields": [
                "zone_air_distribution_effectiveness_in_cooling_mode",
                "zone_air_distribution_effectiveness_in_heating_mode",
                "zone_secondary_recirculation_fraction",
                "minimum_zone_ventilation_efficiency"
            ]
        }
    },
    "type": "object",
    "memo": "This object is used to describe zone air distribution in terms of air distribution effectiveness and secondary recirculation fraction. It is referenced by Sizing:Zone and Controller:MechanicalVentilation objects",
    "min_fields": 1.0
}
```
