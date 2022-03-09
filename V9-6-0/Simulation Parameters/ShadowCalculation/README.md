```
{
    "ShadowCalculation": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "shading_calculation_method": {
                        "type": "string",
                        "note": "Select between CPU-based polygon clipping method, the GPU-based pixel counting method, or importing from external shading data. If PixelCounting is selected and GPU hardware (or GPU emulation) is not available, a warning will be displayed and EnergyPlus will revert to PolygonClipping. If Scheduled is chosen, the External Shading Fraction Schedule Name is required in SurfaceProperty:LocalEnvironment. If Imported is chosen, the Schedule:File:Shading object is required.",
                        "enum": [
                            "",
                            "Imported",
                            "PixelCounting",
                            "PolygonClipping",
                            "Scheduled"
                        ],
                        "default": "PolygonClipping"
                    },
                    "shading_calculation_update_frequency_method": {
                        "type": "string",
                        "note": "choose calculation frequency method. note that Timestep is only needed for certain cases and can increase execution time significantly.",
                        "enum": [
                            "",
                            "Periodic",
                            "Timestep"
                        ],
                        "default": "Periodic"
                    },
                    "shading_calculation_update_frequency": {
                        "type": "number",
                        "minimum": 1.0,
                        "default": 20.0,
                        "note": "enter number of days this field is only used if the previous field is set to Periodic warning issued if >31"
                    },
                    "maximum_figures_in_shadow_overlap_calculations": {
                        "type": "number",
                        "note": "Number of allowable figures in shadow overlap in PolygonClipping calculations",
                        "minimum": 200.0,
                        "default": 15000.0
                    },
                    "polygon_clipping_algorithm": {
                        "type": "string",
                        "note": "Advanced Feature. Internal default is SutherlandHodgman Refer to InputOutput Reference and Engineering Reference for more information",
                        "enum": [
                            "",
                            "ConvexWeilerAtherton",
                            "SlaterBarskyandSutherlandHodgman",
                            "SutherlandHodgman"
                        ],
                        "default": "SutherlandHodgman"
                    },
                    "pixel_counting_resolution": {
                        "type": "number",
                        "note": "Number of pixels in both dimensions of the surface rendering",
                        "default": 512.0
                    },
                    "sky_diffuse_modeling_algorithm": {
                        "type": "string",
                        "note": "Advanced Feature. Internal default is SimpleSkyDiffuseModeling If you have shading elements that change transmittance over the year, you may wish to choose the detailed method. Refer to InputOutput Reference and Engineering Reference for more information",
                        "enum": [
                            "",
                            "DetailedSkyDiffuseModeling",
                            "SimpleSkyDiffuseModeling"
                        ],
                        "default": "SimpleSkyDiffuseModeling"
                    },
                    "output_external_shading_calculation_results": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No",
                        "note": "If Yes is chosen, the calculated external shading fraction results will be saved to an external CSV file with surface names as the column headers."
                    },
                    "disable_self_shading_within_shading_zone_groups": {
                        "type": "string",
                        "note": "If Yes, self-shading will be disabled from all exterior surfaces in a given Shading Zone Group to surfaces within the same Shading Zone Group. If both Disable Self-Shading Within Shading Zone Groups and Disable Self-Shading From Shading Zone Groups to Other Zones = Yes, then all self-shading from exterior surfaces will be disabled. If only one of these fields = Yes, then at least one Shading Zone Group must be specified, or this field will be ignored. Shading from Shading:* surfaces, overhangs, fins, and reveals will not be disabled.",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No"
                    },
                    "disable_self_shading_from_shading_zone_groups_to_other_zones": {
                        "type": "string",
                        "note": "If Yes, self-shading will be disabled from all exterior surfaces in a given Shading Zone Group to all other zones in the model. If both Disable Self-Shading Within Shading Zone Groups and Disable Self-Shading From Shading Zone Groups to Other Zones = Yes, then all self-shading from exterior surfaces will be disabled. If only one of these fields = Yes, then at least one Shading Zone Group must be specified, or this field will be ignored. Shading from Shading:* surfaces, overhangs, fins, and reveals will not be disabled.",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No"
                    },
                    "shading_zone_groups": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "shading_zone_group_zonelist_name": {
                                    "type": "string",
                                    "note": "Specifies a group of zones which are controlled by the Disable Self-Shading fields.",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "ZoneListNames"
                                    ]
                                }
                            },
                            "type": "object"
                        }
                    }
                }
            }
        },
        "group": "Simulation Parameters",
        "legacy_idd": {
            "field_info": {
                "shading_calculation_method": {
                    "field_name": "Shading Calculation Method",
                    "field_type": "a"
                },
                "shading_calculation_update_frequency_method": {
                    "field_name": "Shading Calculation Update Frequency Method",
                    "field_type": "a"
                },
                "shading_calculation_update_frequency": {
                    "field_name": "Shading Calculation Update Frequency",
                    "field_type": "n"
                },
                "maximum_figures_in_shadow_overlap_calculations": {
                    "field_name": "Maximum Figures in Shadow Overlap Calculations",
                    "field_type": "n"
                },
                "polygon_clipping_algorithm": {
                    "field_name": "Polygon Clipping Algorithm",
                    "field_type": "a"
                },
                "pixel_counting_resolution": {
                    "field_name": "Pixel Counting Resolution",
                    "field_type": "n"
                },
                "sky_diffuse_modeling_algorithm": {
                    "field_name": "Sky Diffuse Modeling Algorithm",
                    "field_type": "a"
                },
                "output_external_shading_calculation_results": {
                    "field_name": "Output External Shading Calculation Results",
                    "field_type": "a"
                },
                "disable_self_shading_within_shading_zone_groups": {
                    "field_name": "Disable Self-Shading Within Shading Zone Groups",
                    "field_type": "a"
                },
                "disable_self_shading_from_shading_zone_groups_to_other_zones": {
                    "field_name": "Disable Self-Shading From Shading Zone Groups to Other Zones",
                    "field_type": "a"
                },
                "shading_zone_group_zonelist_name": {
                    "field_name": "Shading Zone Group ZoneList Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "shading_calculation_method",
                "shading_calculation_update_frequency_method",
                "shading_calculation_update_frequency",
                "maximum_figures_in_shadow_overlap_calculations",
                "polygon_clipping_algorithm",
                "pixel_counting_resolution",
                "sky_diffuse_modeling_algorithm",
                "output_external_shading_calculation_results",
                "disable_self_shading_within_shading_zone_groups",
                "disable_self_shading_from_shading_zone_groups_to_other_zones"
            ],
            "alphas": {
                "fields": [
                    "shading_calculation_method",
                    "shading_calculation_update_frequency_method",
                    "polygon_clipping_algorithm",
                    "sky_diffuse_modeling_algorithm",
                    "output_external_shading_calculation_results",
                    "disable_self_shading_within_shading_zone_groups",
                    "disable_self_shading_from_shading_zone_groups_to_other_zones"
                ],
                "extensions": [
                    "shading_zone_group_zonelist_name"
                ]
            },
            "numerics": {
                "fields": [
                    "shading_calculation_update_frequency",
                    "maximum_figures_in_shadow_overlap_calculations",
                    "pixel_counting_resolution"
                ]
            },
            "extensibles": [
                "shading_zone_group_zonelist_name"
            ],
            "extension": "shading_zone_groups"
        },
        "type": "object",
        "maxProperties": 1,
        "memo": "This object is used to control details of the solar, shading, and daylighting models",
        "extensible_size": 1.0
    }
}
```
