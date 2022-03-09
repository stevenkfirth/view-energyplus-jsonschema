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
                "inlet_node_name": {
                    "type": "string"
                },
                "outlet_node_name": {
                    "type": "string"
                },
                "heating_design_capacity_method": {
                    "type": "string",
                    "enum": [
                        "",
                        "CapacityPerFloorArea",
                        "FractionOfAutosizedHeatingCapacity",
                        "HeatingDesignCapacity"
                    ],
                    "default": "HeatingDesignCapacity",
                    "note": "Enter the method used to determine the heating design capacity. HeatingDesignCapacity = > selected when the design heating capacity value or autosize is specified. CapacityPerFloorArea = > selected when the design heating capacity is determine from user specified heating capacity per floor area and zone floor area. FractionOfAutosizedHeatingCapacity = > is selected when the design heating capacity is determined from a user specified fraction and the auto-sized design heating capacity."
                },
                "heating_design_capacity": {
                    "units": "W",
                    "ip-units": "W",
                    "default": "Autosize",
                    "note": "Enter the design heating capacity. Required field when the heating design capacity method HeatingDesignCapacity.",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "",
                                "Autosize"
                            ]
                        }
                    ]
                },
                "heating_design_capacity_per_floor_area": {
                    "type": "number",
                    "units": "W/m2",
                    "minimum": 0.0,
                    "note": "Enter the heating design capacity per zone floor area. Required field when the heating design capacity method field is CapacityPerFloorArea."
                },
                "fraction_of_autosized_heating_design_capacity": {
                    "type": "number",
                    "minimum": 0.0,
                    "default": 1.0,
                    "note": "Enter the fraction of autosized heating design capacity. Required field when capacity the heating design capacity method field is FractionOfAutosizedHeatingCapacity."
                },
                "u_factor_times_area_value": {
                    "units": "W/K",
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
                "maximum_water_flow_rate": {
                    "units": "m3/s",
                    "ip-units": "gal/min",
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
                "convergence_tolerance": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 0.001
                }
            },
            "required": [
                "inlet_node_name",
                "outlet_node_name",
                "u_factor_times_area_value",
                "maximum_water_flow_rate"
            ]
        }
    },
    "group": "Zone HVAC Radiative/Convective Units",
    "name": {
        "type": "string",
        "is_required": true,
        "reference-class-name": [
            "validBranchEquipmentTypes"
        ],
        "reference": [
            "ZoneEquipmentNames",
            "validBranchEquipmentNames"
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
            "inlet_node_name": {
                "field_name": "Inlet Node Name",
                "field_type": "a"
            },
            "outlet_node_name": {
                "field_name": "Outlet Node Name",
                "field_type": "a"
            },
            "heating_design_capacity_method": {
                "field_name": "Heating Design Capacity Method",
                "field_type": "a"
            },
            "heating_design_capacity": {
                "field_name": "Heating Design Capacity",
                "field_type": "n"
            },
            "heating_design_capacity_per_floor_area": {
                "field_name": "Heating Design Capacity Per Floor Area",
                "field_type": "n"
            },
            "fraction_of_autosized_heating_design_capacity": {
                "field_name": "Fraction of Autosized Heating Design Capacity",
                "field_type": "n"
            },
            "u_factor_times_area_value": {
                "field_name": "U-Factor Times Area Value",
                "field_type": "n"
            },
            "maximum_water_flow_rate": {
                "field_name": "Maximum Water Flow Rate",
                "field_type": "n"
            },
            "convergence_tolerance": {
                "field_name": "Convergence Tolerance",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "inlet_node_name",
            "outlet_node_name",
            "heating_design_capacity_method",
            "heating_design_capacity",
            "heating_design_capacity_per_floor_area",
            "fraction_of_autosized_heating_design_capacity",
            "u_factor_times_area_value",
            "maximum_water_flow_rate",
            "convergence_tolerance"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "inlet_node_name",
                "outlet_node_name",
                "heating_design_capacity_method"
            ]
        },
        "numerics": {
            "fields": [
                "heating_design_capacity",
                "heating_design_capacity_per_floor_area",
                "fraction_of_autosized_heating_design_capacity",
                "u_factor_times_area_value",
                "maximum_water_flow_rate",
                "convergence_tolerance"
            ]
        }
    },
    "type": "object",
    "memo": "Hot water baseboard heater, convection-only. Natural convection hydronic heating unit.",
    "min_fields": 10.0
}
```
