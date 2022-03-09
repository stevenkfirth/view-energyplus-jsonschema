```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "boundary_conditions_model_name": {
                    "type": "string",
                    "note": "Enter the name of a SurfaceProperty:OtherSideConditionsModel object",
                    "data_type": "object_list",
                    "object_list": [
                        "OSCMNames"
                    ]
                },
                "area_fraction_of_openings": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "maximum": 1.0,
                    "units": "dimensionless"
                },
                "thermal_emissivity_of_exterior_baffle_material": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "units": "dimensionless"
                },
                "solar_absorbtivity_of_exterior_baffle": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "units": "dimensionless"
                },
                "height_scale_for_buoyancy_driven_ventilation": {
                    "type": "number",
                    "units": "m",
                    "exclusiveMinimum": 0.0
                },
                "effective_thickness_of_cavity_behind_exterior_baffle": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "units": "m",
                    "note": "if corrugated, use average depth"
                },
                "ratio_of_actual_surface_area_to_projected_surface_area": {
                    "type": "number",
                    "note": "this parameter is used to help account for corrugations in the collector",
                    "default": 1.0,
                    "minimum": 0.8,
                    "maximum": 2.0,
                    "units": "dimensionless"
                },
                "roughness_of_exterior_surface": {
                    "type": "string",
                    "enum": [
                        "MediumRough",
                        "MediumSmooth",
                        "Rough",
                        "Smooth",
                        "VeryRough",
                        "VerySmooth"
                    ]
                },
                "effectiveness_for_perforations_with_respect_to_wind": {
                    "type": "number",
                    "units": "dimensionless",
                    "default": 0.25,
                    "exclusiveMinimum": 0.0,
                    "maximum": 1.5
                },
                "discharge_coefficient_for_openings_with_respect_to_buoyancy_driven_flow": {
                    "type": "number",
                    "units": "dimensionless",
                    "default": 0.65,
                    "exclusiveMinimum": 0.0,
                    "maximum": 1.5
                },
                "surface": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "surface_name": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "AllShadingAndHTSurfNames"
                                ]
                            }
                        },
                        "type": "object",
                        "required": [
                            "surface_name"
                        ]
                    }
                }
            },
            "required": [
                "boundary_conditions_model_name",
                "roughness_of_exterior_surface"
            ]
        }
    },
    "group": "Advanced Construction, Surface, Zone Concepts",
    "name": {
        "type": "string",
        "is_required": true
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "boundary_conditions_model_name": {
                "field_name": "Boundary Conditions Model Name",
                "field_type": "a"
            },
            "area_fraction_of_openings": {
                "field_name": "Area Fraction of Openings",
                "field_type": "n"
            },
            "thermal_emissivity_of_exterior_baffle_material": {
                "field_name": "Thermal Emissivity of Exterior Baffle Material",
                "field_type": "n"
            },
            "solar_absorbtivity_of_exterior_baffle": {
                "field_name": "Solar Absorbtivity of Exterior Baffle",
                "field_type": "n"
            },
            "height_scale_for_buoyancy_driven_ventilation": {
                "field_name": "Height Scale for Buoyancy-Driven Ventilation",
                "field_type": "n"
            },
            "effective_thickness_of_cavity_behind_exterior_baffle": {
                "field_name": "Effective Thickness of Cavity Behind Exterior Baffle",
                "field_type": "n"
            },
            "ratio_of_actual_surface_area_to_projected_surface_area": {
                "field_name": "Ratio of Actual Surface Area to Projected Surface Area",
                "field_type": "n"
            },
            "roughness_of_exterior_surface": {
                "field_name": "Roughness of Exterior Surface",
                "field_type": "a"
            },
            "effectiveness_for_perforations_with_respect_to_wind": {
                "field_name": "Effectiveness for Perforations with Respect to Wind",
                "field_type": "n"
            },
            "discharge_coefficient_for_openings_with_respect_to_buoyancy_driven_flow": {
                "field_name": "Discharge Coefficient for Openings with Respect to Buoyancy Driven Flow",
                "field_type": "n"
            },
            "surface_name": {
                "field_name": "Surface Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "boundary_conditions_model_name",
            "area_fraction_of_openings",
            "thermal_emissivity_of_exterior_baffle_material",
            "solar_absorbtivity_of_exterior_baffle",
            "height_scale_for_buoyancy_driven_ventilation",
            "effective_thickness_of_cavity_behind_exterior_baffle",
            "ratio_of_actual_surface_area_to_projected_surface_area",
            "roughness_of_exterior_surface",
            "effectiveness_for_perforations_with_respect_to_wind",
            "discharge_coefficient_for_openings_with_respect_to_buoyancy_driven_flow"
        ],
        "alphas": {
            "fields": [
                "name",
                "boundary_conditions_model_name",
                "roughness_of_exterior_surface"
            ],
            "extensions": [
                "surface_name"
            ]
        },
        "numerics": {
            "fields": [
                "area_fraction_of_openings",
                "thermal_emissivity_of_exterior_baffle_material",
                "solar_absorbtivity_of_exterior_baffle",
                "height_scale_for_buoyancy_driven_ventilation",
                "effective_thickness_of_cavity_behind_exterior_baffle",
                "ratio_of_actual_surface_area_to_projected_surface_area",
                "effectiveness_for_perforations_with_respect_to_wind",
                "discharge_coefficient_for_openings_with_respect_to_buoyancy_driven_flow"
            ]
        },
        "extensibles": [
            "surface_name"
        ],
        "extension": "surface"
    },
    "type": "object",
    "memo": "Used to describe the decoupled layer, or baffle, and the characteristics of the cavity and openings for naturally ventilated exterior surfaces. This object is also used in conjunction with the OtherSideConditionsModel.",
    "extensible_size": 1.0
}
```
