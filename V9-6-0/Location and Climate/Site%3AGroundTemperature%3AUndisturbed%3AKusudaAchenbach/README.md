```
{
    "Site:GroundTemperature:Undisturbed:KusudaAchenbach": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "soil_thermal_conductivity": {
                        "type": "number",
                        "units": "W/m-K",
                        "exclusiveMinimum": 0.0
                    },
                    "soil_density": {
                        "type": "number",
                        "units": "kg/m3",
                        "exclusiveMinimum": 0.0
                    },
                    "soil_specific_heat": {
                        "type": "number",
                        "units": "J/kg-K",
                        "exclusiveMinimum": 0.0
                    },
                    "average_soil_surface_temperature": {
                        "type": "number",
                        "units": "C",
                        "note": "Annual average surface temperature If left blank the Site:GroundTemperature:Shallow object must be included in the input The soil temperature, amplitude, and phase shift must all be included or omitted together"
                    },
                    "average_amplitude_of_surface_temperature": {
                        "type": "number",
                        "units": "deltaC",
                        "minimum": 0.0,
                        "note": "Annual average surface temperature variation from average. If left blank the Site:GroundTemperature:Shallow object must be included in the input The soil temperature, amplitude, and phase shift must all be included or omitted together"
                    },
                    "phase_shift_of_minimum_surface_temperature": {
                        "type": "number",
                        "units": "days",
                        "minimum": 0.0,
                        "exclusiveMaximum": 365.0,
                        "note": "The phase shift of minimum surface temperature, or the day of the year when the minimum surface temperature occurs. If left blank the Site:GroundTemperature:Shallow object must be included in the input The soil temperature, amplitude, and phase shift must all be included or omitted together"
                    }
                },
                "required": [
                    "soil_thermal_conductivity",
                    "soil_density",
                    "soil_specific_heat"
                ]
            }
        },
        "group": "Location and Climate",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "UndisturbedGroundTempModels"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "soil_thermal_conductivity": {
                    "field_name": "Soil Thermal Conductivity",
                    "field_type": "n"
                },
                "soil_density": {
                    "field_name": "Soil Density",
                    "field_type": "n"
                },
                "soil_specific_heat": {
                    "field_name": "Soil Specific Heat",
                    "field_type": "n"
                },
                "average_soil_surface_temperature": {
                    "field_name": "Average Soil Surface Temperature",
                    "field_type": "n"
                },
                "average_amplitude_of_surface_temperature": {
                    "field_name": "Average Amplitude of Surface Temperature",
                    "field_type": "n"
                },
                "phase_shift_of_minimum_surface_temperature": {
                    "field_name": "Phase Shift of Minimum Surface Temperature",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "soil_thermal_conductivity",
                "soil_density",
                "soil_specific_heat",
                "average_soil_surface_temperature",
                "average_amplitude_of_surface_temperature",
                "phase_shift_of_minimum_surface_temperature"
            ],
            "alphas": {
                "fields": [
                    "name"
                ]
            },
            "numerics": {
                "fields": [
                    "soil_thermal_conductivity",
                    "soil_density",
                    "soil_specific_heat",
                    "average_soil_surface_temperature",
                    "average_amplitude_of_surface_temperature",
                    "phase_shift_of_minimum_surface_temperature"
                ]
            }
        },
        "type": "object",
        "memo": "Undisturbed ground temperature object using the Kusuda-Achenbach 1965 correlation.",
        "min_fields": 7.0
    }
}
```
