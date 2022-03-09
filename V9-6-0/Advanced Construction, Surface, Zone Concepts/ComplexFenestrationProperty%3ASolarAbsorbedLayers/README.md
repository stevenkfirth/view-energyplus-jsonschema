```
{
    "ComplexFenestrationProperty:SolarAbsorbedLayers": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "fenestration_surface": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "SubSurfNames"
                        ]
                    },
                    "construction_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ComplexFenestrationStates"
                        ]
                    },
                    "layer_1_solar_radiation_absorbed_schedule_name": {
                        "type": "string",
                        "note": "Values in schedule are expected to be in W/m2",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "layer_2_solar_radiation_absorbed_schedule_name": {
                        "type": "string",
                        "note": "Values in schedule are expected to be in W/m2",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "layer_3_solar_radiation_absorbed_schedule_name": {
                        "type": "string",
                        "note": "Values in schedule are expected to be in W/m2",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "layer_4_solar_radiation_absorbed_schedule_name": {
                        "type": "string",
                        "note": "Values in schedule are expected to be in W/m2",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "layer_5_solar_radiation_absorbed_schedule_name": {
                        "type": "string",
                        "note": "Values in schedule are expected to be in W/m2",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    }
                },
                "required": [
                    "fenestration_surface",
                    "construction_name",
                    "layer_1_solar_radiation_absorbed_schedule_name"
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
                "fenestration_surface": {
                    "field_name": "Fenestration Surface",
                    "field_type": "a"
                },
                "construction_name": {
                    "field_name": "Construction Name",
                    "field_type": "a"
                },
                "layer_1_solar_radiation_absorbed_schedule_name": {
                    "field_name": "Layer 1 Solar Radiation Absorbed Schedule Name",
                    "field_type": "a"
                },
                "layer_2_solar_radiation_absorbed_schedule_name": {
                    "field_name": "Layer 2 Solar Radiation Absorbed Schedule Name",
                    "field_type": "a"
                },
                "layer_3_solar_radiation_absorbed_schedule_name": {
                    "field_name": "Layer 3 Solar Radiation Absorbed Schedule Name",
                    "field_type": "a"
                },
                "layer_4_solar_radiation_absorbed_schedule_name": {
                    "field_name": "Layer 4 Solar Radiation Absorbed Schedule Name",
                    "field_type": "a"
                },
                "layer_5_solar_radiation_absorbed_schedule_name": {
                    "field_name": "Layer 5 Solar Radiation Absorbed Schedule Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "fenestration_surface",
                "construction_name",
                "layer_1_solar_radiation_absorbed_schedule_name",
                "layer_2_solar_radiation_absorbed_schedule_name",
                "layer_3_solar_radiation_absorbed_schedule_name",
                "layer_4_solar_radiation_absorbed_schedule_name",
                "layer_5_solar_radiation_absorbed_schedule_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "fenestration_surface",
                    "construction_name",
                    "layer_1_solar_radiation_absorbed_schedule_name",
                    "layer_2_solar_radiation_absorbed_schedule_name",
                    "layer_3_solar_radiation_absorbed_schedule_name",
                    "layer_4_solar_radiation_absorbed_schedule_name",
                    "layer_5_solar_radiation_absorbed_schedule_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "Used to provide solar radiation absorbed in fenestration layers. References surface-construction pair and if that pair is used in a simulation, then program will use value provided in schedules instead of calculating it."
    }
}
```
