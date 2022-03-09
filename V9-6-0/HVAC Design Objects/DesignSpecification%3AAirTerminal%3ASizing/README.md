```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "fraction_of_design_cooling_load": {
                    "type": "number",
                    "note": "The fraction of the design sensible cooling load to be met by this terminal unit. This fraction is applied after the Zone Cooling Sizing Factor (see Sizing:Zone).",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "default": 1.0
                },
                "cooling_design_supply_air_temperature_difference_ratio": {
                    "type": "number",
                    "note": "This ratio adjusts the supply air temperature difference used to calculate the cooling design supply air flow rate for this terminal unit.",
                    "units": "dimensionless",
                    "exclusiveMinimum": 0.0,
                    "default": 1.0
                },
                "fraction_of_design_heating_load": {
                    "type": "number",
                    "note": "The fraction of the design sensible heating load to be met by this terminal unit. This fraction is applied after the Zone Heating Sizing Factor (see Sizing:Zone).",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "default": 1.0
                },
                "heating_design_supply_air_temperature_difference_ratio": {
                    "type": "number",
                    "note": "This ratio adjusts the supply air temperature difference used to calculate the heating design supply air flow rate for this terminal unit.",
                    "units": "dimensionless",
                    "exclusiveMinimum": 0.0,
                    "default": 1.0
                },
                "fraction_of_minimum_outdoor_air_flow": {
                    "type": "number",
                    "note": "The fraction of the zone minimum outdoor air requirement to be met by this terminal unit.",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "default": 1.0
                }
            }
        }
    },
    "group": "HVAC Design Objects",
    "name": {
        "type": "string",
        "note": "This name may be referenced by a ZoneHVAC:AirDistributionUnit object.",
        "is_required": true,
        "reference": [
            "DesignSpecificationAirTerminalSizingName"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "fraction_of_design_cooling_load": {
                "field_name": "Fraction of Design Cooling Load",
                "field_type": "n"
            },
            "cooling_design_supply_air_temperature_difference_ratio": {
                "field_name": "Cooling Design Supply Air Temperature Difference Ratio",
                "field_type": "n"
            },
            "fraction_of_design_heating_load": {
                "field_name": "Fraction of Design Heating Load",
                "field_type": "n"
            },
            "heating_design_supply_air_temperature_difference_ratio": {
                "field_name": "Heating Design Supply Air Temperature Difference Ratio",
                "field_type": "n"
            },
            "fraction_of_minimum_outdoor_air_flow": {
                "field_name": "Fraction of Minimum Outdoor Air Flow",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "fraction_of_design_cooling_load",
            "cooling_design_supply_air_temperature_difference_ratio",
            "fraction_of_design_heating_load",
            "heating_design_supply_air_temperature_difference_ratio",
            "fraction_of_minimum_outdoor_air_flow"
        ],
        "alphas": {
            "fields": [
                "name"
            ]
        },
        "numerics": {
            "fields": [
                "fraction_of_design_cooling_load",
                "cooling_design_supply_air_temperature_difference_ratio",
                "fraction_of_design_heating_load",
                "heating_design_supply_air_temperature_difference_ratio",
                "fraction_of_minimum_outdoor_air_flow"
            ]
        }
    },
    "type": "object",
    "memo": "This object is used to scale the sizing of air terminal units.",
    "min_fields": 1.0
}
```
