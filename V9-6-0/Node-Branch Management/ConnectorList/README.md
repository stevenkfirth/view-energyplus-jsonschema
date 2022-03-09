```
{
    "ConnectorList": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "connector_1_object_type": {
                        "type": "string",
                        "enum": [
                            "Connector:Mixer",
                            "Connector:Splitter"
                        ]
                    },
                    "connector_1_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "PlantConnectors"
                        ]
                    },
                    "connector_2_object_type": {
                        "type": "string",
                        "enum": [
                            "Connector:Mixer",
                            "Connector:Splitter"
                        ]
                    },
                    "connector_2_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "PlantConnectors"
                        ]
                    }
                },
                "required": [
                    "connector_1_object_type",
                    "connector_1_name"
                ]
            }
        },
        "group": "Node-Branch Management",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "ConnectorLists"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "connector_1_object_type": {
                    "field_name": "Connector 1 Object Type",
                    "field_type": "a"
                },
                "connector_1_name": {
                    "field_name": "Connector 1 Name",
                    "field_type": "a"
                },
                "connector_2_object_type": {
                    "field_name": "Connector 2 Object Type",
                    "field_type": "a"
                },
                "connector_2_name": {
                    "field_name": "Connector 2 Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "connector_1_object_type",
                "connector_1_name",
                "connector_2_object_type",
                "connector_2_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "connector_1_object_type",
                    "connector_1_name",
                    "connector_2_object_type",
                    "connector_2_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "only two connectors allowed per loop if two entered, one must be Connector:Splitter and one must be Connector:Mixer"
    }
}
```
