```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "nmat_number_of_materials_in_this_domain": {
                    "type": "number",
                    "maximum": 6.0
                },
                "density_for_foundation_wall": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 2243.0,
                    "units": "kg/m3"
                },
                "density_for_floor_slab": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 2243.0,
                    "units": "kg/m3"
                },
                "density_for_ceiling": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 311.0,
                    "units": "kg/m3"
                },
                "density_for_soil": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 1500.0,
                    "units": "kg/m3"
                },
                "density_for_gravel": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 2000.0,
                    "units": "kg/m3"
                },
                "density_for_wood": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 449.0,
                    "units": "kg/m3"
                },
                "specific_heat_for_foundation_wall": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 880.0,
                    "units": "J/kg-K"
                },
                "specific_heat_for_floor_slab": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 880.0,
                    "units": "J/kg-K"
                },
                "specific_heat_for_ceiling": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 1530.0,
                    "units": "J/kg-K"
                },
                "specific_heat_for_soil": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 840.0,
                    "units": "J/kg-K"
                },
                "specific_heat_for_gravel": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 720.0,
                    "units": "J/kg-K"
                },
                "specific_heat_for_wood": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 1530.0,
                    "units": "J/kg-K"
                },
                "thermal_conductivity_for_foundation_wall": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 1.4,
                    "units": "W/m-K"
                },
                "thermal_conductivity_for_floor_slab": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 1.4,
                    "units": "W/m-K"
                },
                "thermal_conductivity_for_ceiling": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 0.09,
                    "units": "W/m-K"
                },
                "thermal_conductivity_for_soil": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 1.1,
                    "units": "W/m-K"
                },
                "thermal_conductivity_for_gravel": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 1.9,
                    "units": "W/m-K"
                },
                "thermal_conductivity_for_wood": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 0.12,
                    "units": "W/m-K"
                }
            },
            "required": [
                "nmat_number_of_materials_in_this_domain"
            ]
        }
    },
    "group": "Detailed Ground Heat Transfer",
    "legacy_idd": {
        "field_info": {
            "nmat_number_of_materials_in_this_domain": {
                "field_name": "NMAT: Number of materials in this domain",
                "field_type": "n"
            },
            "density_for_foundation_wall": {
                "field_name": "Density for Foundation Wall",
                "field_type": "n"
            },
            "density_for_floor_slab": {
                "field_name": "density for Floor Slab",
                "field_type": "n"
            },
            "density_for_ceiling": {
                "field_name": "density for Ceiling",
                "field_type": "n"
            },
            "density_for_soil": {
                "field_name": "density for Soil",
                "field_type": "n"
            },
            "density_for_gravel": {
                "field_name": "density for Gravel",
                "field_type": "n"
            },
            "density_for_wood": {
                "field_name": "density for Wood",
                "field_type": "n"
            },
            "specific_heat_for_foundation_wall": {
                "field_name": "Specific heat for foundation wall",
                "field_type": "n"
            },
            "specific_heat_for_floor_slab": {
                "field_name": "Specific heat for floor slab",
                "field_type": "n"
            },
            "specific_heat_for_ceiling": {
                "field_name": "Specific heat for ceiling",
                "field_type": "n"
            },
            "specific_heat_for_soil": {
                "field_name": "Specific heat for soil",
                "field_type": "n"
            },
            "specific_heat_for_gravel": {
                "field_name": "Specific heat for gravel",
                "field_type": "n"
            },
            "specific_heat_for_wood": {
                "field_name": "Specific heat for wood",
                "field_type": "n"
            },
            "thermal_conductivity_for_foundation_wall": {
                "field_name": "Thermal conductivity for foundation wall",
                "field_type": "n"
            },
            "thermal_conductivity_for_floor_slab": {
                "field_name": "Thermal conductivity for floor slab",
                "field_type": "n"
            },
            "thermal_conductivity_for_ceiling": {
                "field_name": "Thermal conductivity for ceiling",
                "field_type": "n"
            },
            "thermal_conductivity_for_soil": {
                "field_name": "thermal conductivity for soil",
                "field_type": "n"
            },
            "thermal_conductivity_for_gravel": {
                "field_name": "thermal conductivity for gravel",
                "field_type": "n"
            },
            "thermal_conductivity_for_wood": {
                "field_name": "thermal conductivity for wood",
                "field_type": "n"
            }
        },
        "fields": [
            "nmat_number_of_materials_in_this_domain",
            "density_for_foundation_wall",
            "density_for_floor_slab",
            "density_for_ceiling",
            "density_for_soil",
            "density_for_gravel",
            "density_for_wood",
            "specific_heat_for_foundation_wall",
            "specific_heat_for_floor_slab",
            "specific_heat_for_ceiling",
            "specific_heat_for_soil",
            "specific_heat_for_gravel",
            "specific_heat_for_wood",
            "thermal_conductivity_for_foundation_wall",
            "thermal_conductivity_for_floor_slab",
            "thermal_conductivity_for_ceiling",
            "thermal_conductivity_for_soil",
            "thermal_conductivity_for_gravel",
            "thermal_conductivity_for_wood"
        ],
        "alphas": {
            "fields": []
        },
        "numerics": {
            "fields": [
                "nmat_number_of_materials_in_this_domain",
                "density_for_foundation_wall",
                "density_for_floor_slab",
                "density_for_ceiling",
                "density_for_soil",
                "density_for_gravel",
                "density_for_wood",
                "specific_heat_for_foundation_wall",
                "specific_heat_for_floor_slab",
                "specific_heat_for_ceiling",
                "specific_heat_for_soil",
                "specific_heat_for_gravel",
                "specific_heat_for_wood",
                "thermal_conductivity_for_foundation_wall",
                "thermal_conductivity_for_floor_slab",
                "thermal_conductivity_for_ceiling",
                "thermal_conductivity_for_soil",
                "thermal_conductivity_for_gravel",
                "thermal_conductivity_for_wood"
            ]
        }
    },
    "type": "object",
    "memo": "Specifies the material properties for the Basement preprocessor ground heat transfer simulation. Only the Foundation Wall, Floor Slab, Soil, and Gravel properties are currently used."
}
```
