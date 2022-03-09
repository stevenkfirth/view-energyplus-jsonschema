```
{
    "AirflowNetwork:Distribution:Node": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "component_name_or_node_name": {
                        "type": "string",
                        "note": "Designates node names defined in another object. The node name may occur in air branches. Enter a node name to represent a node already defined in an air loop. Leave this field blank if the Node or Object Type field below is entered as AirLoopHVAC:ZoneMixer, AirLoopHVAC:ZoneSplitter, AirLoopHVAC:OutdoorAirSystem, or Other."
                    },
                    "component_object_type_or_node_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "AirLoopHVAC:OutdoorAirSystem",
                            "AirLoopHVAC:ZoneMixer",
                            "AirLoopHVAC:ZoneSplitter",
                            "OAMixerOutdoorAirStreamNode",
                            "Other",
                            "OutdoorAir:Node",
                            "OutdoorAir:NodeList"
                        ],
                        "default": "Other",
                        "note": "Designates Node type for the Node or Component Name defined in the field above. AirLoopHVAC:ZoneMixer -- Represents a AirLoopHVAC:ZoneMixer object. AirLoopHVAC:ZoneSplitter -- Represents a AirLoopHVAC:ZoneSplitter object. AirLoopHVAC:OutdoorAirSystem -- Represents an AirLoopHVAC:OutdoorAirSystem object. OAMixerOutdoorAirStreamNode -- Represents an external node used in the OutdoorAir:Mixer OutdoorAir:NodeList -- Represents an external node when a heat exchanger is used before the OutdoorAir:Mixer OutdoorAir:Node -- Represents an external node when a heat exchanger is used before the OutdoorAir:Mixer Other -- none of the above, the Node name already defined in the previous field is part of an air loop."
                    },
                    "node_height": {
                        "type": "number",
                        "units": "m",
                        "default": 0.0,
                        "note": "Enter the reference height used to calculate the relative pressure."
                    }
                }
            }
        },
        "group": "AirflowNetwork",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "AirflowNetworkNodeAndZoneNames"
            ],
            "note": "Enter a unique name for this object."
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "component_name_or_node_name": {
                    "field_name": "Component Name or Node Name",
                    "field_type": "a"
                },
                "component_object_type_or_node_type": {
                    "field_name": "Component Object Type or Node Type",
                    "field_type": "a"
                },
                "node_height": {
                    "field_name": "Node Height",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "component_name_or_node_name",
                "component_object_type_or_node_type",
                "node_height"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "component_name_or_node_name",
                    "component_object_type_or_node_type"
                ]
            },
            "numerics": {
                "fields": [
                    "node_height"
                ]
            }
        },
        "type": "object",
        "memo": "This object represents an air distribution node in the AirflowNetwork model.",
        "min_fields": 4.0
    }
}
```
