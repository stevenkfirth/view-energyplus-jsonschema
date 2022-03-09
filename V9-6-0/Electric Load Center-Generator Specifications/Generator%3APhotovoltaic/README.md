```
{
    "Generator:Photovoltaic": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "surface_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AllShadingAndHTSurfNames"
                        ]
                    },
                    "photovoltaic_performance_object_type": {
                        "type": "string",
                        "enum": [
                            "PhotovoltaicPerformance:EquivalentOne-Diode",
                            "PhotovoltaicPerformance:Sandia",
                            "PhotovoltaicPerformance:Simple"
                        ]
                    },
                    "module_performance_name": {
                        "type": "string",
                        "note": "PV array modeling details",
                        "data_type": "object_list",
                        "object_list": [
                            "PVModules"
                        ]
                    },
                    "heat_transfer_integration_mode": {
                        "type": "string",
                        "enum": [
                            "",
                            "Decoupled",
                            "DecoupledUllebergDynamic",
                            "IntegratedExteriorVentedCavity",
                            "IntegratedSurfaceOutsideFace",
                            "IntegratedTranspiredCollector",
                            "PhotovoltaicThermalSolarCollector"
                        ],
                        "default": "Decoupled"
                    },
                    "number_of_series_strings_in_parallel": {
                        "type": "number",
                        "note": "number of series-wired strings of PV modules that are in parallel",
                        "default": 1.0,
                        "units": "dimensionless",
                        "minimum": 1.0
                    },
                    "number_of_modules_in_series": {
                        "type": "number",
                        "note": "Number of PV modules wired in series for each string.",
                        "default": 1.0,
                        "units": "dimensionless",
                        "minimum": 1.0
                    }
                },
                "required": [
                    "surface_name"
                ]
            }
        },
        "group": "Electric Load Center-Generator Specifications",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "GeneratorNames",
                "PVGeneratorNames"
            ]
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
                "photovoltaic_performance_object_type": {
                    "field_name": "Photovoltaic Performance Object Type",
                    "field_type": "a"
                },
                "module_performance_name": {
                    "field_name": "Module Performance Name",
                    "field_type": "a"
                },
                "heat_transfer_integration_mode": {
                    "field_name": "Heat Transfer Integration Mode",
                    "field_type": "a"
                },
                "number_of_series_strings_in_parallel": {
                    "field_name": "Number of Series Strings in Parallel",
                    "field_type": "n"
                },
                "number_of_modules_in_series": {
                    "field_name": "Number of Modules in Series",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "surface_name",
                "photovoltaic_performance_object_type",
                "module_performance_name",
                "heat_transfer_integration_mode",
                "number_of_series_strings_in_parallel",
                "number_of_modules_in_series"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "surface_name",
                    "photovoltaic_performance_object_type",
                    "module_performance_name",
                    "heat_transfer_integration_mode"
                ]
            },
            "numerics": {
                "fields": [
                    "number_of_series_strings_in_parallel",
                    "number_of_modules_in_series"
                ]
            }
        },
        "type": "object",
        "memo": "Describes an array of photovoltaic (PV) modules. A series of different PV arrays can be connected to a single electric load center (and inverter) by listing them all in an ElectricLoadCenter:Generator object. PV performance is taken from the referenced PhotovoltaicPerformance:* object. Array tilt, azimuth, and gross area are taken from the referenced building surface or shading surface. The array surface participates normally in all shading calculations."
    }
}
```
