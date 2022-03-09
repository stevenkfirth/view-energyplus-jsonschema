```
{
    "SolarCollectorPerformance:IntegralCollectorStorage": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "ics_collector_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "RectangularTank"
                        ],
                        "default": "RectangularTank",
                        "note": "Currently only RectangularTank ICS collector type is available."
                    },
                    "gross_area": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "m2"
                    },
                    "collector_water_volume": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "m3",
                        "ip-units": "gal"
                    },
                    "bottom_heat_loss_conductance": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "default": 0.4,
                        "units": "W/m2-K",
                        "note": "Heat loss conductance of the collector bottom insulation"
                    },
                    "side_heat_loss_conductance": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "default": 0.6,
                        "units": "W/m2-K",
                        "note": "heat loss conductance of the collector side insulation"
                    },
                    "aspect_ratio": {
                        "type": "number",
                        "exclusiveMinimum": 0.5,
                        "exclusiveMaximum": 1.0,
                        "default": 0.8,
                        "units": "m",
                        "note": "This value is ratio of the width (short side) to length (long side of) of the collector. Used to calculate the perimeter of the collector"
                    },
                    "collector_side_height": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "exclusiveMaximum": 0.3,
                        "default": 0.2,
                        "units": "m",
                        "note": "This value is used to estimate collector side area for the heat loss calculation through the collector side"
                    },
                    "thermal_mass_of_absorber_plate": {
                        "type": "number",
                        "minimum": 0.0,
                        "default": 0.0,
                        "units": "J/m2-K",
                        "note": "Calculated from the specific heat, density and thickness of the absorber plate."
                    },
                    "number_of_covers": {
                        "type": "number",
                        "minimum": 1.0,
                        "maximum": 2.0,
                        "default": 2.0,
                        "note": "Number of transparent covers. Common practice is to use low-iron glass as the outer cover and very thin transparent sheet such as Teflon as the inner cover."
                    },
                    "cover_spacing": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "maximum": 0.2,
                        "default": 0.05,
                        "units": "m",
                        "note": "The gap between the transparent covers and between the inner cover and the absorber plate"
                    },
                    "refractive_index_of_outer_cover": {
                        "type": "number",
                        "minimum": 1.0,
                        "maximum": 2.0,
                        "default": 1.526,
                        "units": "dimensionless",
                        "note": "Refractive index of outer cover. Typically low-iron glass is used as the outer cover material, and used as the default outer cover with a value of 1.526."
                    },
                    "extinction_coefficient_times_thickness_of_outer_cover": {
                        "type": "number",
                        "minimum": 0.0,
                        "default": 0.045,
                        "units": "dimensionless",
                        "note": "Clear glass has extinction coefficient of about 15 [1/m] and with thickness of 3.0mm, the product of the extinction coefficient and thickness becomes 0.045 (=15 * 0.003)"
                    },
                    "emissivity_of_outer_cover": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "exclusiveMaximum": 1.0,
                        "default": 0.88,
                        "units": "dimensionless",
                        "note": "Thermal emissivity of the outer cover, commonly glass is used as the out collector cover material."
                    },
                    "refractive_index_of_inner_cover": {
                        "type": "number",
                        "minimum": 1.0,
                        "maximum": 2.0,
                        "default": 1.37,
                        "units": "dimensionless",
                        "note": "Typical material is very thin sheet of Teflon (PTFE). The default value is refractive index of Teflon."
                    },
                    "extinction_coefficient_times_thickness_of_the_inner_cover": {
                        "type": "number",
                        "minimum": 0.0,
                        "default": 0.008,
                        "units": "dimensionless",
                        "note": "Default inner cover is very thin sheet of Teflon with extinction coefficient of approximately 40.0 and a thickness 0.2mm yields a default value of 0.008."
                    },
                    "emissivity_of_inner_cover": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "exclusiveMaximum": 1.0,
                        "default": 0.88,
                        "units": "dimensionless",
                        "note": "Thermal emissivity of the inner cover material"
                    },
                    "absorptance_of_absorber_plate": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "exclusiveMaximum": 1.0,
                        "default": 0.96,
                        "units": "dimensionless",
                        "note": "The absorber plate solar absorptance. Copper is assumed as the default absorber plate."
                    },
                    "emissivity_of_absorber_plate": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "exclusiveMaximum": 1.0,
                        "default": 0.3,
                        "units": "dimensionless",
                        "note": "Thermal emissivity of the absorber plate"
                    }
                }
            }
        },
        "group": "Solar Collectors",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "CollectorStoragePerformance"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "ics_collector_type": {
                    "field_name": "ICS Collector Type",
                    "field_type": "a"
                },
                "gross_area": {
                    "field_name": "Gross Area",
                    "field_type": "n"
                },
                "collector_water_volume": {
                    "field_name": "Collector Water Volume",
                    "field_type": "n"
                },
                "bottom_heat_loss_conductance": {
                    "field_name": "Bottom Heat Loss Conductance",
                    "field_type": "n"
                },
                "side_heat_loss_conductance": {
                    "field_name": "Side Heat Loss Conductance",
                    "field_type": "n"
                },
                "aspect_ratio": {
                    "field_name": "Aspect Ratio",
                    "field_type": "n"
                },
                "collector_side_height": {
                    "field_name": "Collector Side Height",
                    "field_type": "n"
                },
                "thermal_mass_of_absorber_plate": {
                    "field_name": "Thermal Mass of Absorber Plate",
                    "field_type": "n"
                },
                "number_of_covers": {
                    "field_name": "Number of Covers",
                    "field_type": "n"
                },
                "cover_spacing": {
                    "field_name": "Cover Spacing",
                    "field_type": "n"
                },
                "refractive_index_of_outer_cover": {
                    "field_name": "Refractive Index of Outer Cover",
                    "field_type": "n"
                },
                "extinction_coefficient_times_thickness_of_outer_cover": {
                    "field_name": "Extinction Coefficient Times Thickness of Outer Cover",
                    "field_type": "n"
                },
                "emissivity_of_outer_cover": {
                    "field_name": "Emissivity of Outer Cover",
                    "field_type": "n"
                },
                "refractive_index_of_inner_cover": {
                    "field_name": "Refractive Index of Inner Cover",
                    "field_type": "n"
                },
                "extinction_coefficient_times_thickness_of_the_inner_cover": {
                    "field_name": "Extinction Coefficient Times Thickness of the inner Cover",
                    "field_type": "n"
                },
                "emissivity_of_inner_cover": {
                    "field_name": "Emissivity of Inner Cover",
                    "field_type": "n"
                },
                "absorptance_of_absorber_plate": {
                    "field_name": "Absorptance of Absorber Plate",
                    "field_type": "n"
                },
                "emissivity_of_absorber_plate": {
                    "field_name": "Emissivity of Absorber Plate",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "ics_collector_type",
                "gross_area",
                "collector_water_volume",
                "bottom_heat_loss_conductance",
                "side_heat_loss_conductance",
                "aspect_ratio",
                "collector_side_height",
                "thermal_mass_of_absorber_plate",
                "number_of_covers",
                "cover_spacing",
                "refractive_index_of_outer_cover",
                "extinction_coefficient_times_thickness_of_outer_cover",
                "emissivity_of_outer_cover",
                "refractive_index_of_inner_cover",
                "extinction_coefficient_times_thickness_of_the_inner_cover",
                "emissivity_of_inner_cover",
                "absorptance_of_absorber_plate",
                "emissivity_of_absorber_plate"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "ics_collector_type"
                ]
            },
            "numerics": {
                "fields": [
                    "gross_area",
                    "collector_water_volume",
                    "bottom_heat_loss_conductance",
                    "side_heat_loss_conductance",
                    "aspect_ratio",
                    "collector_side_height",
                    "thermal_mass_of_absorber_plate",
                    "number_of_covers",
                    "cover_spacing",
                    "refractive_index_of_outer_cover",
                    "extinction_coefficient_times_thickness_of_outer_cover",
                    "emissivity_of_outer_cover",
                    "refractive_index_of_inner_cover",
                    "extinction_coefficient_times_thickness_of_the_inner_cover",
                    "emissivity_of_inner_cover",
                    "absorptance_of_absorber_plate",
                    "emissivity_of_absorber_plate"
                ]
            }
        },
        "type": "object",
        "memo": "Thermal and optical performance parameters for a single glazed solar collector with integral storage unit.",
        "min_fields": 19.0
    }
}
```
