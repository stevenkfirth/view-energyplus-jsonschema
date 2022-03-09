```
{
    "ShadingProperty:Reflectance": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "shading_surface_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AllShadingSurfNames"
                        ]
                    },
                    "diffuse_solar_reflectance_of_unglazed_part_of_shading_surface": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.2
                    },
                    "diffuse_visible_reflectance_of_unglazed_part_of_shading_surface": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.2
                    },
                    "fraction_of_shading_surface_that_is_glazed": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "glazing_construction_name": {
                        "type": "string",
                        "note": "Required if Fraction of Shading Surface That Is Glazed > 0.0"
                    }
                },
                "required": [
                    "shading_surface_name"
                ]
            }
        },
        "group": "Thermal Zones and Surfaces",
        "legacy_idd": {
            "field_info": {
                "shading_surface_name": {
                    "field_name": "Shading Surface Name",
                    "field_type": "a"
                },
                "diffuse_solar_reflectance_of_unglazed_part_of_shading_surface": {
                    "field_name": "Diffuse Solar Reflectance of Unglazed Part of Shading Surface",
                    "field_type": "n"
                },
                "diffuse_visible_reflectance_of_unglazed_part_of_shading_surface": {
                    "field_name": "Diffuse Visible Reflectance of Unglazed Part of Shading Surface",
                    "field_type": "n"
                },
                "fraction_of_shading_surface_that_is_glazed": {
                    "field_name": "Fraction of Shading Surface That Is Glazed",
                    "field_type": "n"
                },
                "glazing_construction_name": {
                    "field_name": "Glazing Construction Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "shading_surface_name",
                "diffuse_solar_reflectance_of_unglazed_part_of_shading_surface",
                "diffuse_visible_reflectance_of_unglazed_part_of_shading_surface",
                "fraction_of_shading_surface_that_is_glazed",
                "glazing_construction_name"
            ],
            "alphas": {
                "fields": [
                    "shading_surface_name",
                    "glazing_construction_name"
                ]
            },
            "numerics": {
                "fields": [
                    "diffuse_solar_reflectance_of_unglazed_part_of_shading_surface",
                    "diffuse_visible_reflectance_of_unglazed_part_of_shading_surface",
                    "fraction_of_shading_surface_that_is_glazed"
                ]
            }
        },
        "type": "object",
        "memo": "If this object is not defined for a shading surface the default values listed in following fields will be used in the solar reflection calculation.",
        "min_fields": 3.0
    }
}
```
