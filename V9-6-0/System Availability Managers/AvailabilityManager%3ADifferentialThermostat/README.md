```
{
    "AvailabilityManager:DifferentialThermostat": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "hot_node_name": {
                        "type": "string"
                    },
                    "cold_node_name": {
                        "type": "string"
                    },
                    "temperature_difference_on_limit": {
                        "type": "number",
                        "units": "deltaC"
                    },
                    "temperature_difference_off_limit": {
                        "type": "number",
                        "units": "deltaC",
                        "note": "Defaults to Temperature Difference On Limit."
                    }
                },
                "required": [
                    "hot_node_name",
                    "cold_node_name",
                    "temperature_difference_on_limit"
                ]
            }
        },
        "group": "System Availability Managers",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "SystemAvailabilityManagers"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "hot_node_name": {
                    "field_name": "Hot Node Name",
                    "field_type": "a"
                },
                "cold_node_name": {
                    "field_name": "Cold Node Name",
                    "field_type": "a"
                },
                "temperature_difference_on_limit": {
                    "field_name": "Temperature Difference On Limit",
                    "field_type": "n"
                },
                "temperature_difference_off_limit": {
                    "field_name": "Temperature Difference Off Limit",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "hot_node_name",
                "cold_node_name",
                "temperature_difference_on_limit",
                "temperature_difference_off_limit"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "hot_node_name",
                    "cold_node_name"
                ]
            },
            "numerics": {
                "fields": [
                    "temperature_difference_on_limit",
                    "temperature_difference_off_limit"
                ]
            }
        },
        "type": "object",
        "memo": "Overrides fan/pump schedules depending on temperature difference between two nodes."
    }
}
```
