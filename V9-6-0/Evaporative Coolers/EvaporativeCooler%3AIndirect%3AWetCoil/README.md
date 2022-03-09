```
{
    "EvaporativeCooler:Indirect:WetCoil": {
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
                    "coil_maximum_efficiency": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "coil_flow_ratio": {
                        "type": "number"
                    },
                    "recirculating_water_pump_power_consumption": {
                        "type": "number",
                        "units": "W",
                        "ip-units": "W"
                    },
                    "secondary_air_fan_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0
                    },
                    "secondary_air_fan_total_efficiency": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0
                    },
                    "secondary_air_fan_delta_pressure": {
                        "type": "number",
                        "units": "Pa",
                        "minimum": 0.0,
                        "ip-units": "inH2O"
                    },
                    "primary_air_inlet_node_name": {
                        "type": "string"
                    },
                    "primary_air_outlet_node_name": {
                        "type": "string"
                    },
                    "control_type": {
                        "type": "string",
                        "note": "This field is not currently used and can be left blank"
                    },
                    "water_supply_storage_tank_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "WaterStorageTankNames"
                        ]
                    },
                    "secondary_air_inlet_node_name": {
                        "type": "string",
                        "note": "Enter the name of an outdoor air node"
                    }
                },
                "required": [
                    "coil_maximum_efficiency",
                    "recirculating_water_pump_power_consumption",
                    "secondary_air_fan_flow_rate",
                    "secondary_air_fan_total_efficiency",
                    "secondary_air_fan_delta_pressure",
                    "primary_air_inlet_node_name",
                    "primary_air_outlet_node_name",
                    "secondary_air_inlet_node_name"
                ]
            }
        },
        "group": "Evaporative Coolers",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "EvapCoolerNames",
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
                "coil_maximum_efficiency": {
                    "field_name": "Coil Maximum Efficiency",
                    "field_type": "n"
                },
                "coil_flow_ratio": {
                    "field_name": "Coil Flow Ratio",
                    "field_type": "n"
                },
                "recirculating_water_pump_power_consumption": {
                    "field_name": "Recirculating Water Pump Power Consumption",
                    "field_type": "n"
                },
                "secondary_air_fan_flow_rate": {
                    "field_name": "Secondary Air Fan Flow Rate",
                    "field_type": "n"
                },
                "secondary_air_fan_total_efficiency": {
                    "field_name": "Secondary Air Fan Total Efficiency",
                    "field_type": "n"
                },
                "secondary_air_fan_delta_pressure": {
                    "field_name": "Secondary Air Fan Delta Pressure",
                    "field_type": "n"
                },
                "primary_air_inlet_node_name": {
                    "field_name": "Primary Air Inlet Node Name",
                    "field_type": "a"
                },
                "primary_air_outlet_node_name": {
                    "field_name": "Primary Air Outlet Node Name",
                    "field_type": "a"
                },
                "control_type": {
                    "field_name": "Control Type",
                    "field_type": "a"
                },
                "water_supply_storage_tank_name": {
                    "field_name": "Water Supply Storage Tank Name",
                    "field_type": "a"
                },
                "secondary_air_inlet_node_name": {
                    "field_name": "Secondary Air Inlet Node Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "coil_maximum_efficiency",
                "coil_flow_ratio",
                "recirculating_water_pump_power_consumption",
                "secondary_air_fan_flow_rate",
                "secondary_air_fan_total_efficiency",
                "secondary_air_fan_delta_pressure",
                "primary_air_inlet_node_name",
                "primary_air_outlet_node_name",
                "control_type",
                "water_supply_storage_tank_name",
                "secondary_air_inlet_node_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "primary_air_inlet_node_name",
                    "primary_air_outlet_node_name",
                    "control_type",
                    "water_supply_storage_tank_name",
                    "secondary_air_inlet_node_name"
                ]
            },
            "numerics": {
                "fields": [
                    "coil_maximum_efficiency",
                    "coil_flow_ratio",
                    "recirculating_water_pump_power_consumption",
                    "secondary_air_fan_flow_rate",
                    "secondary_air_fan_total_efficiency",
                    "secondary_air_fan_delta_pressure"
                ]
            }
        },
        "type": "object",
        "memo": "Indirect evaporative cooler with wetted coil, recirculating water pump, and secondary air fan. This model has no controls other than its availability schedule.",
        "min_fields": 13.0
    }
}
```
