```
{
    "ZoneHVAC:Dehumidifier:DX": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "availability_schedule_name": {
                        "type": "string",
                        "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available. Schedule values of 0 denote the unit is off. Schedule values >0.0 (usually 1.0) indicate that the dehumidifier is available to operate.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "air_inlet_node_name": {
                        "type": "string",
                        "note": "Air inlet node for the dehumidifier must be a zone air exhaust node."
                    },
                    "air_outlet_node_name": {
                        "type": "string",
                        "note": "Air outlet node for the dehumidifier must be a zone air inlet node."
                    },
                    "rated_water_removal": {
                        "type": "number",
                        "units": "L/day",
                        "exclusiveMinimum": 0.0,
                        "note": "Rating point: air entering dehumidifier at 26.7 C (80 F) dry-bulb and 60% relative humidity."
                    },
                    "rated_energy_factor": {
                        "type": "number",
                        "units": "L/kWh",
                        "exclusiveMinimum": 0.0,
                        "note": "Rating point: air entering dehumidifier at 26.7 C (80 F) dry-bulb and 60% relative humidity."
                    },
                    "rated_air_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "exclusiveMinimum": 0.0
                    },
                    "water_removal_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Name of a curve that describes the water removal rate (normalized to rated conditions) as a function of the dry-bulb temperature and relative humidity of the air entering the dehumidifier. Curve output = (actual water removal/rated water removal) = a + b*T + c*T**2 + d*RH + e*RH**2 + f*T*RH T = inlet air dry-bulb temperature (C) RH = inlet air RH (%)"
                    },
                    "energy_factor_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Name of a curve that describes the energy factor (normalized to rated conditions) as a function of the dry-bulb temperature and relative humidity of the air entering the dehumidifier. Curve output = (actual energy factor/rated energy factor) = a + b*T + c*T**2 + d*RH + e*RH**2 + f*T*RH T = inlet air dry-bulb temperature (C) RH = inlet air RH (%)"
                    },
                    "part_load_fraction_correlation_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Name of a curve that describes the part load fraction (PLF) of the system as a function of the part load ratio. Used to calculate dehumidifier run time fraction and electric power. quadratic curve = a + b*PLR + c*PLR**2 cubic curve = a + b*PLR + c*PLR**2 + d*PLR**3 PLR = part load ratio (dehumidification load/steady state water removal capacity)"
                    },
                    "minimum_dry_bulb_temperature_for_dehumidifier_operation": {
                        "type": "number",
                        "units": "C",
                        "default": 10.0,
                        "note": "Dehumidifier shut off if inlet air (zone) temperature is below this value. This value must be less than the Maximum Dry-Bulb Temperature for Dehumidifier Operation."
                    },
                    "maximum_dry_bulb_temperature_for_dehumidifier_operation": {
                        "type": "number",
                        "units": "C",
                        "default": 35.0,
                        "note": "Dehumidifier shut off if inlet air (zone) temperature is above this value. This value must be greater than the Minimum Dry-Bulb Temperature for Dehumidifier Operation."
                    },
                    "off_cycle_parasitic_electric_load": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0,
                        "default": 0.0,
                        "note": "Parasitic electric power consumed when the dehumidifier is available to operate, but does not operate (i.e., no high humidity load to be met). Off cycle parasitic power is 0 when the availability schedule is 0. This electric load is considered as a heat gain to the zone air."
                    },
                    "condensate_collection_water_storage_tank_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "WaterStorageTankNames"
                        ],
                        "note": "Name of storage tank used to collect water removed by the dehumidifier."
                    }
                },
                "required": [
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "rated_water_removal",
                    "rated_energy_factor",
                    "rated_air_flow_rate",
                    "water_removal_curve_name",
                    "energy_factor_curve_name",
                    "part_load_fraction_correlation_curve_name"
                ]
            }
        },
        "group": "Zone HVAC Forced Air Units",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "ZoneEquipmentNames"
            ],
            "note": "Unique name for this direct expansion (DX) zone dehumidifier object."
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "availability_schedule_name": {
                    "field_name": "Availability Schedule Name",
                    "field_type": "a"
                },
                "air_inlet_node_name": {
                    "field_name": "Air Inlet Node Name",
                    "field_type": "a"
                },
                "air_outlet_node_name": {
                    "field_name": "Air Outlet Node Name",
                    "field_type": "a"
                },
                "rated_water_removal": {
                    "field_name": "Rated Water Removal",
                    "field_type": "n"
                },
                "rated_energy_factor": {
                    "field_name": "Rated Energy Factor",
                    "field_type": "n"
                },
                "rated_air_flow_rate": {
                    "field_name": "Rated Air Flow Rate",
                    "field_type": "n"
                },
                "water_removal_curve_name": {
                    "field_name": "Water Removal Curve Name",
                    "field_type": "a"
                },
                "energy_factor_curve_name": {
                    "field_name": "Energy Factor Curve Name",
                    "field_type": "a"
                },
                "part_load_fraction_correlation_curve_name": {
                    "field_name": "Part Load Fraction Correlation Curve Name",
                    "field_type": "a"
                },
                "minimum_dry_bulb_temperature_for_dehumidifier_operation": {
                    "field_name": "Minimum Dry-Bulb Temperature for Dehumidifier Operation",
                    "field_type": "n"
                },
                "maximum_dry_bulb_temperature_for_dehumidifier_operation": {
                    "field_name": "Maximum Dry-Bulb Temperature for Dehumidifier Operation",
                    "field_type": "n"
                },
                "off_cycle_parasitic_electric_load": {
                    "field_name": "Off-Cycle Parasitic Electric Load",
                    "field_type": "n"
                },
                "condensate_collection_water_storage_tank_name": {
                    "field_name": "Condensate Collection Water Storage Tank Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "rated_water_removal",
                "rated_energy_factor",
                "rated_air_flow_rate",
                "water_removal_curve_name",
                "energy_factor_curve_name",
                "part_load_fraction_correlation_curve_name",
                "minimum_dry_bulb_temperature_for_dehumidifier_operation",
                "maximum_dry_bulb_temperature_for_dehumidifier_operation",
                "off_cycle_parasitic_electric_load",
                "condensate_collection_water_storage_tank_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "water_removal_curve_name",
                    "energy_factor_curve_name",
                    "part_load_fraction_correlation_curve_name",
                    "condensate_collection_water_storage_tank_name"
                ]
            },
            "numerics": {
                "fields": [
                    "rated_water_removal",
                    "rated_energy_factor",
                    "rated_air_flow_rate",
                    "minimum_dry_bulb_temperature_for_dehumidifier_operation",
                    "maximum_dry_bulb_temperature_for_dehumidifier_operation",
                    "off_cycle_parasitic_electric_load"
                ]
            }
        },
        "type": "object",
        "memo": "This object calculates the performance of zone (room) air dehumidifiers. Meant to model conventional direct expansion (DX) cooling-based room air dehumidifiers (reject 100% of condenser heat to the zone air), but this object might be able to be used to model other room air dehumidifier types.",
        "min_fields": 13.0
    }
}
```
