```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "controller_list_name": {
                    "type": "string",
                    "note": "Enter the name of an AirLoopHVAC:ControllerList object or blank if this object is used in AirLoopHVAC:DedicatedOutdoorAirSystem.",
                    "data_type": "object_list",
                    "object_list": [
                        "ControllerLists"
                    ]
                },
                "outdoor_air_equipment_list_name": {
                    "type": "string",
                    "note": "Enter the name of an AirLoopHVAC:OutdoorAirSystem:EquipmentList object.",
                    "data_type": "object_list",
                    "object_list": [
                        "AirLoopOAEquipmentLists"
                    ]
                }
            },
            "required": [
                "outdoor_air_equipment_list_name"
            ]
        }
    },
    "group": "Air Distribution",
    "name": {
        "type": "string",
        "is_required": true,
        "reference-class-name": [
            "validBranchEquipmentTypes"
        ],
        "reference": [
            "validBranchEquipmentNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "controller_list_name": {
                "field_name": "Controller List Name",
                "field_type": "a"
            },
            "outdoor_air_equipment_list_name": {
                "field_name": "Outdoor Air Equipment List Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "controller_list_name",
            "outdoor_air_equipment_list_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "controller_list_name",
                "outdoor_air_equipment_list_name"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "Outdoor air subsystem for an AirLoopHVAC. Includes an outdoor air mixing box and optional outdoor air conditioning equipment such as heat recovery, preheat, and precool coils. From the perspective of the primary air loop the outdoor air system is treated as a single component.",
    "min_fields": 3.0
}
```
