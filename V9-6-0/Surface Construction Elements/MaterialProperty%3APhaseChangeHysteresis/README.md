```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "latent_heat_during_the_entire_phase_change_process": {
                    "type": "number",
                    "note": "The total latent heat absorbed or rejected during the transition from solid to liquid, or back",
                    "units": "J/kg",
                    "exclusiveMinimum": 0.0
                },
                "liquid_state_thermal_conductivity": {
                    "type": "number",
                    "note": "The thermal conductivity used by this material when the material is fully liquid",
                    "units": "W/m-K",
                    "exclusiveMinimum": 0.0
                },
                "liquid_state_density": {
                    "type": "number",
                    "note": "The density used by this material when the material is fully liquid",
                    "units": "kg/m3",
                    "exclusiveMinimum": 0.0
                },
                "liquid_state_specific_heat": {
                    "type": "number",
                    "note": "The constant specific heat used for the fully melted (liquid) state",
                    "units": "J/kg-K",
                    "exclusiveMinimum": 0.0
                },
                "high_temperature_difference_of_melting_curve": {
                    "type": "number",
                    "note": "The total melting range of the material is the sum of low and high temperature difference of melting curve.",
                    "units": "deltaC",
                    "exclusiveMinimum": 0.0
                },
                "peak_melting_temperature": {
                    "type": "number",
                    "note": "The temperature at which the melting curve peaks",
                    "units": "C",
                    "exclusiveMinimum": 0.0
                },
                "low_temperature_difference_of_melting_curve": {
                    "type": "number",
                    "note": "The total melting range of the material is the sum of low and high temperature difference of melting curve.",
                    "units": "deltaC",
                    "exclusiveMinimum": 0.0
                },
                "solid_state_thermal_conductivity": {
                    "type": "number",
                    "note": "The thermal conductivity used by this material when the material is fully solid",
                    "units": "W/m-K",
                    "exclusiveMinimum": 0.0
                },
                "solid_state_density": {
                    "type": "number",
                    "note": "The density used by this material when the material is fully solid",
                    "units": "kg/m3",
                    "exclusiveMinimum": 0.0
                },
                "solid_state_specific_heat": {
                    "type": "number",
                    "note": "The constant specific heat used for the fully frozen (crystallized) state",
                    "units": "J/kg-K",
                    "exclusiveMinimum": 0.0
                },
                "high_temperature_difference_of_freezing_curve": {
                    "type": "number",
                    "note": "The total freezing range of the material is the sum of low and high temperature difference of freezing curve.",
                    "units": "deltaC",
                    "exclusiveMinimum": 0.0
                },
                "peak_freezing_temperature": {
                    "type": "number",
                    "note": "The temperature at which the freezing curve peaks",
                    "units": "C",
                    "exclusiveMinimum": 0.0
                },
                "low_temperature_difference_of_freezing_curve": {
                    "type": "number",
                    "note": "The total freezing range of the material is the sum of low and high temperature difference of freezing curve.",
                    "units": "deltaC",
                    "exclusiveMinimum": 0.0
                }
            },
            "required": [
                "latent_heat_during_the_entire_phase_change_process",
                "liquid_state_thermal_conductivity",
                "liquid_state_density",
                "liquid_state_specific_heat",
                "high_temperature_difference_of_melting_curve",
                "peak_melting_temperature",
                "low_temperature_difference_of_melting_curve",
                "solid_state_thermal_conductivity",
                "solid_state_density",
                "solid_state_specific_heat",
                "high_temperature_difference_of_freezing_curve",
                "peak_freezing_temperature",
                "low_temperature_difference_of_freezing_curve"
            ]
        }
    },
    "group": "Surface Construction Elements",
    "name": {
        "type": "string",
        "is_required": true,
        "data_type": "object_list",
        "object_list": [
            "MaterialName"
        ],
        "note": "Regular Material Name to which the additional properties will be added. this the material name for the basic material properties."
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "latent_heat_during_the_entire_phase_change_process": {
                "field_name": "Latent Heat during the Entire Phase Change Process",
                "field_type": "n"
            },
            "liquid_state_thermal_conductivity": {
                "field_name": "Liquid State Thermal Conductivity",
                "field_type": "n"
            },
            "liquid_state_density": {
                "field_name": "Liquid State Density",
                "field_type": "n"
            },
            "liquid_state_specific_heat": {
                "field_name": "Liquid State Specific Heat",
                "field_type": "n"
            },
            "high_temperature_difference_of_melting_curve": {
                "field_name": "High Temperature Difference of Melting Curve",
                "field_type": "n"
            },
            "peak_melting_temperature": {
                "field_name": "Peak Melting Temperature",
                "field_type": "n"
            },
            "low_temperature_difference_of_melting_curve": {
                "field_name": "Low Temperature Difference of Melting Curve",
                "field_type": "n"
            },
            "solid_state_thermal_conductivity": {
                "field_name": "Solid State Thermal Conductivity",
                "field_type": "n"
            },
            "solid_state_density": {
                "field_name": "Solid State Density",
                "field_type": "n"
            },
            "solid_state_specific_heat": {
                "field_name": "Solid State Specific Heat",
                "field_type": "n"
            },
            "high_temperature_difference_of_freezing_curve": {
                "field_name": "High Temperature Difference of Freezing Curve",
                "field_type": "n"
            },
            "peak_freezing_temperature": {
                "field_name": "Peak Freezing Temperature",
                "field_type": "n"
            },
            "low_temperature_difference_of_freezing_curve": {
                "field_name": "Low Temperature Difference of Freezing Curve",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "latent_heat_during_the_entire_phase_change_process",
            "liquid_state_thermal_conductivity",
            "liquid_state_density",
            "liquid_state_specific_heat",
            "high_temperature_difference_of_melting_curve",
            "peak_melting_temperature",
            "low_temperature_difference_of_melting_curve",
            "solid_state_thermal_conductivity",
            "solid_state_density",
            "solid_state_specific_heat",
            "high_temperature_difference_of_freezing_curve",
            "peak_freezing_temperature",
            "low_temperature_difference_of_freezing_curve"
        ],
        "alphas": {
            "fields": [
                "name"
            ]
        },
        "numerics": {
            "fields": [
                "latent_heat_during_the_entire_phase_change_process",
                "liquid_state_thermal_conductivity",
                "liquid_state_density",
                "liquid_state_specific_heat",
                "high_temperature_difference_of_melting_curve",
                "peak_melting_temperature",
                "low_temperature_difference_of_melting_curve",
                "solid_state_thermal_conductivity",
                "solid_state_density",
                "solid_state_specific_heat",
                "high_temperature_difference_of_freezing_curve",
                "peak_freezing_temperature",
                "low_temperature_difference_of_freezing_curve"
            ]
        }
    },
    "type": "object",
    "memo": "Additional properties for temperature dependent thermal conductivity and enthalpy for Phase Change Materials (PCM) with separate melting and freezing curves. HeatBalanceAlgorithm = CondFD (ConductionFiniteDifference) solution algorithm only. Constructions with this should use the detailed CondFD process. Has no effect with other HeatBalanceAlgorithm solution algorithms."
}
```
