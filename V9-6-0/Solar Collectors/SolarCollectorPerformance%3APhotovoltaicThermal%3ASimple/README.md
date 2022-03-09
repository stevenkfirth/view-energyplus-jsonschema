```
{
    "SolarCollectorPerformance:PhotovoltaicThermal:Simple": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "fraction_of_surface_area_with_active_thermal_collector": {
                        "type": "number",
                        "units": "dimensionless",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0
                    },
                    "thermal_conversion_efficiency_input_mode_type": {
                        "type": "string",
                        "enum": [
                            "Fixed",
                            "Scheduled"
                        ]
                    },
                    "value_for_thermal_conversion_efficiency_if_fixed": {
                        "type": "number",
                        "note": "Efficiency = (thermal power generated [W])/(incident solar[W])",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "thermal_conversion_efficiency_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "front_surface_emittance": {
                        "type": "number",
                        "default": 0.84,
                        "exclusiveMinimum": 0.0,
                        "exclusiveMaximum": 1.0
                    }
                },
                "required": [
                    "fraction_of_surface_area_with_active_thermal_collector"
                ]
            }
        },
        "group": "Solar Collectors",
        "name": {
            "type": "string",
            "reference": [
                "FlatPlatePVTParameters"
            ]
        },
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "fraction_of_surface_area_with_active_thermal_collector": {
                    "field_name": "Fraction of Surface Area with Active Thermal Collector",
                    "field_type": "n"
                },
                "thermal_conversion_efficiency_input_mode_type": {
                    "field_name": "Thermal Conversion Efficiency Input Mode Type",
                    "field_type": "a"
                },
                "value_for_thermal_conversion_efficiency_if_fixed": {
                    "field_name": "Value for Thermal Conversion Efficiency if Fixed",
                    "field_type": "n"
                },
                "thermal_conversion_efficiency_schedule_name": {
                    "field_name": "Thermal Conversion Efficiency Schedule Name",
                    "field_type": "a"
                },
                "front_surface_emittance": {
                    "field_name": "Front Surface Emittance",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "fraction_of_surface_area_with_active_thermal_collector",
                "thermal_conversion_efficiency_input_mode_type",
                "value_for_thermal_conversion_efficiency_if_fixed",
                "thermal_conversion_efficiency_schedule_name",
                "front_surface_emittance"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "thermal_conversion_efficiency_input_mode_type",
                    "thermal_conversion_efficiency_schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "fraction_of_surface_area_with_active_thermal_collector",
                    "value_for_thermal_conversion_efficiency_if_fixed",
                    "front_surface_emittance"
                ]
            }
        },
        "type": "object",
        "memo": "Thermal performance parameters for a hybrid photovoltaic-thermal (PVT) solar collector."
    }
}
```
