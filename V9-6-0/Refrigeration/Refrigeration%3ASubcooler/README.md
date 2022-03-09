```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "subcooler_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "LiquidSuction",
                        "Mechanical"
                    ],
                    "default": "LiquidSuction",
                    "note": "plan to add ambient subcoolers at future time"
                },
                "liquid_suction_design_subcooling_temperature_difference": {
                    "type": "number",
                    "units": "deltaC",
                    "note": "Applicable only and required for liquid suction heat exchangers design liquid suction subcooling"
                },
                "design_liquid_inlet_temperature": {
                    "type": "number",
                    "units": "C",
                    "note": "design inlet temperature on liquid side Applicable only and required for liquid suction heat exchangers (LSHX)"
                },
                "design_vapor_inlet_temperature": {
                    "type": "number",
                    "units": "C",
                    "note": "design inlet temperature on vapor side Applicable only and required for liquid suction heat exchangers (LSHX) Design vapor inlet temperature must be less than or equal to the Liquid inlet design temp"
                },
                "capacity_providing_system": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "RefrigerationSystemNames"
                    ],
                    "note": "Name of the Detailed Refrigeration System providing cooling capacity Applicable only and required for mechanical subcoolers"
                },
                "outlet_control_temperature": {
                    "type": "number",
                    "units": "C",
                    "note": "Control Temperature Out for subcooled liquid Applicable only and required for mechanical subcoolers"
                }
            }
        }
    },
    "group": "Refrigeration",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "RefrigerationSubcoolerNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "subcooler_type": {
                "field_name": "Subcooler Type",
                "field_type": "a"
            },
            "liquid_suction_design_subcooling_temperature_difference": {
                "field_name": "Liquid Suction Design Subcooling Temperature Difference",
                "field_type": "n"
            },
            "design_liquid_inlet_temperature": {
                "field_name": "Design Liquid Inlet Temperature",
                "field_type": "n"
            },
            "design_vapor_inlet_temperature": {
                "field_name": "Design Vapor Inlet Temperature",
                "field_type": "n"
            },
            "capacity_providing_system": {
                "field_name": "Capacity-Providing System",
                "field_type": "a"
            },
            "outlet_control_temperature": {
                "field_name": "Outlet Control Temperature",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "subcooler_type",
            "liquid_suction_design_subcooling_temperature_difference",
            "design_liquid_inlet_temperature",
            "design_vapor_inlet_temperature",
            "capacity_providing_system",
            "outlet_control_temperature"
        ],
        "alphas": {
            "fields": [
                "name",
                "subcooler_type",
                "capacity_providing_system"
            ]
        },
        "numerics": {
            "fields": [
                "liquid_suction_design_subcooling_temperature_difference",
                "design_liquid_inlet_temperature",
                "design_vapor_inlet_temperature",
                "outlet_control_temperature"
            ]
        }
    },
    "type": "object",
    "memo": "Two types of subcoolers are modeled by the detailed refrigeration system. The liquid suction heat exchanger uses cool suction gas to subcool the hot condensate after it leaves the condenser and before it reaches the thermal expansion valve. A mechanical subcooler is used to transfer cooling capacity from one refrigeration system to another.",
    "min_fields": 5.0
}
```
