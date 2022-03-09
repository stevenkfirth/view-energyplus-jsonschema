```
{
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
                "heat_reclaim_recovery_efficiency": {
                    "type": "number",
                    "minimum": 0.0
                },
                "air_inlet_node_name": {
                    "type": "string"
                },
                "air_outlet_node_name": {
                    "type": "string"
                },
                "heating_source_object_type": {
                    "type": "string",
                    "enum": [
                        "Coil:Cooling:DX:SingleSpeed",
                        "Coil:Cooling:DX:TwoSpeed",
                        "Coil:Cooling:DX:TwoStageWithHumidityControlMode",
                        "Coil:Cooling:DX:VariableSpeed",
                        "Refrigeration:CompressorRack",
                        "Refrigeration:Condenser:AirCooled",
                        "Refrigeration:Condenser:EvaporativeCooled",
                        "Refrigeration:Condenser:WaterCooled"
                    ]
                },
                "heating_source_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "DesuperHeatingCoilSources"
                    ]
                },
                "temperature_setpoint_node_name": {
                    "type": "string",
                    "note": "Required if coil is temperature controlled. Temperature-based control requires the use of a SetpointManager object"
                },
                "parasitic_electric_load": {
                    "type": "number",
                    "units": "W",
                    "minimum": 0.0,
                    "note": "parasitic electric load associated with the desuperheater coil operation such as solenoid valves, etc.",
                    "ip-units": "W"
                }
            },
            "required": [
                "air_inlet_node_name",
                "air_outlet_node_name",
                "heating_source_object_type",
                "heating_source_name"
            ]
        }
    },
    "group": "Coils",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "AFNCoilNames",
            "HeatingCoilsDesuperheater",
            "validBranchEquipmentNames"
        ],
        "reference-class-name": [
            "validBranchEquipmentTypes"
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
            "heat_reclaim_recovery_efficiency": {
                "field_name": "Heat Reclaim Recovery Efficiency",
                "field_type": "n"
            },
            "air_inlet_node_name": {
                "field_name": "Air Inlet Node Name",
                "field_type": "a"
            },
            "air_outlet_node_name": {
                "field_name": "Air Outlet Node Name",
                "field_type": "a"
            },
            "heating_source_object_type": {
                "field_name": "Heating Source Object Type",
                "field_type": "a"
            },
            "heating_source_name": {
                "field_name": "Heating Source Name",
                "field_type": "a"
            },
            "temperature_setpoint_node_name": {
                "field_name": "Temperature Setpoint Node Name",
                "field_type": "a"
            },
            "parasitic_electric_load": {
                "field_name": "Parasitic Electric Load",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "heat_reclaim_recovery_efficiency",
            "air_inlet_node_name",
            "air_outlet_node_name",
            "heating_source_object_type",
            "heating_source_name",
            "temperature_setpoint_node_name",
            "parasitic_electric_load"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "heating_source_object_type",
                "heating_source_name",
                "temperature_setpoint_node_name"
            ]
        },
        "numerics": {
            "fields": [
                "heat_reclaim_recovery_efficiency",
                "parasitic_electric_load"
            ]
        }
    },
    "type": "object",
    "memo": "Desuperheater air heating coil. The heating energy provided by this coil is reclaimed from the superheated refrigerant gas leaving a compressor and does not impact the performance of the compressor. If the coil is located directly in an air loop branch or outdoor air equipment list, then it is controlled on leaving air temperature and the Temperature Setpoint Node Name must be specified. If the coil is contained within another component such as a unitary system, then the coil is controlled by the parent component and the setpoint node name is not entered.",
    "min_fields": 7.0
}
```
