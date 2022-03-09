```
{
    "Site:GroundDomain:Slab": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "ground_domain_depth": {
                        "type": "number",
                        "default": 10.0,
                        "units": "m",
                        "exclusiveMinimum": 0.0
                    },
                    "aspect_ratio": {
                        "type": "number",
                        "default": 1.0
                    },
                    "perimeter_offset": {
                        "type": "number",
                        "default": 5.0,
                        "units": "m",
                        "exclusiveMinimum": 0.0
                    },
                    "soil_thermal_conductivity": {
                        "type": "number",
                        "default": 1.5,
                        "units": "W/m-K",
                        "exclusiveMinimum": 0.0
                    },
                    "soil_density": {
                        "type": "number",
                        "default": 2800.0,
                        "units": "kg/m3",
                        "exclusiveMinimum": 0.0
                    },
                    "soil_specific_heat": {
                        "type": "number",
                        "default": 850.0,
                        "units": "J/kg-K",
                        "exclusiveMinimum": 0.0
                    },
                    "soil_moisture_content_volume_fraction": {
                        "type": "number",
                        "units": "percent",
                        "minimum": 0.0,
                        "maximum": 100.0,
                        "default": 30.0
                    },
                    "soil_moisture_content_volume_fraction_at_saturation": {
                        "type": "number",
                        "units": "percent",
                        "minimum": 0.0,
                        "maximum": 100.0,
                        "default": 50.0
                    },
                    "undisturbed_ground_temperature_model_type": {
                        "type": "string",
                        "enum": [
                            "Site:GroundTemperature:Undisturbed:FiniteDifference",
                            "Site:GroundTemperature:Undisturbed:KusudaAchenbach",
                            "Site:GroundTemperature:Undisturbed:Xing"
                        ]
                    },
                    "undisturbed_ground_temperature_model_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UndisturbedGroundTempModels"
                        ]
                    },
                    "evapotranspiration_ground_cover_parameter": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.5,
                        "default": 0.4,
                        "note": "This specifies the ground cover effects during evapotranspiration calculations. The value roughly represents the following cases: = 0   : concrete or other solid, non-permeable ground surface material = 0.5 : short grass, much like a manicured lawn = 1   : standard reference state (12 cm grass) = 1.5 : wild growth"
                    },
                    "slab_boundary_condition_model_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "OSCMNames"
                        ]
                    },
                    "slab_location": {
                        "type": "string",
                        "enum": [
                            "InGrade",
                            "OnGrade"
                        ],
                        "note": "This field specifies whether the slab is located \"in-grade\" or \"on-grade\""
                    },
                    "slab_material_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "MaterialName"
                        ],
                        "note": "Only applicable for the in-grade case"
                    },
                    "horizontal_insulation": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No",
                        "note": "This field specifies the presence of insulation beneath the slab. Only required for in-grade case."
                    },
                    "horizontal_insulation_material_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "MaterialName"
                        ],
                        "note": "This field specifies the horizontal insulation material."
                    },
                    "horizontal_insulation_extents": {
                        "type": "string",
                        "enum": [
                            "",
                            "Full",
                            "Perimeter"
                        ],
                        "default": "Full",
                        "note": "This field specifies whether the horizontal insulation fully insulates the surface or is perimeter only insulation"
                    },
                    "perimeter_insulation_width": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "note": "This field specifies the width of the underfloor perimeter insulation"
                    },
                    "vertical_insulation": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No",
                        "note": "This field specifies the presence of vertical insulation at the slab edge."
                    },
                    "vertical_insulation_material_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "MaterialName"
                        ],
                        "note": "This field specifies the vertical insulation material."
                    },
                    "vertical_insulation_depth": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "note": "Only used when including vertical insulation This field specifies the depth of the vertical insulation"
                    },
                    "simulation_timestep": {
                        "type": "string",
                        "enum": [
                            "",
                            "Hourly",
                            "Timestep"
                        ],
                        "default": "Hourly",
                        "note": "This field specifies the ground domain simulation timestep."
                    },
                    "geometric_mesh_coefficient": {
                        "type": "number",
                        "minimum": 1.0,
                        "maximum": 2.0,
                        "default": 1.6
                    },
                    "mesh_density_parameter": {
                        "type": "number",
                        "minimum": 4.0,
                        "default": 6.0
                    }
                },
                "required": [
                    "undisturbed_ground_temperature_model_type",
                    "undisturbed_ground_temperature_model_name",
                    "slab_boundary_condition_model_name",
                    "slab_location"
                ]
            }
        },
        "group": "Location and Climate",
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
                "ground_domain_depth": {
                    "field_name": "Ground Domain Depth",
                    "field_type": "n"
                },
                "aspect_ratio": {
                    "field_name": "Aspect Ratio",
                    "field_type": "n"
                },
                "perimeter_offset": {
                    "field_name": "Perimeter Offset",
                    "field_type": "n"
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
                "soil_moisture_content_volume_fraction": {
                    "field_name": "Soil Moisture Content Volume Fraction",
                    "field_type": "n"
                },
                "soil_moisture_content_volume_fraction_at_saturation": {
                    "field_name": "Soil Moisture Content Volume Fraction at Saturation",
                    "field_type": "n"
                },
                "undisturbed_ground_temperature_model_type": {
                    "field_name": "Undisturbed Ground Temperature Model Type",
                    "field_type": "a"
                },
                "undisturbed_ground_temperature_model_name": {
                    "field_name": "Undisturbed Ground Temperature Model Name",
                    "field_type": "a"
                },
                "evapotranspiration_ground_cover_parameter": {
                    "field_name": "Evapotranspiration Ground Cover Parameter",
                    "field_type": "n"
                },
                "slab_boundary_condition_model_name": {
                    "field_name": "Slab Boundary Condition Model Name",
                    "field_type": "a"
                },
                "slab_location": {
                    "field_name": "Slab Location",
                    "field_type": "a"
                },
                "slab_material_name": {
                    "field_name": "Slab Material Name",
                    "field_type": "a"
                },
                "horizontal_insulation": {
                    "field_name": "Horizontal Insulation",
                    "field_type": "a"
                },
                "horizontal_insulation_material_name": {
                    "field_name": "Horizontal Insulation Material Name",
                    "field_type": "a"
                },
                "horizontal_insulation_extents": {
                    "field_name": "Horizontal Insulation Extents",
                    "field_type": "a"
                },
                "perimeter_insulation_width": {
                    "field_name": "Perimeter Insulation Width",
                    "field_type": "n"
                },
                "vertical_insulation": {
                    "field_name": "Vertical Insulation",
                    "field_type": "a"
                },
                "vertical_insulation_material_name": {
                    "field_name": "Vertical Insulation Material Name",
                    "field_type": "a"
                },
                "vertical_insulation_depth": {
                    "field_name": "Vertical Insulation Depth",
                    "field_type": "n"
                },
                "simulation_timestep": {
                    "field_name": "Simulation Timestep",
                    "field_type": "a"
                },
                "geometric_mesh_coefficient": {
                    "field_name": "Geometric Mesh Coefficient",
                    "field_type": "n"
                },
                "mesh_density_parameter": {
                    "field_name": "Mesh Density Parameter",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "ground_domain_depth",
                "aspect_ratio",
                "perimeter_offset",
                "soil_thermal_conductivity",
                "soil_density",
                "soil_specific_heat",
                "soil_moisture_content_volume_fraction",
                "soil_moisture_content_volume_fraction_at_saturation",
                "undisturbed_ground_temperature_model_type",
                "undisturbed_ground_temperature_model_name",
                "evapotranspiration_ground_cover_parameter",
                "slab_boundary_condition_model_name",
                "slab_location",
                "slab_material_name",
                "horizontal_insulation",
                "horizontal_insulation_material_name",
                "horizontal_insulation_extents",
                "perimeter_insulation_width",
                "vertical_insulation",
                "vertical_insulation_material_name",
                "vertical_insulation_depth",
                "simulation_timestep",
                "geometric_mesh_coefficient",
                "mesh_density_parameter"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "undisturbed_ground_temperature_model_type",
                    "undisturbed_ground_temperature_model_name",
                    "slab_boundary_condition_model_name",
                    "slab_location",
                    "slab_material_name",
                    "horizontal_insulation",
                    "horizontal_insulation_material_name",
                    "horizontal_insulation_extents",
                    "vertical_insulation",
                    "vertical_insulation_material_name",
                    "simulation_timestep"
                ]
            },
            "numerics": {
                "fields": [
                    "ground_domain_depth",
                    "aspect_ratio",
                    "perimeter_offset",
                    "soil_thermal_conductivity",
                    "soil_density",
                    "soil_specific_heat",
                    "soil_moisture_content_volume_fraction",
                    "soil_moisture_content_volume_fraction_at_saturation",
                    "evapotranspiration_ground_cover_parameter",
                    "perimeter_insulation_width",
                    "vertical_insulation_depth",
                    "geometric_mesh_coefficient",
                    "mesh_density_parameter"
                ]
            }
        },
        "type": "object",
        "memo": "Ground-coupled slab model for on-grade and in-grade cases with or without insulation."
    }
}
```
