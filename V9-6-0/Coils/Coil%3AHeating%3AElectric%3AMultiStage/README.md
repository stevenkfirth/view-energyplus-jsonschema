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
                "air_inlet_node_name": {
                    "type": "string"
                },
                "air_outlet_node_name": {
                    "type": "string"
                },
                "temperature_setpoint_node_name": {
                    "type": "string",
                    "note": "Required if coil is temperature controlled. controlled"
                },
                "number_of_stages": {
                    "type": "number",
                    "minimum": 1.0,
                    "maximum": 4.0,
                    "note": "Enter the number of the following sets of data for coil capacity and Efficiency."
                },
                "stage_1_efficiency": {
                    "type": "number",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0
                },
                "stage_1_nominal_capacity": {
                    "units": "W",
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
                "stage_2_efficiency": {
                    "type": "number",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0
                },
                "stage_2_nominal_capacity": {
                    "units": "W",
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
                "stage_3_efficiency": {
                    "type": "number",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0
                },
                "stage_3_nominal_capacity": {
                    "units": "W",
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
                "stage_4_efficiency": {
                    "type": "number",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0
                },
                "stage_4_nominal_capacity": {
                    "units": "W",
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
                }
            },
            "required": [
                "air_inlet_node_name",
                "air_outlet_node_name",
                "number_of_stages",
                "stage_1_efficiency",
                "stage_1_nominal_capacity"
            ]
        }
    },
    "group": "Coils",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "HeatingCoilsElectricMultiStage"
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
            "air_inlet_node_name": {
                "field_name": "Air Inlet Node Name",
                "field_type": "a"
            },
            "air_outlet_node_name": {
                "field_name": "Air Outlet Node Name",
                "field_type": "a"
            },
            "temperature_setpoint_node_name": {
                "field_name": "Temperature Setpoint Node Name",
                "field_type": "a"
            },
            "number_of_stages": {
                "field_name": "Number of Stages",
                "field_type": "n"
            },
            "stage_1_efficiency": {
                "field_name": "Stage 1 Efficiency",
                "field_type": "n"
            },
            "stage_1_nominal_capacity": {
                "field_name": "Stage 1 Nominal Capacity",
                "field_type": "n"
            },
            "stage_2_efficiency": {
                "field_name": "Stage 2 Efficiency",
                "field_type": "n"
            },
            "stage_2_nominal_capacity": {
                "field_name": "Stage 2 Nominal Capacity",
                "field_type": "n"
            },
            "stage_3_efficiency": {
                "field_name": "Stage 3 Efficiency",
                "field_type": "n"
            },
            "stage_3_nominal_capacity": {
                "field_name": "Stage 3 Nominal Capacity",
                "field_type": "n"
            },
            "stage_4_efficiency": {
                "field_name": "Stage 4 Efficiency",
                "field_type": "n"
            },
            "stage_4_nominal_capacity": {
                "field_name": "Stage 4 Nominal Capacity",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "air_inlet_node_name",
            "air_outlet_node_name",
            "temperature_setpoint_node_name",
            "number_of_stages",
            "stage_1_efficiency",
            "stage_1_nominal_capacity",
            "stage_2_efficiency",
            "stage_2_nominal_capacity",
            "stage_3_efficiency",
            "stage_3_nominal_capacity",
            "stage_4_efficiency",
            "stage_4_nominal_capacity"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "temperature_setpoint_node_name"
            ]
        },
        "numerics": {
            "fields": [
                "number_of_stages",
                "stage_1_efficiency",
                "stage_1_nominal_capacity",
                "stage_2_efficiency",
                "stage_2_nominal_capacity",
                "stage_3_efficiency",
                "stage_3_nominal_capacity",
                "stage_4_efficiency",
                "stage_4_nominal_capacity"
            ]
        }
    },
    "type": "object",
    "memo": "Electric heating coil, multi-stage. If the coil is located directly in an air loop branch or outdoor air equipment list, then it is controlled on leaving air temperature and the Temperature Setpoint Node Name must be specified. If the coil is contained within another component such as an air terminal unit, zone HVAC equipment, or unitary system, then the coil is controlled by the parent component and the setpoint node name is not entered."
}
```
