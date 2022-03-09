```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "control_variable": {
                    "type": "string",
                    "enum": [
                        "",
                        "Temperature"
                    ],
                    "default": "Temperature"
                },
                "default_condenser_entering_water_temperature_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "This scheduled setpoint value is only used in a given timestep if the \"Optimized\" Condenser Entering Temperature does not fall within the prescribed boundary conditions."
                },
                "minimum_design_wetbulb_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "QuadvariateFunctions"
                    ]
                },
                "minimum_outside_air_wetbulb_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "QuadvariateFunctions"
                    ]
                },
                "optimized_cond_entering_water_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "QuadvariateFunctions"
                    ]
                },
                "minimum_lift": {
                    "type": "number",
                    "units": "deltaC",
                    "default": 11.1
                },
                "maximum_condenser_entering_water_temperature": {
                    "type": "number",
                    "units": "C",
                    "default": 32.0
                },
                "cooling_tower_design_inlet_air_wet_bulb_temperature": {
                    "type": "number",
                    "units": "C",
                    "default": 25.56
                },
                "setpoint_node_or_nodelist_name": {
                    "type": "string",
                    "note": "Node(s) at which control variable will be set"
                }
            },
            "required": [
                "default_condenser_entering_water_temperature_schedule_name",
                "minimum_design_wetbulb_temperature_curve_name",
                "minimum_outside_air_wetbulb_temperature_curve_name",
                "optimized_cond_entering_water_temperature_curve_name",
                "setpoint_node_or_nodelist_name"
            ]
        }
    },
    "group": "Setpoint Managers",
    "name": {
        "type": "string",
        "is_required": true
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "control_variable": {
                "field_name": "Control Variable",
                "field_type": "a"
            },
            "default_condenser_entering_water_temperature_schedule_name": {
                "field_name": "Default Condenser Entering Water Temperature Schedule Name",
                "field_type": "a"
            },
            "minimum_design_wetbulb_temperature_curve_name": {
                "field_name": "Minimum Design Wetbulb Temperature Curve Name",
                "field_type": "a"
            },
            "minimum_outside_air_wetbulb_temperature_curve_name": {
                "field_name": "Minimum Outside Air Wetbulb Temperature Curve Name",
                "field_type": "a"
            },
            "optimized_cond_entering_water_temperature_curve_name": {
                "field_name": "Optimized Cond Entering Water Temperature Curve Name",
                "field_type": "a"
            },
            "minimum_lift": {
                "field_name": "Minimum Lift",
                "field_type": "n"
            },
            "maximum_condenser_entering_water_temperature": {
                "field_name": "Maximum Condenser Entering Water Temperature",
                "field_type": "n"
            },
            "cooling_tower_design_inlet_air_wet_bulb_temperature": {
                "field_name": "Cooling Tower Design Inlet Air Wet-Bulb Temperature",
                "field_type": "n"
            },
            "setpoint_node_or_nodelist_name": {
                "field_name": "Setpoint Node or NodeList Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "control_variable",
            "default_condenser_entering_water_temperature_schedule_name",
            "minimum_design_wetbulb_temperature_curve_name",
            "minimum_outside_air_wetbulb_temperature_curve_name",
            "optimized_cond_entering_water_temperature_curve_name",
            "minimum_lift",
            "maximum_condenser_entering_water_temperature",
            "cooling_tower_design_inlet_air_wet_bulb_temperature",
            "setpoint_node_or_nodelist_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "control_variable",
                "default_condenser_entering_water_temperature_schedule_name",
                "minimum_design_wetbulb_temperature_curve_name",
                "minimum_outside_air_wetbulb_temperature_curve_name",
                "optimized_cond_entering_water_temperature_curve_name",
                "setpoint_node_or_nodelist_name"
            ]
        },
        "numerics": {
            "fields": [
                "minimum_lift",
                "maximum_condenser_entering_water_temperature",
                "cooling_tower_design_inlet_air_wet_bulb_temperature"
            ]
        }
    },
    "type": "object",
    "memo": "This setpoint manager uses one curve to determine the optimum condenser entering water temperature for a given timestep and two other curves to place boundary conditions on the setpoint value.",
    "min_fields": 10.0
}
```
