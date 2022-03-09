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
                "fuel_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "Coal",
                        "Diesel",
                        "FuelOilNo1",
                        "FuelOilNo2",
                        "Gasoline",
                        "NaturalGas",
                        "OtherFuel1",
                        "OtherFuel2",
                        "Propane"
                    ],
                    "default": "NaturalGas"
                },
                "burner_efficiency": {
                    "type": "number",
                    "maximum": 1.0,
                    "minimum": 0.0,
                    "default": 0.8
                },
                "nominal_capacity": {
                    "units": "W",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
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
                    "note": "optional, used if coil is temperature control and not load-base controlled"
                },
                "parasitic_electric_load": {
                    "type": "number",
                    "units": "W",
                    "note": "parasitic electric load associated with the coil operation such as an inducer fan, etc... This will be modified by the part load ratio to reflect the time of operation in a timestep.",
                    "ip-units": "W"
                },
                "part_load_fraction_correlation_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "quadratic curve, PLF = a + b*PLR + c*PLR**2 cubic curve, PLF = a + b*PLR + c*PLR**2 + d*PLR**3 PLF = part load fraction PLR = part load ratio (sensible heating load/steady state heating capacity) Coil runtime fraction = Part Load Ratio / PLF This part load degradation is for coil performance & will increase the fuel consumption of the coil due to transient coil operation."
                },
                "parasitic_fuel_load": {
                    "type": "number",
                    "units": "W",
                    "note": "parasitic fuel load associated with the coil operation (i.e., standing pilot)"
                }
            },
            "required": [
                "air_inlet_node_name",
                "air_outlet_node_name"
            ]
        }
    },
    "group": "Coils",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "AFNCoilNames",
            "HeatingCoilName",
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
            "fuel_type": {
                "field_name": "Fuel Type",
                "field_type": "a"
            },
            "burner_efficiency": {
                "field_name": "Burner Efficiency",
                "field_type": "n"
            },
            "nominal_capacity": {
                "field_name": "Nominal Capacity",
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
            "temperature_setpoint_node_name": {
                "field_name": "Temperature Setpoint Node Name",
                "field_type": "a"
            },
            "parasitic_electric_load": {
                "field_name": "Parasitic Electric Load",
                "field_type": "n"
            },
            "part_load_fraction_correlation_curve_name": {
                "field_name": "Part Load Fraction Correlation Curve Name",
                "field_type": "a"
            },
            "parasitic_fuel_load": {
                "field_name": "Parasitic Fuel Load",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "fuel_type",
            "burner_efficiency",
            "nominal_capacity",
            "air_inlet_node_name",
            "air_outlet_node_name",
            "temperature_setpoint_node_name",
            "parasitic_electric_load",
            "part_load_fraction_correlation_curve_name",
            "parasitic_fuel_load"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "fuel_type",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "temperature_setpoint_node_name",
                "part_load_fraction_correlation_curve_name"
            ]
        },
        "numerics": {
            "fields": [
                "burner_efficiency",
                "nominal_capacity",
                "parasitic_electric_load",
                "parasitic_fuel_load"
            ]
        }
    },
    "type": "object",
    "memo": "Gas or other fuel heating coil. If the coil is located directly in an air loop branch or outdoor air equipment list, then it is controlled on leaving air temperature and the Temperature Setpoint Node Name must be specified. If the coil is contained within another component such as an air terminal unit, zone HVAC equipment, or unitary system, then the coil is controlled by the parent component and the setpoint node name is not entered.",
    "min_fields": 7.0
}
```
