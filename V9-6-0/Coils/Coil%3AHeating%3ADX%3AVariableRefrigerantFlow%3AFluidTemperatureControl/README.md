```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "availability_schedule": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Enter the name of a schedule that defines the availability of the coil Schedule values of 0 denote the unit is off. All other values denote the unit is available If this field is left blank, the unit is available the entire simulation"
                },
                "coil_air_inlet_node": {
                    "type": "string",
                    "note": "the inlet node to the coil"
                },
                "coil_air_outlet_node": {
                    "type": "string",
                    "note": "the outlet node to the coil"
                },
                "rated_total_heating_capacity": {
                    "units": "W",
                    "note": "Supply air fan heat is not included",
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
                "indoor_unit_reference_subcooling": {
                    "type": "number",
                    "units": "deltaC",
                    "minimum": 0.0,
                    "default": 5.0
                },
                "indoor_unit_condensing_temperature_function_of_subcooling_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                }
            },
            "required": [
                "coil_air_inlet_node",
                "coil_air_outlet_node",
                "rated_total_heating_capacity",
                "indoor_unit_condensing_temperature_function_of_subcooling_curve_name"
            ]
        }
    },
    "group": "Coils",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "HeatingCoilsDXVarRefrigFlowFluidTemperatureControl"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "availability_schedule": {
                "field_name": "Availability Schedule",
                "field_type": "a"
            },
            "coil_air_inlet_node": {
                "field_name": "Coil Air Inlet Node",
                "field_type": "a"
            },
            "coil_air_outlet_node": {
                "field_name": "Coil Air Outlet Node",
                "field_type": "a"
            },
            "rated_total_heating_capacity": {
                "field_name": "Rated Total Heating Capacity",
                "field_type": "n"
            },
            "indoor_unit_reference_subcooling": {
                "field_name": "Indoor Unit Reference Subcooling",
                "field_type": "n"
            },
            "indoor_unit_condensing_temperature_function_of_subcooling_curve_name": {
                "field_name": "Indoor Unit Condensing Temperature Function of Subcooling Curve Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "availability_schedule",
            "coil_air_inlet_node",
            "coil_air_outlet_node",
            "rated_total_heating_capacity",
            "indoor_unit_reference_subcooling",
            "indoor_unit_condensing_temperature_function_of_subcooling_curve_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule",
                "coil_air_inlet_node",
                "coil_air_outlet_node",
                "indoor_unit_condensing_temperature_function_of_subcooling_curve_name"
            ]
        },
        "numerics": {
            "fields": [
                "rated_total_heating_capacity",
                "indoor_unit_reference_subcooling"
            ]
        }
    },
    "type": "object",
    "memo": "This is a key object in the new physics based VRF model applicable for Fluid Temperature Control. It describes the the indoor unit coil of the system at heating mode. Used with ZoneHVAC:TerminalUnit:VariableRefrigerantFlow. Outdoor unit is modeled separately, see AirConditioner:VariableRefrigerantFlow:FluidTemperatureControl or AirConditioner:VariableRefrigerantFlow:FluidTemperatureControl:HR",
    "min_fields": 5.0
}
```
