```
{
    "FaultModel:TemperatureSensorOffset:CoilSupplyAir": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "availability_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "severity_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "coil_object_type": {
                        "type": "string",
                        "note": "Enter the type of the coil affected",
                        "enum": [
                            "AirLoopHVAC:UnitarySystem",
                            "Coil:Cooling:Water",
                            "Coil:Cooling:Water:Detailedgeometry",
                            "Coil:Heating:Desuperheater",
                            "Coil:Heating:Electric",
                            "Coil:Heating:Gas",
                            "Coil:Heating:Steam",
                            "Coil:Heating:Water",
                            "CoilSystem:Cooling:DX",
                            "CoilSystem:Heating:DX"
                        ]
                    },
                    "coil_object_name": {
                        "type": "string",
                        "note": "Enter the name of the coil affected",
                        "data_type": "object_list",
                        "object_list": [
                            "CoolingCoilName",
                            "CoolingCoilSystemName",
                            "DOAToZonalUnit",
                            "HeatingCoilName",
                            "HeatingCoilSystemName",
                            "HeatingCoilsDesuperheater",
                            "HeatingCoilsElectricMultiStage",
                            "HeatingCoilsGasMultiStage"
                        ]
                    },
                    "water_coil_controller_name": {
                        "type": "string",
                        "note": "Enter the name of controller for the water coil affected Required for water coils",
                        "data_type": "object_list",
                        "object_list": [
                            "WaterCoilControllers"
                        ]
                    },
                    "reference_sensor_offset": {
                        "type": "number",
                        "exclusiveMinimum": -10.0,
                        "exclusiveMaximum": 10.0,
                        "default": 0.0,
                        "units": "deltaC"
                    }
                },
                "required": [
                    "coil_object_type",
                    "coil_object_name"
                ]
            }
        },
        "group": "Operational Faults",
        "name": {
            "type": "string",
            "note": "Enter the name of the fault",
            "is_required": true
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "availability_schedule_name": {
                    "field_name": "Availability Schedule Name",
                    "field_type": "a"
                },
                "severity_schedule_name": {
                    "field_name": "Severity Schedule Name",
                    "field_type": "a"
                },
                "coil_object_type": {
                    "field_name": "Coil Object Type",
                    "field_type": "a"
                },
                "coil_object_name": {
                    "field_name": "Coil Object Name",
                    "field_type": "a"
                },
                "water_coil_controller_name": {
                    "field_name": "Water Coil Controller Name",
                    "field_type": "a"
                },
                "reference_sensor_offset": {
                    "field_name": "Reference Sensor Offset",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "severity_schedule_name",
                "coil_object_type",
                "coil_object_name",
                "water_coil_controller_name",
                "reference_sensor_offset"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "severity_schedule_name",
                    "coil_object_type",
                    "coil_object_name",
                    "water_coil_controller_name"
                ]
            },
            "numerics": {
                "fields": [
                    "reference_sensor_offset"
                ]
            }
        },
        "type": "object",
        "memo": "This object describes fault of coil supply air temperature sensor offset",
        "min_fields": 6.0
    }
}
```
