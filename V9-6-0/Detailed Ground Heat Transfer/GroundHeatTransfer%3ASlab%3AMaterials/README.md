```
{
    "GroundHeatTransfer:Slab:Materials": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "nmat_number_of_materials": {
                        "type": "number",
                        "note": "This field specifies the number of different materials that will be used in the model. Typically only a ground material and a slab material are used. (2 materials)",
                        "exclusiveMinimum": 0.0
                    },
                    "albedo_surface_albedo_no_snow": {
                        "type": "number",
                        "note": "Two fields specify the albedo value of the surface: first for no snow coverage days; second for days with snow coverage. The albedo is the solar reflectivity of the surface, and can vary from 0.05 for blacktop to 0.95 for fresh snow. Typical values for North America reported by Bahnfleth range from 0.16 to 0.4.",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.16
                    },
                    "albedo_surface_albedo_snow": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.4
                    },
                    "epslw_surface_emissivity_no_snow": {
                        "type": "number",
                        "note": "EPSLW (No Snow and Snow) specifies the long wavelength (thermal) emissivity of the ground surface. primarily important for nighttime radiation to sky. typical value .95",
                        "exclusiveMinimum": 0.0,
                        "default": 0.94
                    },
                    "epslw_surface_emissivity_snow": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "default": 0.86
                    },
                    "z0_surface_roughness_no_snow": {
                        "type": "number",
                        "note": "fields Z0 (No Snow and Snow) describe the height at which an experimentally velocity profile goes to zero. typical value= .75 cm",
                        "exclusiveMinimum": 0.0,
                        "default": 0.75,
                        "units": "cm"
                    },
                    "z0_surface_roughness_snow": {
                        "type": "number",
                        "note": "typical value= .05 cm",
                        "exclusiveMinimum": 0.0,
                        "default": 0.25,
                        "units": "cm"
                    },
                    "hin_indoor_hconv_downward_flow": {
                        "type": "number",
                        "note": "These fields specify the combined convective and radiative heat transfer coefficient between the slab top inside surface and the room air for the cases where heat is flowing downward, and upward. The program toggles between the two if the direction of the heat flux changes. Typical values can be found in the ASHRAE Handbook of Fundamentals, but should be about 6 W/(m2-K) for downward heat flow and 9 W/(m2-K) for upward heat flow. typical value= 4-10",
                        "units": "W/m2-K",
                        "exclusiveMinimum": 0.0,
                        "default": 6.13
                    },
                    "hin_indoor_hconv_upward": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "note": "typical value= 4-10",
                        "units": "W/m2-K",
                        "default": 9.26
                    }
                },
                "required": [
                    "nmat_number_of_materials"
                ]
            }
        },
        "group": "Detailed Ground Heat Transfer",
        "legacy_idd": {
            "field_info": {
                "nmat_number_of_materials": {
                    "field_name": "NMAT: Number of materials",
                    "field_type": "n"
                },
                "albedo_surface_albedo_no_snow": {
                    "field_name": "ALBEDO: Surface Albedo: No Snow",
                    "field_type": "n"
                },
                "albedo_surface_albedo_snow": {
                    "field_name": "ALBEDO: Surface Albedo: Snow",
                    "field_type": "n"
                },
                "epslw_surface_emissivity_no_snow": {
                    "field_name": "EPSLW: Surface Emissivity: No Snow",
                    "field_type": "n"
                },
                "epslw_surface_emissivity_snow": {
                    "field_name": "EPSLW: Surface Emissivity: Snow",
                    "field_type": "n"
                },
                "z0_surface_roughness_no_snow": {
                    "field_name": "Z0: Surface Roughness: No Snow",
                    "field_type": "n"
                },
                "z0_surface_roughness_snow": {
                    "field_name": "Z0: Surface Roughness: Snow",
                    "field_type": "n"
                },
                "hin_indoor_hconv_downward_flow": {
                    "field_name": "HIN: Indoor HConv: Downward Flow",
                    "field_type": "n"
                },
                "hin_indoor_hconv_upward": {
                    "field_name": "HIN: Indoor HConv: Upward",
                    "field_type": "n"
                }
            },
            "fields": [
                "nmat_number_of_materials",
                "albedo_surface_albedo_no_snow",
                "albedo_surface_albedo_snow",
                "epslw_surface_emissivity_no_snow",
                "epslw_surface_emissivity_snow",
                "z0_surface_roughness_no_snow",
                "z0_surface_roughness_snow",
                "hin_indoor_hconv_downward_flow",
                "hin_indoor_hconv_upward"
            ],
            "alphas": {
                "fields": []
            },
            "numerics": {
                "fields": [
                    "nmat_number_of_materials",
                    "albedo_surface_albedo_no_snow",
                    "albedo_surface_albedo_snow",
                    "epslw_surface_emissivity_no_snow",
                    "epslw_surface_emissivity_snow",
                    "z0_surface_roughness_no_snow",
                    "z0_surface_roughness_snow",
                    "hin_indoor_hconv_downward_flow",
                    "hin_indoor_hconv_upward"
                ]
            }
        },
        "type": "object",
        "memo": "Object gives an overall description of the slab ground heat transfer model."
    }
}
```
