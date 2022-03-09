```
{
    "SolarCollector:FlatPlate:Water": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "solarcollectorperformance_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "FlatPlateSolarCollectorParameters"
                        ]
                    },
                    "surface_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AllShadingAndHTSurfNames"
                        ]
                    },
                    "inlet_node_name": {
                        "type": "string"
                    },
                    "outlet_node_name": {
                        "type": "string"
                    },
                    "maximum_flow_rate": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "m3/s",
                        "ip-units": "gal/min"
                    }
                },
                "required": [
                    "solarcollectorperformance_name",
                    "surface_name",
                    "inlet_node_name",
                    "outlet_node_name"
                ]
            }
        },
        "group": "Solar Collectors",
        "name": {
            "type": "string",
            "is_required": true,
            "reference-class-name": [
                "validBranchEquipmentTypes",
                "validPlantEquipmentTypes"
            ],
            "reference": [
                "validBranchEquipmentNames",
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
                "solarcollectorperformance_name": {
                    "field_name": "SolarCollectorPerformance Name",
                    "field_type": "a"
                },
                "surface_name": {
                    "field_name": "Surface Name",
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
                "maximum_flow_rate": {
                    "field_name": "Maximum Flow Rate",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "solarcollectorperformance_name",
                "surface_name",
                "inlet_node_name",
                "outlet_node_name",
                "maximum_flow_rate"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "solarcollectorperformance_name",
                    "surface_name",
                    "inlet_node_name",
                    "outlet_node_name"
                ]
            },
            "numerics": {
                "fields": [
                    "maximum_flow_rate"
                ]
            }
        },
        "type": "object",
        "memo": "Flat plate water solar collector (single glazed, unglazed, or evacuated tube). Thermal and optical properties are taken from the referenced SolarCollectorPerformance:FlatPlate object. Collector tilt, azimuth, and gross area are taken from the referenced building surface or shading surface. The collector surface participates normally in all shading calculations."
    }
}
```
