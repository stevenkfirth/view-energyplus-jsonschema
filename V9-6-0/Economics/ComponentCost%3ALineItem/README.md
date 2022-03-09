```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "type": {
                    "type": "string"
                },
                "line_item_type": {
                    "type": "string",
                    "enum": [
                        "Chiller:Electric",
                        "Coil:Cooling:DX",
                        "Coil:Cooling:DX:SingleSpeed",
                        "Coil:DX",
                        "Coil:Heating:Fuel",
                        "Construction",
                        "Daylighting:Controls",
                        "General",
                        "Generator:Photovoltaic",
                        "Lights",
                        "Shading:Zone:Detailed"
                    ],
                    "note": "extend choice-keys as Cases are added to code"
                },
                "item_name": {
                    "type": "string",
                    "note": "wildcard \"*\" is acceptable for some components"
                },
                "object_end_use_key": {
                    "type": "string",
                    "note": "not yet used"
                },
                "cost_per_each": {
                    "type": "number",
                    "units": "$"
                },
                "cost_per_area": {
                    "type": "number",
                    "units": "$/m2"
                },
                "cost_per_unit_of_output_capacity": {
                    "type": "number",
                    "units": "$/kW"
                },
                "cost_per_unit_of_output_capacity_per_cop": {
                    "type": "number",
                    "units": "$/kW",
                    "note": "The value is per change in COP."
                },
                "cost_per_volume": {
                    "type": "number",
                    "units": "$/m3"
                },
                "cost_per_volume_rate": {
                    "type": "number",
                    "units": "$/(m3/s)"
                },
                "cost_per_energy_per_temperature_difference": {
                    "type": "number",
                    "units": "$/(W/K)",
                    "note": "as in for use with UA sizing of Coils"
                },
                "quantity": {
                    "type": "number",
                    "units": "dimensionless",
                    "note": "optional for use with Cost per Each and \"General\" object Type"
                }
            },
            "required": [
                "line_item_type",
                "item_name"
            ]
        }
    },
    "group": "Economics",
    "name": {
        "type": "string"
    },
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "type": {
                "field_name": "Type",
                "field_type": "a"
            },
            "line_item_type": {
                "field_name": "Line Item Type",
                "field_type": "a"
            },
            "item_name": {
                "field_name": "Item Name",
                "field_type": "a"
            },
            "object_end_use_key": {
                "field_name": "Object End-Use Key",
                "field_type": "a"
            },
            "cost_per_each": {
                "field_name": "Cost per Each",
                "field_type": "n"
            },
            "cost_per_area": {
                "field_name": "Cost per Area",
                "field_type": "n"
            },
            "cost_per_unit_of_output_capacity": {
                "field_name": "Cost per Unit of Output Capacity",
                "field_type": "n"
            },
            "cost_per_unit_of_output_capacity_per_cop": {
                "field_name": "Cost per Unit of Output Capacity per COP",
                "field_type": "n"
            },
            "cost_per_volume": {
                "field_name": "Cost per Volume",
                "field_type": "n"
            },
            "cost_per_volume_rate": {
                "field_name": "Cost per Volume Rate",
                "field_type": "n"
            },
            "cost_per_energy_per_temperature_difference": {
                "field_name": "Cost per Energy per Temperature Difference",
                "field_type": "n"
            },
            "quantity": {
                "field_name": "Quantity",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "type",
            "line_item_type",
            "item_name",
            "object_end_use_key",
            "cost_per_each",
            "cost_per_area",
            "cost_per_unit_of_output_capacity",
            "cost_per_unit_of_output_capacity_per_cop",
            "cost_per_volume",
            "cost_per_volume_rate",
            "cost_per_energy_per_temperature_difference",
            "quantity"
        ],
        "alphas": {
            "fields": [
                "name",
                "type",
                "line_item_type",
                "item_name",
                "object_end_use_key"
            ]
        },
        "numerics": {
            "fields": [
                "cost_per_each",
                "cost_per_area",
                "cost_per_unit_of_output_capacity",
                "cost_per_unit_of_output_capacity_per_cop",
                "cost_per_volume",
                "cost_per_volume_rate",
                "cost_per_energy_per_temperature_difference",
                "quantity"
            ]
        }
    },
    "type": "object",
    "memo": "Each instance of this object creates a cost line item and will contribute to the total for a cost estimate."
}
```
