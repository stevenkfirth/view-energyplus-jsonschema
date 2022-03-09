```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "waterheater_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "WaterHeaterNames"
                    ]
                },
                "design_mode": {
                    "type": "string",
                    "enum": [
                        "PeakDraw",
                        "PerFloorArea",
                        "PerPerson",
                        "PerSolarCollectorArea",
                        "PerUnit",
                        "ResidentialHUD-FHAMinimum"
                    ]
                },
                "time_storage_can_meet_peak_draw": {
                    "type": "number",
                    "units": "hr",
                    "note": "Only used for Design Mode = PeakDraw",
                    "minimum": 0.0
                },
                "time_for_tank_recovery": {
                    "type": "number",
                    "units": "hr",
                    "note": "Only used for Design Mode = PeakDraw",
                    "minimum": 0.0
                },
                "nominal_tank_volume_for_autosizing_plant_connections": {
                    "type": "number",
                    "units": "m3",
                    "ip-units": "gal",
                    "note": "Only used if Design Mode = PeakDraw and the water heater also has autosized flow rates for connections on the demand side of a plant loop"
                },
                "number_of_bedrooms": {
                    "type": "number",
                    "note": "Only used for Design Mode = ResidentialHUD-FHAMinimum",
                    "minimum": 1.0
                },
                "number_of_bathrooms": {
                    "type": "number",
                    "note": "Only used for Design Mode = ResidentialHUD-FHAMinimum",
                    "minimum": 1.0
                },
                "storage_capacity_per_person": {
                    "type": "number",
                    "units": "m3/person",
                    "ip-units": "gal/person",
                    "note": "Only used for Design Mode = PerPerson",
                    "minimum": 0.0
                },
                "recovery_capacity_per_person": {
                    "type": "number",
                    "units": "m3/hr-person",
                    "ip-units": "gal/hr-person",
                    "note": "Only used for Design Mode = PerPerson",
                    "minimum": 0.0
                },
                "storage_capacity_per_floor_area": {
                    "type": "number",
                    "units": "m3/m2",
                    "ip-units": "gal/ft2",
                    "note": "Only used for Design Mode = PerFloorArea",
                    "minimum": 0.0
                },
                "recovery_capacity_per_floor_area": {
                    "type": "number",
                    "units": "m3/hr-m2",
                    "ip-units": "gal/hr-ft2",
                    "note": "Only used for Design Mode = PerFloorArea",
                    "minimum": 0.0
                },
                "number_of_units": {
                    "type": "number",
                    "note": "Only used for Design Mode = PerUnit"
                },
                "storage_capacity_per_unit": {
                    "type": "number",
                    "units": "m3",
                    "ip-units": "gal",
                    "note": "Only used for Design Mode = PerUnit",
                    "minimum": 0.0
                },
                "recovery_capacity_perunit": {
                    "type": "number",
                    "units": "m3/hr",
                    "ip-units": "gal/hr",
                    "note": "Only used for Design Mode = PerUnit",
                    "minimum": 0.0
                },
                "storage_capacity_per_collector_area": {
                    "type": "number",
                    "units": "m3/m2",
                    "ip-units": "gal/ft2",
                    "note": "Only used for Design Mode = PerSolarCollectorArea",
                    "minimum": 0.0
                },
                "height_aspect_ratio": {
                    "type": "number",
                    "note": "only used if for WaterHeater:Stratified",
                    "minimum": 0.0
                }
            },
            "required": [
                "waterheater_name"
            ]
        }
    },
    "group": "Water Heaters and Thermal Storage",
    "legacy_idd": {
        "field_info": {
            "waterheater_name": {
                "field_name": "WaterHeater Name",
                "field_type": "a"
            },
            "design_mode": {
                "field_name": "Design Mode",
                "field_type": "a"
            },
            "time_storage_can_meet_peak_draw": {
                "field_name": "Time Storage Can Meet Peak Draw",
                "field_type": "n"
            },
            "time_for_tank_recovery": {
                "field_name": "Time for Tank Recovery",
                "field_type": "n"
            },
            "nominal_tank_volume_for_autosizing_plant_connections": {
                "field_name": "Nominal Tank Volume for Autosizing Plant Connections",
                "field_type": "n"
            },
            "number_of_bedrooms": {
                "field_name": "Number of Bedrooms",
                "field_type": "n"
            },
            "number_of_bathrooms": {
                "field_name": "Number of Bathrooms",
                "field_type": "n"
            },
            "storage_capacity_per_person": {
                "field_name": "Storage Capacity per Person",
                "field_type": "n"
            },
            "recovery_capacity_per_person": {
                "field_name": "Recovery Capacity per Person",
                "field_type": "n"
            },
            "storage_capacity_per_floor_area": {
                "field_name": "Storage Capacity per Floor Area",
                "field_type": "n"
            },
            "recovery_capacity_per_floor_area": {
                "field_name": "Recovery Capacity per Floor Area",
                "field_type": "n"
            },
            "number_of_units": {
                "field_name": "Number of Units",
                "field_type": "n"
            },
            "storage_capacity_per_unit": {
                "field_name": "Storage Capacity per Unit",
                "field_type": "n"
            },
            "recovery_capacity_perunit": {
                "field_name": "Recovery Capacity PerUnit",
                "field_type": "n"
            },
            "storage_capacity_per_collector_area": {
                "field_name": "Storage Capacity per Collector Area",
                "field_type": "n"
            },
            "height_aspect_ratio": {
                "field_name": "Height Aspect Ratio",
                "field_type": "n"
            }
        },
        "fields": [
            "waterheater_name",
            "design_mode",
            "time_storage_can_meet_peak_draw",
            "time_for_tank_recovery",
            "nominal_tank_volume_for_autosizing_plant_connections",
            "number_of_bedrooms",
            "number_of_bathrooms",
            "storage_capacity_per_person",
            "recovery_capacity_per_person",
            "storage_capacity_per_floor_area",
            "recovery_capacity_per_floor_area",
            "number_of_units",
            "storage_capacity_per_unit",
            "recovery_capacity_perunit",
            "storage_capacity_per_collector_area",
            "height_aspect_ratio"
        ],
        "alphas": {
            "fields": [
                "waterheater_name",
                "design_mode"
            ]
        },
        "numerics": {
            "fields": [
                "time_storage_can_meet_peak_draw",
                "time_for_tank_recovery",
                "nominal_tank_volume_for_autosizing_plant_connections",
                "number_of_bedrooms",
                "number_of_bathrooms",
                "storage_capacity_per_person",
                "recovery_capacity_per_person",
                "storage_capacity_per_floor_area",
                "recovery_capacity_per_floor_area",
                "number_of_units",
                "storage_capacity_per_unit",
                "recovery_capacity_perunit",
                "storage_capacity_per_collector_area",
                "height_aspect_ratio"
            ]
        }
    },
    "type": "object",
    "memo": "This input object is used with WaterHeater:Mixed or with WaterHeater:Stratified to autosize tank volume and heater capacity This object is not needed if water heaters are not autosized.",
    "min_fields": 4.0
}
```
