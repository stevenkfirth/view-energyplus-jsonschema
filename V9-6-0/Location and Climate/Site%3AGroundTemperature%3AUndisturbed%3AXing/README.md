```
{
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
                "average_soil_surface_tempeature": {
                    "type": "number",
                    "units": "C"
                },
                "soil_surface_temperature_amplitude_1": {
                    "type": "number",
                    "units": "deltaC"
                },
                "soil_surface_temperature_amplitude_2": {
                    "type": "number",
                    "units": "deltaC"
                },
                "phase_shift_of_temperature_amplitude_1": {
                    "type": "number",
                    "units": "days",
                    "exclusiveMaximum": 365.0
                },
                "phase_shift_of_temperature_amplitude_2": {
                    "type": "number",
                    "units": "days",
                    "exclusiveMaximum": 365.0
                }
            },
            "required": [
                "soil_thermal_conductivity",
                "soil_density",
                "soil_specific_heat",
                "average_soil_surface_tempeature",
                "soil_surface_temperature_amplitude_1",
                "soil_surface_temperature_amplitude_2",
                "phase_shift_of_temperature_amplitude_1",
                "phase_shift_of_temperature_amplitude_2"
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
            "average_soil_surface_tempeature": {
                "field_name": "Average Soil Surface Tempeature",
                "field_type": "n"
            },
            "soil_surface_temperature_amplitude_1": {
                "field_name": "Soil Surface Temperature Amplitude 1",
                "field_type": "n"
            },
            "soil_surface_temperature_amplitude_2": {
                "field_name": "Soil Surface Temperature Amplitude 2",
                "field_type": "n"
            },
            "phase_shift_of_temperature_amplitude_1": {
                "field_name": "Phase Shift of Temperature Amplitude 1",
                "field_type": "n"
            },
            "phase_shift_of_temperature_amplitude_2": {
                "field_name": "Phase Shift of Temperature Amplitude 2",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "soil_thermal_conductivity",
            "soil_density",
            "soil_specific_heat",
            "average_soil_surface_tempeature",
            "soil_surface_temperature_amplitude_1",
            "soil_surface_temperature_amplitude_2",
            "phase_shift_of_temperature_amplitude_1",
            "phase_shift_of_temperature_amplitude_2"
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
                "average_soil_surface_tempeature",
                "soil_surface_temperature_amplitude_1",
                "soil_surface_temperature_amplitude_2",
                "phase_shift_of_temperature_amplitude_1",
                "phase_shift_of_temperature_amplitude_2"
            ]
        }
    },
    "type": "object",
    "memo": "Undisturbed ground temperature object using the Xing 2014 2 harmonic parameter model.",
    "min_fields": 9.0
}
```
