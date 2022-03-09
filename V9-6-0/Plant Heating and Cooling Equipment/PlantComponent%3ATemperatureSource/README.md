```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "inlet_node": {
                    "type": "string",
                    "note": "Name of the source inlet node"
                },
                "outlet_node": {
                    "type": "string",
                    "note": "Name of the source outlet node"
                },
                "design_volume_flow_rate": {
                    "units": "m3/s",
                    "note": "The design volumetric flow rate for this source",
                    "ip-units": "gal/min",
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
                "temperature_specification_type": {
                    "type": "string",
                    "enum": [
                        "Constant",
                        "Scheduled"
                    ]
                },
                "source_temperature": {
                    "type": "number",
                    "units": "C",
                    "note": "Used if Temperature Specification Type = Constant"
                },
                "source_temperature_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "units": "C",
                    "note": "Used if Temperature Specification Type = Scheduled"
                }
            },
            "required": [
                "inlet_node",
                "outlet_node",
                "design_volume_flow_rate"
            ]
        }
    },
    "group": "Plant Heating and Cooling Equipment",
    "name": {
        "type": "string",
        "is_required": true,
        "note": "Component Name",
        "reference-class-name": [
            "validBranchEquipmentTypes",
            "validCondenserEquipmentTypes",
            "validPlantEquipmentTypes"
        ],
        "reference": [
            "validBranchEquipmentNames",
            "validCondenserEquipmentNames",
            "validPlantEquipmentNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "inlet_node": {
                "field_name": "Inlet Node",
                "field_type": "a"
            },
            "outlet_node": {
                "field_name": "Outlet Node",
                "field_type": "a"
            },
            "design_volume_flow_rate": {
                "field_name": "Design Volume Flow Rate",
                "field_type": "n"
            },
            "temperature_specification_type": {
                "field_name": "Temperature Specification Type",
                "field_type": "a"
            },
            "source_temperature": {
                "field_name": "Source Temperature",
                "field_type": "n"
            },
            "source_temperature_schedule_name": {
                "field_name": "Source Temperature Schedule Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "inlet_node",
            "outlet_node",
            "design_volume_flow_rate",
            "temperature_specification_type",
            "source_temperature",
            "source_temperature_schedule_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "inlet_node",
                "outlet_node",
                "temperature_specification_type",
                "source_temperature_schedule_name"
            ]
        },
        "numerics": {
            "fields": [
                "design_volume_flow_rate",
                "source_temperature"
            ]
        }
    },
    "type": "object",
    "memo": "Simulates an object of pre-determined (constant or scheduled) source temperature The object introduces fluid into the plant loop at the specified temperature and at the same flow rate as the fluid enters the component Fluid entering the component vanishes equivalent to the relief air in an air system"
}
```
