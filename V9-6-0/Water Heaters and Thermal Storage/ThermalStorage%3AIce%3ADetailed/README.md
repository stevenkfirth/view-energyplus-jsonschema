```
{
    "ThermalStorage:Ice:Detailed": {
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
                    "capacity": {
                        "type": "number",
                        "note": "This includes only the latent storage capacity",
                        "units": "GJ"
                    },
                    "inlet_node_name": {
                        "type": "string"
                    },
                    "outlet_node_name": {
                        "type": "string"
                    },
                    "discharging_curve_variable_specifications": {
                        "type": "string",
                        "enum": [
                            "FractionChargedLMTD",
                            "FractionDischargedLMTD",
                            "LMTDFractionCharged",
                            "LMTDMassFlow"
                        ]
                    },
                    "discharging_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ]
                    },
                    "charging_curve_variable_specifications": {
                        "type": "string",
                        "enum": [
                            "FractionChargedLMTD",
                            "FractionDischargedLMTD",
                            "LMTDFractionCharged",
                            "LMTDMassFlow"
                        ]
                    },
                    "charging_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ]
                    },
                    "timestep_of_the_curve_data": {
                        "type": "number",
                        "units": "hr"
                    },
                    "parasitic_electric_load_during_discharging": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "parasitic_electric_load_during_charging": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "tank_loss_coefficient": {
                        "type": "number",
                        "note": "This is the fraction the total storage capacity that is lost or melts each hour",
                        "units": "dimensionless"
                    },
                    "freezing_temperature_of_storage_medium": {
                        "type": "number",
                        "note": "This temperature is typically 0C for water. Simply changing this temperature without adjusting the performance parameters input above is inappropriate and not advised.",
                        "units": "C",
                        "default": 0.0
                    },
                    "thaw_process_indicator": {
                        "type": "string",
                        "note": "This field determines whether the system uses internal or external melt during discharging. This will then have an impact on charging performance.",
                        "enum": [
                            "",
                            "InsideMelt",
                            "OutsideMelt"
                        ],
                        "default": "OutsideMelt"
                    }
                },
                "required": [
                    "capacity",
                    "inlet_node_name",
                    "outlet_node_name",
                    "discharging_curve_variable_specifications",
                    "discharging_curve_name",
                    "charging_curve_variable_specifications",
                    "charging_curve_name"
                ]
            }
        },
        "group": "Water Heaters and Thermal Storage",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "IceThermalStorageEquipment",
                "validBranchEquipmentNames",
                "validPlantEquipmentNames"
            ],
            "reference-class-name": [
                "validBranchEquipmentTypes",
                "validPlantEquipmentTypes"
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
                "capacity": {
                    "field_name": "Capacity",
                    "field_type": "n"
                },
                "inlet_node_name": {
                    "field_name": "Inlet Node Name",
                    "field_type": "a"
                },
                "outlet_node_name": {
                    "field_name": "Outlet Node Name",
                    "field_type": "a"
                },
                "discharging_curve_variable_specifications": {
                    "field_name": "Discharging Curve Variable Specifications",
                    "field_type": "a"
                },
                "discharging_curve_name": {
                    "field_name": "Discharging Curve Name",
                    "field_type": "a"
                },
                "charging_curve_variable_specifications": {
                    "field_name": "Charging Curve Variable Specifications",
                    "field_type": "a"
                },
                "charging_curve_name": {
                    "field_name": "Charging Curve Name",
                    "field_type": "a"
                },
                "timestep_of_the_curve_data": {
                    "field_name": "Timestep of the Curve Data",
                    "field_type": "n"
                },
                "parasitic_electric_load_during_discharging": {
                    "field_name": "Parasitic Electric Load During Discharging",
                    "field_type": "n"
                },
                "parasitic_electric_load_during_charging": {
                    "field_name": "Parasitic Electric Load During Charging",
                    "field_type": "n"
                },
                "tank_loss_coefficient": {
                    "field_name": "Tank Loss Coefficient",
                    "field_type": "n"
                },
                "freezing_temperature_of_storage_medium": {
                    "field_name": "Freezing Temperature of Storage Medium",
                    "field_type": "n"
                },
                "thaw_process_indicator": {
                    "field_name": "Thaw Process Indicator",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "capacity",
                "inlet_node_name",
                "outlet_node_name",
                "discharging_curve_variable_specifications",
                "discharging_curve_name",
                "charging_curve_variable_specifications",
                "charging_curve_name",
                "timestep_of_the_curve_data",
                "parasitic_electric_load_during_discharging",
                "parasitic_electric_load_during_charging",
                "tank_loss_coefficient",
                "freezing_temperature_of_storage_medium",
                "thaw_process_indicator"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "inlet_node_name",
                    "outlet_node_name",
                    "discharging_curve_variable_specifications",
                    "discharging_curve_name",
                    "charging_curve_variable_specifications",
                    "charging_curve_name",
                    "thaw_process_indicator"
                ]
            },
            "numerics": {
                "fields": [
                    "capacity",
                    "timestep_of_the_curve_data",
                    "parasitic_electric_load_during_discharging",
                    "parasitic_electric_load_during_charging",
                    "tank_loss_coefficient",
                    "freezing_temperature_of_storage_medium"
                ]
            }
        },
        "type": "object",
        "memo": "This input syntax is intended to describe a thermal storage system that includes smaller containers filled with water that are placed in a larger tank or series of tanks. The model uses polynomial equations to describe the system performance.",
        "min_fields": 14.0
    }
}
```
