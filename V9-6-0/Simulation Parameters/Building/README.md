```
{
    "Building": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "north_axis": {
                        "type": "number",
                        "note": "degrees from true North",
                        "units": "deg",
                        "default": 0.0
                    },
                    "terrain": {
                        "type": "string",
                        "note": "Country=FlatOpenCountry | Suburbs=CountryTownsSuburbs | City=CityCenter | Ocean=body of water (5km) | Urban=Urban-Industrial-Forest",
                        "enum": [
                            "",
                            "City",
                            "Country",
                            "Ocean",
                            "Suburbs",
                            "Urban"
                        ],
                        "default": "Suburbs"
                    },
                    "loads_convergence_tolerance_value": {
                        "type": "number",
                        "note": "Loads Convergence Tolerance Value is a change in load from one warmup day to the next",
                        "exclusiveMinimum": 0.0,
                        "maximum": 0.5,
                        "default": 0.04,
                        "units": "W"
                    },
                    "temperature_convergence_tolerance_value": {
                        "type": "number",
                        "units": "deltaC",
                        "exclusiveMinimum": 0.0,
                        "maximum": 0.5,
                        "default": 0.4
                    },
                    "solar_distribution": {
                        "type": "string",
                        "note": "MinimalShadowing | FullExterior | FullInteriorAndExterior | FullExteriorWithReflections | FullInteriorAndExteriorWithReflections",
                        "enum": [
                            "",
                            "FullExterior",
                            "FullExteriorWithReflections",
                            "FullInteriorAndExterior",
                            "FullInteriorAndExteriorWithReflections",
                            "MinimalShadowing"
                        ],
                        "default": "FullExterior"
                    },
                    "maximum_number_of_warmup_days": {
                        "type": "number",
                        "note": "EnergyPlus will only use as many warmup days as needed to reach convergence tolerance. This field's value should NOT be set less than 25.",
                        "exclusiveMinimum": 0.0,
                        "default": 25.0
                    },
                    "minimum_number_of_warmup_days": {
                        "type": "number",
                        "note": "The minimum number of warmup days that produce enough temperature and flux history to start EnergyPlus simulation for all reference buildings was suggested to be 6. However this can lead to excessive run times as warmup days can be repeated needlessly. For faster execution rely on the convergence criteria to detect when warmup is complete. When this field is greater than the maximum warmup days defined previous field the maximum number of warmup days will be reset to the minimum value entered here. Warmup days will be set to be the value you entered. The default is 1.",
                        "exclusiveMinimum": 0.0,
                        "default": 1.0
                    }
                }
            }
        },
        "group": "Simulation Parameters",
        "name": {
            "type": "string",
            "retaincase": true,
            "default": "NONE"
        },
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "north_axis": {
                    "field_name": "North Axis",
                    "field_type": "n"
                },
                "terrain": {
                    "field_name": "Terrain",
                    "field_type": "a"
                },
                "loads_convergence_tolerance_value": {
                    "field_name": "Loads Convergence Tolerance Value",
                    "field_type": "n"
                },
                "temperature_convergence_tolerance_value": {
                    "field_name": "Temperature Convergence Tolerance Value",
                    "field_type": "n"
                },
                "solar_distribution": {
                    "field_name": "Solar Distribution",
                    "field_type": "a"
                },
                "maximum_number_of_warmup_days": {
                    "field_name": "Maximum Number of Warmup Days",
                    "field_type": "n"
                },
                "minimum_number_of_warmup_days": {
                    "field_name": "Minimum Number of Warmup Days",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "north_axis",
                "terrain",
                "loads_convergence_tolerance_value",
                "temperature_convergence_tolerance_value",
                "solar_distribution",
                "maximum_number_of_warmup_days",
                "minimum_number_of_warmup_days"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "terrain",
                    "solar_distribution"
                ]
            },
            "numerics": {
                "fields": [
                    "north_axis",
                    "loads_convergence_tolerance_value",
                    "temperature_convergence_tolerance_value",
                    "maximum_number_of_warmup_days",
                    "minimum_number_of_warmup_days"
                ]
            }
        },
        "type": "object",
        "minProperties": 1,
        "maxProperties": 1,
        "memo": "Describes parameters that are used during the simulation of the building. There are necessary correlations between the entries for this object and some entries in the Site:WeatherStation and Site:HeightVariation objects, specifically the Terrain field.",
        "min_fields": 8.0
    }
}
```
