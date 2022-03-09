```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "water_quality_subcategory": {
                    "type": "string"
                },
                "maximum_capacity": {
                    "type": "number",
                    "units": "m3",
                    "ip-units": "gal",
                    "note": "Defaults to unlimited capacity."
                },
                "initial_volume": {
                    "type": "number",
                    "units": "m3",
                    "ip-units": "gal"
                },
                "design_in_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "note": "Defaults to unlimited flow."
                },
                "design_out_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "note": "Defaults to unlimited flow."
                },
                "overflow_destination": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "WaterStorageTankNames"
                    ],
                    "note": "If blank, overflow is discarded"
                },
                "type_of_supply_controlled_by_float_valve": {
                    "type": "string",
                    "enum": [
                        "GroundwaterWell",
                        "Mains",
                        "None",
                        "OtherTank"
                    ]
                },
                "float_valve_on_capacity": {
                    "type": "number",
                    "units": "m3",
                    "ip-units": "gal",
                    "note": "Lower range of target storage level e.g. float valve kicks on"
                },
                "float_valve_off_capacity": {
                    "type": "number",
                    "units": "m3",
                    "ip-units": "gal",
                    "note": "Upper range of target storage level e.g. float valve kicks off"
                },
                "backup_mains_capacity": {
                    "type": "number",
                    "units": "m3",
                    "ip-units": "gal",
                    "note": "Lower range of secondary target storage level used to keep tanks at a minimum level using mains water if well can't keep up"
                },
                "other_tank_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "WaterStorageTankNames"
                    ]
                },
                "water_thermal_mode": {
                    "type": "string",
                    "enum": [
                        "ScheduledTemperature",
                        "ThermalModel"
                    ]
                },
                "water_temperature_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "ambient_temperature_indicator": {
                    "type": "string",
                    "enum": [
                        "Outdoors",
                        "Schedule",
                        "Zone"
                    ]
                },
                "ambient_temperature_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "zone_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "tank_surface_area": {
                    "type": "number",
                    "units": "m2"
                },
                "tank_u_value": {
                    "type": "number",
                    "units": "W/m2-K"
                },
                "tank_outside_surface_material_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "MaterialName"
                    ]
                }
            },
            "required": [
                "water_temperature_schedule_name"
            ]
        }
    },
    "group": "Water Systems",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "WaterStorageTankNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "water_quality_subcategory": {
                "field_name": "Water Quality Subcategory",
                "field_type": "a"
            },
            "maximum_capacity": {
                "field_name": "Maximum Capacity",
                "field_type": "n"
            },
            "initial_volume": {
                "field_name": "Initial Volume",
                "field_type": "n"
            },
            "design_in_flow_rate": {
                "field_name": "Design In Flow Rate",
                "field_type": "n"
            },
            "design_out_flow_rate": {
                "field_name": "Design Out Flow Rate",
                "field_type": "n"
            },
            "overflow_destination": {
                "field_name": "Overflow Destination",
                "field_type": "a"
            },
            "type_of_supply_controlled_by_float_valve": {
                "field_name": "Type of Supply Controlled by Float Valve",
                "field_type": "a"
            },
            "float_valve_on_capacity": {
                "field_name": "Float Valve On Capacity",
                "field_type": "n"
            },
            "float_valve_off_capacity": {
                "field_name": "Float Valve Off Capacity",
                "field_type": "n"
            },
            "backup_mains_capacity": {
                "field_name": "Backup Mains Capacity",
                "field_type": "n"
            },
            "other_tank_name": {
                "field_name": "Other Tank Name",
                "field_type": "a"
            },
            "water_thermal_mode": {
                "field_name": "Water Thermal Mode",
                "field_type": "a"
            },
            "water_temperature_schedule_name": {
                "field_name": "Water Temperature Schedule Name",
                "field_type": "a"
            },
            "ambient_temperature_indicator": {
                "field_name": "Ambient Temperature Indicator",
                "field_type": "a"
            },
            "ambient_temperature_schedule_name": {
                "field_name": "Ambient Temperature Schedule Name",
                "field_type": "a"
            },
            "zone_name": {
                "field_name": "Zone Name",
                "field_type": "a"
            },
            "tank_surface_area": {
                "field_name": "Tank Surface Area",
                "field_type": "n"
            },
            "tank_u_value": {
                "field_name": "Tank U Value",
                "field_type": "n"
            },
            "tank_outside_surface_material_name": {
                "field_name": "Tank Outside Surface Material Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "water_quality_subcategory",
            "maximum_capacity",
            "initial_volume",
            "design_in_flow_rate",
            "design_out_flow_rate",
            "overflow_destination",
            "type_of_supply_controlled_by_float_valve",
            "float_valve_on_capacity",
            "float_valve_off_capacity",
            "backup_mains_capacity",
            "other_tank_name",
            "water_thermal_mode",
            "water_temperature_schedule_name",
            "ambient_temperature_indicator",
            "ambient_temperature_schedule_name",
            "zone_name",
            "tank_surface_area",
            "tank_u_value",
            "tank_outside_surface_material_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "water_quality_subcategory",
                "overflow_destination",
                "type_of_supply_controlled_by_float_valve",
                "other_tank_name",
                "water_thermal_mode",
                "water_temperature_schedule_name",
                "ambient_temperature_indicator",
                "ambient_temperature_schedule_name",
                "zone_name",
                "tank_outside_surface_material_name"
            ]
        },
        "numerics": {
            "fields": [
                "maximum_capacity",
                "initial_volume",
                "design_in_flow_rate",
                "design_out_flow_rate",
                "float_valve_on_capacity",
                "float_valve_off_capacity",
                "backup_mains_capacity",
                "tank_surface_area",
                "tank_u_value"
            ]
        }
    },
    "type": "object",
    "memo": "A water storage tank. If the building model is to include any on-site water collection, wells, or storing and reuse of graywater, then a WaterUse:Storage object is needed. Each WaterUse:Storage can serve as a central node and make connections to numerous sources of supply or numerous components with demand. If a maximum capacity is not specified, the tank is assumed to have unlimited capacity."
}
```
