```
{
    "HeatExchanger:AirToAir:SensibleAndLatent": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "availability_schedule_name": {
                        "type": "string",
                        "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "nominal_supply_air_flow_rate": {
                        "units": "m3/s",
                        "anyOf": [
                            {
                                "type": "number",
                                "exclusiveMinimum": 0.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "sensible_effectiveness_at_100_heating_air_flow": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "latent_effectiveness_at_100_heating_air_flow": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "sensible_effectiveness_at_75_heating_air_flow": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "latent_effectiveness_at_75_heating_air_flow": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "sensible_effectiveness_at_100_cooling_air_flow": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "latent_effectiveness_at_100_cooling_air_flow": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "sensible_effectiveness_at_75_cooling_air_flow": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "latent_effectiveness_at_75_cooling_air_flow": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "supply_air_inlet_node_name": {
                        "type": "string"
                    },
                    "supply_air_outlet_node_name": {
                        "type": "string"
                    },
                    "exhaust_air_inlet_node_name": {
                        "type": "string"
                    },
                    "exhaust_air_outlet_node_name": {
                        "type": "string"
                    },
                    "nominal_electric_power": {
                        "type": "number",
                        "units": "W",
                        "ip-units": "W",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "supply_air_outlet_temperature_control": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No"
                    },
                    "heat_exchanger_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Plate",
                            "Rotary"
                        ],
                        "default": "Plate"
                    },
                    "frost_control_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "ExhaustAirRecirculation",
                            "ExhaustOnly",
                            "MinimumExhaustTemperature",
                            "None"
                        ],
                        "default": "None"
                    },
                    "threshold_temperature": {
                        "type": "number",
                        "units": "C",
                        "default": 1.7,
                        "note": "Supply (outdoor) air inlet temp threshold for exhaust air recirculation and exhaust only frost control types. Exhaust air outlet threshold Temperature for minimum exhaust temperature frost control type."
                    },
                    "initial_defrost_time_fraction": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.083,
                        "note": "Fraction of the time when frost control will be invoked at the threshold temperature. This field only used for exhaust air recirc and exhaust-only frost control types."
                    },
                    "rate_of_defrost_time_fraction_increase": {
                        "type": "number",
                        "units": "1/K",
                        "minimum": 0.0,
                        "default": 0.012,
                        "note": "Rate of increase in defrost time fraction as actual temp falls below threshold temperature. This field only used for exhaust air recirc and exhaust-only frost control types."
                    },
                    "economizer_lockout": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes",
                        "note": "Yes means that the heat exchanger will be locked out (off) when the economizer is operating or high humidity control is active"
                    }
                },
                "required": [
                    "nominal_supply_air_flow_rate",
                    "supply_air_inlet_node_name",
                    "supply_air_outlet_node_name",
                    "exhaust_air_inlet_node_name",
                    "exhaust_air_outlet_node_name"
                ]
            }
        },
        "group": "Heat Recovery",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "AFNHeatExchangerNames",
                "HXAirToAirNames",
                "HXAirToAirSensibleAndLatentNames",
                "validBranchEquipmentNames",
                "validOASysEquipmentNames"
            ],
            "reference-class-name": [
                "validBranchEquipmentTypes",
                "validOASysEquipmentTypes"
            ]
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
                "nominal_supply_air_flow_rate": {
                    "field_name": "Nominal Supply Air Flow Rate",
                    "field_type": "n"
                },
                "sensible_effectiveness_at_100_heating_air_flow": {
                    "field_name": "Sensible Effectiveness at 100% Heating Air Flow",
                    "field_type": "n"
                },
                "latent_effectiveness_at_100_heating_air_flow": {
                    "field_name": "Latent Effectiveness at 100% Heating Air Flow",
                    "field_type": "n"
                },
                "sensible_effectiveness_at_75_heating_air_flow": {
                    "field_name": "Sensible Effectiveness at 75% Heating Air Flow",
                    "field_type": "n"
                },
                "latent_effectiveness_at_75_heating_air_flow": {
                    "field_name": "Latent Effectiveness at 75% Heating Air Flow",
                    "field_type": "n"
                },
                "sensible_effectiveness_at_100_cooling_air_flow": {
                    "field_name": "Sensible Effectiveness at 100% Cooling Air Flow",
                    "field_type": "n"
                },
                "latent_effectiveness_at_100_cooling_air_flow": {
                    "field_name": "Latent Effectiveness at 100% Cooling Air Flow",
                    "field_type": "n"
                },
                "sensible_effectiveness_at_75_cooling_air_flow": {
                    "field_name": "Sensible Effectiveness at 75% Cooling Air Flow",
                    "field_type": "n"
                },
                "latent_effectiveness_at_75_cooling_air_flow": {
                    "field_name": "Latent Effectiveness at 75% Cooling Air Flow",
                    "field_type": "n"
                },
                "supply_air_inlet_node_name": {
                    "field_name": "Supply Air Inlet Node Name",
                    "field_type": "a"
                },
                "supply_air_outlet_node_name": {
                    "field_name": "Supply Air Outlet Node Name",
                    "field_type": "a"
                },
                "exhaust_air_inlet_node_name": {
                    "field_name": "Exhaust Air Inlet Node Name",
                    "field_type": "a"
                },
                "exhaust_air_outlet_node_name": {
                    "field_name": "Exhaust Air Outlet Node Name",
                    "field_type": "a"
                },
                "nominal_electric_power": {
                    "field_name": "Nominal Electric Power",
                    "field_type": "n"
                },
                "supply_air_outlet_temperature_control": {
                    "field_name": "Supply Air Outlet Temperature Control",
                    "field_type": "a"
                },
                "heat_exchanger_type": {
                    "field_name": "Heat Exchanger Type",
                    "field_type": "a"
                },
                "frost_control_type": {
                    "field_name": "Frost Control Type",
                    "field_type": "a"
                },
                "threshold_temperature": {
                    "field_name": "Threshold Temperature",
                    "field_type": "n"
                },
                "initial_defrost_time_fraction": {
                    "field_name": "Initial Defrost Time Fraction",
                    "field_type": "n"
                },
                "rate_of_defrost_time_fraction_increase": {
                    "field_name": "Rate of Defrost Time Fraction Increase",
                    "field_type": "n"
                },
                "economizer_lockout": {
                    "field_name": "Economizer Lockout",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "nominal_supply_air_flow_rate",
                "sensible_effectiveness_at_100_heating_air_flow",
                "latent_effectiveness_at_100_heating_air_flow",
                "sensible_effectiveness_at_75_heating_air_flow",
                "latent_effectiveness_at_75_heating_air_flow",
                "sensible_effectiveness_at_100_cooling_air_flow",
                "latent_effectiveness_at_100_cooling_air_flow",
                "sensible_effectiveness_at_75_cooling_air_flow",
                "latent_effectiveness_at_75_cooling_air_flow",
                "supply_air_inlet_node_name",
                "supply_air_outlet_node_name",
                "exhaust_air_inlet_node_name",
                "exhaust_air_outlet_node_name",
                "nominal_electric_power",
                "supply_air_outlet_temperature_control",
                "heat_exchanger_type",
                "frost_control_type",
                "threshold_temperature",
                "initial_defrost_time_fraction",
                "rate_of_defrost_time_fraction_increase",
                "economizer_lockout"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "supply_air_inlet_node_name",
                    "supply_air_outlet_node_name",
                    "exhaust_air_inlet_node_name",
                    "exhaust_air_outlet_node_name",
                    "supply_air_outlet_temperature_control",
                    "heat_exchanger_type",
                    "frost_control_type",
                    "economizer_lockout"
                ]
            },
            "numerics": {
                "fields": [
                    "nominal_supply_air_flow_rate",
                    "sensible_effectiveness_at_100_heating_air_flow",
                    "latent_effectiveness_at_100_heating_air_flow",
                    "sensible_effectiveness_at_75_heating_air_flow",
                    "latent_effectiveness_at_75_heating_air_flow",
                    "sensible_effectiveness_at_100_cooling_air_flow",
                    "latent_effectiveness_at_100_cooling_air_flow",
                    "sensible_effectiveness_at_75_cooling_air_flow",
                    "latent_effectiveness_at_75_cooling_air_flow",
                    "nominal_electric_power",
                    "threshold_temperature",
                    "initial_defrost_time_fraction",
                    "rate_of_defrost_time_fraction_increase"
                ]
            }
        },
        "type": "object",
        "memo": "This object models an air-to-air heat exchanger using effectiveness relationships. The heat exchanger can transfer sensible energy, latent energy, or both between the supply (primary) and exhaust (secondary) air streams.",
        "min_fields": 19.0
    }
}
```
