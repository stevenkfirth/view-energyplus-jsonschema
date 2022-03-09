```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "albedo_surface_albedo_for_no_snow_conditions": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.16
                },
                "albedo_surface_albedo_for_snow_conditions": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.4
                },
                "epsln_surface_emissivity_no_snow": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.94
                },
                "epsln_surface_emissivity_with_snow": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.86
                },
                "veght_surface_roughness_no_snow_conditions": {
                    "type": "number",
                    "minimum": 0.0,
                    "default": 6.0,
                    "units": "cm"
                },
                "veght_surface_roughness_snow_conditions": {
                    "type": "number",
                    "minimum": 0.0,
                    "default": 0.25,
                    "units": "cm"
                },
                "pet_flag_potential_evapotranspiration_on_": {
                    "type": "string",
                    "note": "Typically, PET is False",
                    "enum": [
                        "",
                        "FALSE",
                        "TRUE"
                    ],
                    "default": "FALSE"
                }
            }
        }
    },
    "group": "Detailed Ground Heat Transfer",
    "legacy_idd": {
        "field_info": {
            "albedo_surface_albedo_for_no_snow_conditions": {
                "field_name": "ALBEDO: Surface albedo for No snow conditions",
                "field_type": "n"
            },
            "albedo_surface_albedo_for_snow_conditions": {
                "field_name": "ALBEDO: Surface albedo for snow conditions",
                "field_type": "n"
            },
            "epsln_surface_emissivity_no_snow": {
                "field_name": "EPSLN: Surface emissivity No Snow",
                "field_type": "n"
            },
            "epsln_surface_emissivity_with_snow": {
                "field_name": "EPSLN: Surface emissivity with Snow",
                "field_type": "n"
            },
            "veght_surface_roughness_no_snow_conditions": {
                "field_name": "VEGHT: Surface roughness No snow conditions",
                "field_type": "n"
            },
            "veght_surface_roughness_snow_conditions": {
                "field_name": "VEGHT: Surface roughness Snow conditions",
                "field_type": "n"
            },
            "pet_flag_potential_evapotranspiration_on_": {
                "field_name": "PET: Flag, Potential evapotranspiration on?",
                "field_type": "a"
            }
        },
        "fields": [
            "albedo_surface_albedo_for_no_snow_conditions",
            "albedo_surface_albedo_for_snow_conditions",
            "epsln_surface_emissivity_no_snow",
            "epsln_surface_emissivity_with_snow",
            "veght_surface_roughness_no_snow_conditions",
            "veght_surface_roughness_snow_conditions",
            "pet_flag_potential_evapotranspiration_on_"
        ],
        "alphas": {
            "fields": [
                "pet_flag_potential_evapotranspiration_on_"
            ]
        },
        "numerics": {
            "fields": [
                "albedo_surface_albedo_for_no_snow_conditions",
                "albedo_surface_albedo_for_snow_conditions",
                "epsln_surface_emissivity_no_snow",
                "epsln_surface_emissivity_with_snow",
                "veght_surface_roughness_no_snow_conditions",
                "veght_surface_roughness_snow_conditions"
            ]
        }
    },
    "type": "object",
    "memo": "Specifies the soil surface properties for the Basement preprocessor ground heat transfer simulation.",
    "min_fields": 7.0
}
```
