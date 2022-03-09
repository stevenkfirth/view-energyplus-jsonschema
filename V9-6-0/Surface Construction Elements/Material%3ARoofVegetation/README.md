```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "height_of_plants": {
                    "type": "number",
                    "note": "The ecoroof module is designed for short plants and shrubs.",
                    "exclusiveMinimum": 0.005,
                    "maximum": 1.0,
                    "units": "m",
                    "default": 0.2
                },
                "leaf_area_index": {
                    "type": "number",
                    "units": "dimensionless",
                    "note": "Entire surface is assumed covered, so decrease LAI accordingly.",
                    "exclusiveMinimum": 0.001,
                    "maximum": 5.0,
                    "default": 1.0
                },
                "leaf_reflectivity": {
                    "type": "number",
                    "units": "dimensionless",
                    "note": "Leaf reflectivity (albedo) is typically 0.18-0.25",
                    "maximum": 0.5,
                    "minimum": 0.05,
                    "default": 0.22
                },
                "leaf_emissivity": {
                    "type": "number",
                    "minimum": 0.8,
                    "maximum": 1.0,
                    "default": 0.95
                },
                "minimum_stomatal_resistance": {
                    "type": "number",
                    "units": "s/m",
                    "default": 180.0,
                    "note": "This depends upon plant type",
                    "minimum": 50.0,
                    "maximum": 300.0
                },
                "soil_layer_name": {
                    "type": "string",
                    "default": "Green Roof Soil"
                },
                "roughness": {
                    "type": "string",
                    "enum": [
                        "",
                        "MediumRough",
                        "MediumSmooth",
                        "Rough",
                        "Smooth",
                        "VeryRough",
                        "VerySmooth"
                    ],
                    "default": "MediumRough"
                },
                "thickness": {
                    "type": "number",
                    "note": "thickness of the soil layer of the EcoRoof Soil depths of 0.15m (6in) and 0.30m (12in) are common.",
                    "units": "m",
                    "default": 0.1,
                    "exclusiveMinimum": 0.05,
                    "maximum": 0.7,
                    "ip-units": "in"
                },
                "conductivity_of_dry_soil": {
                    "type": "number",
                    "units": "W/m-K",
                    "note": "Thermal conductivity of dry soil. Typical ecoroof soils range from 0.3 to 0.5",
                    "default": 0.35,
                    "minimum": 0.2,
                    "maximum": 1.5
                },
                "density_of_dry_soil": {
                    "type": "number",
                    "units": "kg/m3",
                    "note": "Density of dry soil (the code modifies this as the soil becomes moist) Typical ecoroof soils range from 400 to 1000 (dry to wet)",
                    "minimum": 300.0,
                    "maximum": 2000.0,
                    "default": 1100.0
                },
                "specific_heat_of_dry_soil": {
                    "type": "number",
                    "units": "J/kg-K",
                    "note": "Specific heat of dry soil",
                    "exclusiveMinimum": 500.0,
                    "maximum": 2000.0,
                    "default": 1200.0
                },
                "thermal_absorptance": {
                    "type": "number",
                    "note": "Soil emissivity is typically in range of 0.90 to 0.98",
                    "exclusiveMinimum": 0.8,
                    "default": 0.9,
                    "maximum": 1.0
                },
                "solar_absorptance": {
                    "type": "number",
                    "note": "Solar absorptance of dry soil (1-albedo) is typically 0.60 to 0.85 corresponding to a dry albedo of 0.15 to 0.40",
                    "default": 0.7,
                    "minimum": 0.4,
                    "maximum": 0.9
                },
                "visible_absorptance": {
                    "type": "number",
                    "exclusiveMinimum": 0.5,
                    "default": 0.75,
                    "maximum": 1.0
                },
                "saturation_volumetric_moisture_content_of_the_soil_layer": {
                    "type": "number",
                    "note": "Maximum moisture content is typically less than 0.5",
                    "exclusiveMinimum": 0.1,
                    "maximum": 0.5,
                    "default": 0.3
                },
                "residual_volumetric_moisture_content_of_the_soil_layer": {
                    "type": "number",
                    "minimum": 0.01,
                    "maximum": 0.1,
                    "default": 0.01
                },
                "initial_volumetric_moisture_content_of_the_soil_layer": {
                    "type": "number",
                    "exclusiveMinimum": 0.05,
                    "maximum": 0.5,
                    "default": 0.1
                },
                "moisture_diffusion_calculation_method": {
                    "type": "string",
                    "note": "Advanced calculation requires increased number of timesteps (recommended >20).",
                    "enum": [
                        "",
                        "Advanced",
                        "Simple"
                    ],
                    "default": "Advanced"
                }
            }
        }
    },
    "group": "Surface Construction Elements",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "MaterialName"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "height_of_plants": {
                "field_name": "Height of Plants",
                "field_type": "n"
            },
            "leaf_area_index": {
                "field_name": "Leaf Area Index",
                "field_type": "n"
            },
            "leaf_reflectivity": {
                "field_name": "Leaf Reflectivity",
                "field_type": "n"
            },
            "leaf_emissivity": {
                "field_name": "Leaf Emissivity",
                "field_type": "n"
            },
            "minimum_stomatal_resistance": {
                "field_name": "Minimum Stomatal Resistance",
                "field_type": "n"
            },
            "soil_layer_name": {
                "field_name": "Soil Layer Name",
                "field_type": "a"
            },
            "roughness": {
                "field_name": "Roughness",
                "field_type": "a"
            },
            "thickness": {
                "field_name": "Thickness",
                "field_type": "n"
            },
            "conductivity_of_dry_soil": {
                "field_name": "Conductivity of Dry Soil",
                "field_type": "n"
            },
            "density_of_dry_soil": {
                "field_name": "Density of Dry Soil",
                "field_type": "n"
            },
            "specific_heat_of_dry_soil": {
                "field_name": "Specific Heat of Dry Soil",
                "field_type": "n"
            },
            "thermal_absorptance": {
                "field_name": "Thermal Absorptance",
                "field_type": "n"
            },
            "solar_absorptance": {
                "field_name": "Solar Absorptance",
                "field_type": "n"
            },
            "visible_absorptance": {
                "field_name": "Visible Absorptance",
                "field_type": "n"
            },
            "saturation_volumetric_moisture_content_of_the_soil_layer": {
                "field_name": "Saturation Volumetric Moisture Content of the Soil Layer",
                "field_type": "n"
            },
            "residual_volumetric_moisture_content_of_the_soil_layer": {
                "field_name": "Residual Volumetric Moisture Content of the Soil Layer",
                "field_type": "n"
            },
            "initial_volumetric_moisture_content_of_the_soil_layer": {
                "field_name": "Initial Volumetric Moisture Content of the Soil Layer",
                "field_type": "n"
            },
            "moisture_diffusion_calculation_method": {
                "field_name": "Moisture Diffusion Calculation Method",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "height_of_plants",
            "leaf_area_index",
            "leaf_reflectivity",
            "leaf_emissivity",
            "minimum_stomatal_resistance",
            "soil_layer_name",
            "roughness",
            "thickness",
            "conductivity_of_dry_soil",
            "density_of_dry_soil",
            "specific_heat_of_dry_soil",
            "thermal_absorptance",
            "solar_absorptance",
            "visible_absorptance",
            "saturation_volumetric_moisture_content_of_the_soil_layer",
            "residual_volumetric_moisture_content_of_the_soil_layer",
            "initial_volumetric_moisture_content_of_the_soil_layer",
            "moisture_diffusion_calculation_method"
        ],
        "alphas": {
            "fields": [
                "name",
                "soil_layer_name",
                "roughness",
                "moisture_diffusion_calculation_method"
            ]
        },
        "numerics": {
            "fields": [
                "height_of_plants",
                "leaf_area_index",
                "leaf_reflectivity",
                "leaf_emissivity",
                "minimum_stomatal_resistance",
                "thickness",
                "conductivity_of_dry_soil",
                "density_of_dry_soil",
                "specific_heat_of_dry_soil",
                "thermal_absorptance",
                "solar_absorptance",
                "visible_absorptance",
                "saturation_volumetric_moisture_content_of_the_soil_layer",
                "residual_volumetric_moisture_content_of_the_soil_layer",
                "initial_volumetric_moisture_content_of_the_soil_layer"
            ]
        }
    },
    "type": "object",
    "memo": "EcoRoof model, plant layer plus soil layer Implemented by Portland State University (Sailor et al., January, 2007) only one material must be referenced per simulation though the same EcoRoof material could be used in multiple constructions. New moisture redistribution scheme (2010) requires higher number of timesteps per hour (minimum 12 recommended).",
    "min_fields": 19.0
}
```
