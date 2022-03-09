```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "rated_effective_total_heat_rejection_rate": {
                    "type": "number",
                    "note": "Rating as per ARI 450 Be sure the rating corresponds to the correct refrigerant not used in calculations, only for identification and output",
                    "units": "W",
                    "exclusiveMinimum": 0.0
                },
                "rated_condensing_temperature": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "units": "C",
                    "note": "must correspond to rating given for total heat rejection effect"
                },
                "rated_subcooling_temperature_difference": {
                    "type": "number",
                    "default": 0.0,
                    "minimum": 0.0,
                    "units": "deltaC",
                    "note": "must correspond to rating given for total heat rejection effect"
                },
                "rated_water_inlet_temperature": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "units": "C",
                    "note": "must correspond to rating given for total heat rejection effect"
                },
                "water_inlet_node_name": {
                    "type": "string"
                },
                "water_outlet_node_name": {
                    "type": "string"
                },
                "water_cooled_loop_flow_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "ConstantFlow",
                        "VariableFlow"
                    ],
                    "default": "VariableFlow"
                },
                "water_outlet_temperature_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Applicable only when loop flow type is Variable Flow."
                },
                "water_design_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "note": "note required units must be converted from L/s as specified in ARI 450-2007 Applicable only when loop flow type is Constant Flow.",
                    "exclusiveMinimum": 0.0
                },
                "water_maximum_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "exclusiveMinimum": 0.0
                },
                "water_maximum_water_outlet_temperature": {
                    "type": "number",
                    "units": "C",
                    "minimum": 10.0,
                    "maximum": 60.0,
                    "default": 55.0
                },
                "water_minimum_water_inlet_temperature": {
                    "type": "number",
                    "units": "C",
                    "minimum": 10.0,
                    "maximum": 30.0,
                    "default": 10.0,
                    "note": "related to the minimum allowed refrigeration system condensing temperature"
                },
                "end_use_subcategory": {
                    "type": "string",
                    "note": "Any text may be used here to categorize the end-uses in the ABUPS End Uses by Subcategory table.",
                    "retaincase": true,
                    "default": "General"
                },
                "condenser_refrigerant_operating_charge_inventory": {
                    "type": "number",
                    "units": "kg",
                    "note": "optional input"
                },
                "condensate_receiver_refrigerant_inventory": {
                    "type": "number",
                    "units": "kg",
                    "note": "optional input"
                },
                "condensate_piping_refrigerant_inventory": {
                    "type": "number",
                    "units": "kg",
                    "note": "optional input"
                }
            },
            "required": [
                "rated_condensing_temperature",
                "rated_water_inlet_temperature"
            ]
        }
    },
    "group": "Refrigeration",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "DesuperHeatingCoilSources",
            "RefrigerationAllTypesCondenserNames",
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
            "rated_effective_total_heat_rejection_rate": {
                "field_name": "Rated Effective Total Heat Rejection Rate",
                "field_type": "n"
            },
            "rated_condensing_temperature": {
                "field_name": "Rated Condensing Temperature",
                "field_type": "n"
            },
            "rated_subcooling_temperature_difference": {
                "field_name": "Rated Subcooling Temperature Difference",
                "field_type": "n"
            },
            "rated_water_inlet_temperature": {
                "field_name": "Rated Water Inlet Temperature",
                "field_type": "n"
            },
            "water_inlet_node_name": {
                "field_name": "Water Inlet Node Name",
                "field_type": "a"
            },
            "water_outlet_node_name": {
                "field_name": "Water Outlet Node Name",
                "field_type": "a"
            },
            "water_cooled_loop_flow_type": {
                "field_name": "Water-Cooled Loop Flow Type",
                "field_type": "a"
            },
            "water_outlet_temperature_schedule_name": {
                "field_name": "Water Outlet Temperature Schedule Name",
                "field_type": "a"
            },
            "water_design_flow_rate": {
                "field_name": "Water Design Flow Rate",
                "field_type": "n"
            },
            "water_maximum_flow_rate": {
                "field_name": "Water Maximum Flow Rate",
                "field_type": "n"
            },
            "water_maximum_water_outlet_temperature": {
                "field_name": "Water Maximum Water Outlet Temperature",
                "field_type": "n"
            },
            "water_minimum_water_inlet_temperature": {
                "field_name": "Water Minimum Water Inlet Temperature",
                "field_type": "n"
            },
            "end_use_subcategory": {
                "field_name": "End-Use Subcategory",
                "field_type": "a"
            },
            "condenser_refrigerant_operating_charge_inventory": {
                "field_name": "Condenser Refrigerant Operating Charge Inventory",
                "field_type": "n"
            },
            "condensate_receiver_refrigerant_inventory": {
                "field_name": "Condensate Receiver Refrigerant Inventory",
                "field_type": "n"
            },
            "condensate_piping_refrigerant_inventory": {
                "field_name": "Condensate Piping Refrigerant Inventory",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "rated_effective_total_heat_rejection_rate",
            "rated_condensing_temperature",
            "rated_subcooling_temperature_difference",
            "rated_water_inlet_temperature",
            "water_inlet_node_name",
            "water_outlet_node_name",
            "water_cooled_loop_flow_type",
            "water_outlet_temperature_schedule_name",
            "water_design_flow_rate",
            "water_maximum_flow_rate",
            "water_maximum_water_outlet_temperature",
            "water_minimum_water_inlet_temperature",
            "end_use_subcategory",
            "condenser_refrigerant_operating_charge_inventory",
            "condensate_receiver_refrigerant_inventory",
            "condensate_piping_refrigerant_inventory"
        ],
        "alphas": {
            "fields": [
                "name",
                "water_inlet_node_name",
                "water_outlet_node_name",
                "water_cooled_loop_flow_type",
                "water_outlet_temperature_schedule_name",
                "end_use_subcategory"
            ]
        },
        "numerics": {
            "fields": [
                "rated_effective_total_heat_rejection_rate",
                "rated_condensing_temperature",
                "rated_subcooling_temperature_difference",
                "rated_water_inlet_temperature",
                "water_design_flow_rate",
                "water_maximum_flow_rate",
                "water_maximum_water_outlet_temperature",
                "water_minimum_water_inlet_temperature",
                "condenser_refrigerant_operating_charge_inventory",
                "condensate_receiver_refrigerant_inventory",
                "condensate_piping_refrigerant_inventory"
            ]
        }
    },
    "type": "object",
    "memo": "Water cooled condenser for a refrigeration system (Refrigeration:System)."
}
```
