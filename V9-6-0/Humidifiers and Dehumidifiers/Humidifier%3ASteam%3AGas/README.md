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
                "rated_capacity": {
                    "note": "Capacity is m3/s of water at 5.05 C The nominal full capacity water addition rate in m3/s of water at 5.05 C",
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
                "rated_gas_use_rate": {
                    "units": "W",
                    "ip-units": "W",
                    "note": "if auto-sized, the rated gas use rate is calculated from the rated capacity and enthalpy rise of water from 20.0C to 100.0C steam and user input thermal efficiency value specified in the next input field. If this input field is hard-sized and Inlet Water Temperature Option input field is selected as FixedInletWaterTemperature, then the thermal efficiency input field will not be used or else if the Inlet Water Temperature Option input field is selected as VariableInletWaterTemperature, then the thermal efficiency input value is overridden by a value calculated from the capacity, rated gas use rate and design condition.",
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
                "thermal_efficiency": {
                    "type": "number",
                    "units": "dimensionless",
                    "exclusiveMinimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.8,
                    "note": "Based on the higher heating value of fuel. If \"Rated Gas Use Rate\" in the field above is not auto-sized and the Inlet Water Temperature Option input field is specified as FixedInletWaterTemperature, then the thermal efficiency specified will not be used in the calculation, or else if the Inlet Water Temperature Option input field is selected as VariableInletWaterTemperature, then the thermal efficiency value is overridden by a value calculated from the capacity, rated gas use rate and design condition."
                },
                "thermal_efficiency_modifier_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Linear, Quadratic and Cubic efficiency curves are solely a function of PLR. Linear = C1 + C2*PLR Quadratic = C1 + C2*PLR + C3*PLR^2 Cubic = C1 + C2*PLR + C3*PLR^2 + C4*PLR^3 This is thermal efficiency modifier curve name of gas fired steam humidifier. This curve is normalized, i.e., curve output value at rated condition is 1.0."
                },
                "rated_fan_power": {
                    "type": "number",
                    "units": "W",
                    "minimum": 0.0,
                    "ip-units": "W",
                    "note": "The nominal full capacity electric power input to the blower fan in Watts. If no blower fan is required to inject the dry steam to the supply air stream, then this input field is set to zero."
                },
                "auxiliary_electric_power": {
                    "type": "number",
                    "units": "W",
                    "minimum": 0.0,
                    "ip-units": "W",
                    "default": 0.0,
                    "note": "The auxiliary electric power input in watts. This amount of power will be consumed whenever the unit is available (as defined by the availability schedule). This electric power is used for control purpose only."
                },
                "air_inlet_node_name": {
                    "type": "string"
                },
                "air_outlet_node_name": {
                    "type": "string"
                },
                "water_storage_tank_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "WaterStorageTankNames"
                    ]
                },
                "inlet_water_temperature_option": {
                    "type": "string",
                    "note": "The inlet water temperature can be fixed at 20C as it is done for electric steam humidifier or it can be allowed to vary with temperature of the water source. Currently allowed water sources are main water or water storage tank in water use objects. if FixedInletWaterTemperature is specified, then a fixed 20C water temperature will be used, or else if VariableInletWaterTemperature is specified, then inlet water will vary depending the source water temperature. If this input field is left blank, then fixed inlet water temperature of 20C will be assumed.",
                    "enum": [
                        "",
                        "FixedInletWaterTemperature",
                        "VariableInletWaterTemperature"
                    ],
                    "default": "FixedInletWaterTemperature"
                }
            }
        }
    },
    "group": "Humidifiers and Dehumidifiers",
    "name": {
        "type": "string",
        "is_required": true,
        "reference-class-name": [
            "validBranchEquipmentTypes",
            "validOASysEquipmentTypes"
        ],
        "reference": [
            "validBranchEquipmentNames",
            "validOASysEquipmentNames"
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
            "rated_capacity": {
                "field_name": "Rated Capacity",
                "field_type": "n"
            },
            "rated_gas_use_rate": {
                "field_name": "Rated Gas Use Rate",
                "field_type": "n"
            },
            "thermal_efficiency": {
                "field_name": "Thermal Efficiency",
                "field_type": "n"
            },
            "thermal_efficiency_modifier_curve_name": {
                "field_name": "Thermal Efficiency Modifier Curve Name",
                "field_type": "a"
            },
            "rated_fan_power": {
                "field_name": "Rated Fan Power",
                "field_type": "n"
            },
            "auxiliary_electric_power": {
                "field_name": "Auxiliary Electric Power",
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
            "water_storage_tank_name": {
                "field_name": "Water Storage Tank Name",
                "field_type": "a"
            },
            "inlet_water_temperature_option": {
                "field_name": "Inlet Water Temperature Option",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "rated_capacity",
            "rated_gas_use_rate",
            "thermal_efficiency",
            "thermal_efficiency_modifier_curve_name",
            "rated_fan_power",
            "auxiliary_electric_power",
            "air_inlet_node_name",
            "air_outlet_node_name",
            "water_storage_tank_name",
            "inlet_water_temperature_option"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "thermal_efficiency_modifier_curve_name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "water_storage_tank_name",
                "inlet_water_temperature_option"
            ]
        },
        "numerics": {
            "fields": [
                "rated_capacity",
                "rated_gas_use_rate",
                "thermal_efficiency",
                "rated_fan_power",
                "auxiliary_electric_power"
            ]
        }
    },
    "type": "object",
    "memo": "Natural gas fired steam humidifier with optional blower fan."
}
```
