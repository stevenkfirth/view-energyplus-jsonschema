```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "node_1_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "AirflowNetworkNodeAndZoneNames"
                    ],
                    "note": "Enter the name of zone or AirflowNetwork Node."
                },
                "node_2_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "AirflowNetworkNodeAndZoneNames"
                    ],
                    "note": "Enter the name of zone or AirflowNetwork Node."
                },
                "component_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "AFNCoilNames",
                        "AFNHeatExchangerNames",
                        "AFNTerminalUnitNames",
                        "AirflowNetworkComponentNames",
                        "FansCVandOnOffandVAV"
                    ],
                    "note": "Enter the name of an AirflowNetwork component. A component is one of the following AirflowNetwork:Distribution:Component objects: Leak, LeakageRatio, Duct, ConstantVolumeFan, Coil, TerminalUnit, ConstantPressureDrop, or HeatExchanger."
                },
                "thermal_zone_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ],
                    "note": "Only used if component = AirflowNetwork:Distribution:Component:Duct The zone name is where AirflowNetwork:Distribution:Component:Duct is exposed. Leave this field blank if the duct conduction loss is ignored."
                }
            },
            "required": [
                "node_1_name",
                "node_2_name",
                "component_name"
            ]
        }
    },
    "group": "AirflowNetwork",
    "name": {
        "type": "string",
        "is_required": true,
        "note": "Enter a unique name for this object."
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "node_1_name": {
                "field_name": "Node 1 Name",
                "field_type": "a"
            },
            "node_2_name": {
                "field_name": "Node 2 Name",
                "field_type": "a"
            },
            "component_name": {
                "field_name": "Component Name",
                "field_type": "a"
            },
            "thermal_zone_name": {
                "field_name": "Thermal Zone Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "node_1_name",
            "node_2_name",
            "component_name",
            "thermal_zone_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "node_1_name",
                "node_2_name",
                "component_name",
                "thermal_zone_name"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "This object defines the connection between two nodes and a component.",
    "min_fields": 4.0
}
```
