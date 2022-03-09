```
{
    "ThermalStorage:Ice:Simple": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "ice_storage_type": {
                        "type": "string",
                        "note": "IceOnCoilInternal = Ice-on-Coil, internal melt IceOnCoilExternal = Ice-on-Coil, external melt",
                        "enum": [
                            "IceOnCoilExternal",
                            "IceOnCoilInternal"
                        ]
                    },
                    "capacity": {
                        "type": "number",
                        "units": "GJ",
                        "ip-units": "ton-hrs"
                    },
                    "inlet_node_name": {
                        "type": "string"
                    },
                    "outlet_node_name": {
                        "type": "string"
                    }
                },
                "required": [
                    "ice_storage_type",
                    "capacity",
                    "inlet_node_name",
                    "outlet_node_name"
                ]
            }
        },
        "group": "Water Heaters and Thermal Storage",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "IceThermalStorageEquipment",
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
                "ice_storage_type": {
                    "field_name": "Ice Storage Type",
                    "field_type": "a"
                },
                "capacity": {
                    "field_name": "Capacity",
                    "field_type": "n"
                },
                "inlet_node_name": {
                    "field_name": "Inlet Node Name",
                    "field_type": "a"
                },
                "outlet_node_name": {
                    "field_name": "Outlet Node Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "ice_storage_type",
                "capacity",
                "inlet_node_name",
                "outlet_node_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "ice_storage_type",
                    "inlet_node_name",
                    "outlet_node_name"
                ]
            },
            "numerics": {
                "fields": [
                    "capacity"
                ]
            }
        },
        "type": "object",
        "memo": "This ice storage model is a simplified model It requires a setpoint placed on the Chilled Water Side Outlet Node It should be placed in the chilled water supply side outlet branch followed by a pipe. Use the PlantEquipmentOperation:ComponentSetpoint plant operation scheme.",
        "min_fields": 5.0
    }
}
```
