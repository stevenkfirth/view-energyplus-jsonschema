```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "nominal_capacity": {
                    "units": "W",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "nominal_cop": {
                    "type": "number",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0
                },
                "design_chilled_water_flow_rate": {
                    "note": "For variable volume this is the maximum flow and for constant flow this is the flow.",
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "design_condenser_water_flow_rate": {
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "note": "This field is not used for Condenser Type = AirCooled or EvaporativelyCooled",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "chilled_water_inlet_node_name": {
                    "type": "string"
                },
                "chilled_water_outlet_node_name": {
                    "type": "string"
                },
                "condenser_inlet_node_name": {
                    "type": "string"
                },
                "condenser_outlet_node_name": {
                    "type": "string"
                },
                "condenser_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "AirCooled",
                        "EvaporativelyCooled",
                        "WaterCooled"
                    ],
                    "default": "AirCooled"
                },
                "chiller_flow_mode": {
                    "type": "string",
                    "note": "Select operating mode for fluid flow through the chiller. \"NotModulated\" is for either variable or constant pumping with flow controlled by the external plant system. \"ConstantFlow\" is for constant pumping with flow controlled by chiller to operate at full design flow rate. \"LeavingSetpointModulated\" is for variable pumping with flow controlled by chiller to vary flow to target a leaving temperature setpoint.",
                    "enum": [
                        "",
                        "ConstantFlow",
                        "LeavingSetpointModulated",
                        "NotModulated"
                    ],
                    "default": "NotModulated"
                },
                "sizing_factor": {
                    "type": "number",
                    "note": "Multiplies the autosized capacity and flow rates",
                    "exclusiveMinimum": 0.0,
                    "default": 1.0
                },
                "basin_heater_capacity": {
                    "type": "number",
                    "units": "W/K",
                    "minimum": 0.0,
                    "default": 0.0,
                    "note": "This field is only used for Condenser Type = EvaporativelyCooled and for periods when the basin heater is available (field Basin Heater Operating Schedule Name). For this situation, the heater maintains the basin water temperature at the basin heater setpoint temperature when the outdoor air temperature falls below the setpoint temperature. The basin heater only operates when the chiller is not operating."
                },
                "basin_heater_setpoint_temperature": {
                    "type": "number",
                    "units": "C",
                    "minimum": 2.0,
                    "default": 2.0,
                    "note": "This field is only used for Condenser Type = EvaporativelyCooled. Enter the outdoor dry-bulb temperature when the basin heater turns on."
                },
                "basin_heater_operating_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "This field is only used for Condenser Type = EvaporativelyCooled. Schedule values greater than 0 allow the basin heater to operate whenever the outdoor air dry-bulb temperature is below the basin heater setpoint temperature. If a schedule name is not entered, the basin heater is allowed to operate throughout the entire simulation."
                }
            },
            "required": [
                "nominal_capacity",
                "nominal_cop",
                "chilled_water_inlet_node_name",
                "chilled_water_outlet_node_name"
            ]
        }
    },
    "group": "Plant Heating and Cooling Equipment",
    "name": {
        "type": "string",
        "reference": [
            "Chillers",
            "validBranchEquipmentNames",
            "validPlantEquipmentNames"
        ],
        "is_required": true,
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
            "nominal_capacity": {
                "field_name": "Nominal Capacity",
                "field_type": "n"
            },
            "nominal_cop": {
                "field_name": "Nominal COP",
                "field_type": "n"
            },
            "design_chilled_water_flow_rate": {
                "field_name": "Design Chilled Water Flow Rate",
                "field_type": "n"
            },
            "design_condenser_water_flow_rate": {
                "field_name": "Design Condenser Water Flow Rate",
                "field_type": "n"
            },
            "chilled_water_inlet_node_name": {
                "field_name": "Chilled Water Inlet Node Name",
                "field_type": "a"
            },
            "chilled_water_outlet_node_name": {
                "field_name": "Chilled Water Outlet Node Name",
                "field_type": "a"
            },
            "condenser_inlet_node_name": {
                "field_name": "Condenser Inlet Node Name",
                "field_type": "a"
            },
            "condenser_outlet_node_name": {
                "field_name": "Condenser Outlet Node Name",
                "field_type": "a"
            },
            "condenser_type": {
                "field_name": "Condenser Type",
                "field_type": "a"
            },
            "chiller_flow_mode": {
                "field_name": "Chiller Flow Mode",
                "field_type": "a"
            },
            "sizing_factor": {
                "field_name": "Sizing Factor",
                "field_type": "n"
            },
            "basin_heater_capacity": {
                "field_name": "Basin Heater Capacity",
                "field_type": "n"
            },
            "basin_heater_setpoint_temperature": {
                "field_name": "Basin Heater Setpoint Temperature",
                "field_type": "n"
            },
            "basin_heater_operating_schedule_name": {
                "field_name": "Basin Heater Operating Schedule Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "nominal_capacity",
            "nominal_cop",
            "design_chilled_water_flow_rate",
            "design_condenser_water_flow_rate",
            "chilled_water_inlet_node_name",
            "chilled_water_outlet_node_name",
            "condenser_inlet_node_name",
            "condenser_outlet_node_name",
            "condenser_type",
            "chiller_flow_mode",
            "sizing_factor",
            "basin_heater_capacity",
            "basin_heater_setpoint_temperature",
            "basin_heater_operating_schedule_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "chilled_water_inlet_node_name",
                "chilled_water_outlet_node_name",
                "condenser_inlet_node_name",
                "condenser_outlet_node_name",
                "condenser_type",
                "chiller_flow_mode",
                "basin_heater_operating_schedule_name"
            ]
        },
        "numerics": {
            "fields": [
                "nominal_capacity",
                "nominal_cop",
                "design_chilled_water_flow_rate",
                "design_condenser_water_flow_rate",
                "sizing_factor",
                "basin_heater_capacity",
                "basin_heater_setpoint_temperature"
            ]
        }
    },
    "type": "object",
    "memo": "This constant COP chiller model provides a means of quickly specifying a Chiller where performance data is not available.",
    "min_fields": 12.0
}
```
