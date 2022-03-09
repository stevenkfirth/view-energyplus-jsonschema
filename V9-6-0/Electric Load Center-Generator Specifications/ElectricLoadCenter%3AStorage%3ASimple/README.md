```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "availability_schedule_name": {
                    "type": "string",
                    "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "zone_name": {
                    "type": "string",
                    "note": "Enter name of zone to receive storage losses as heat if blank then storage is assumed to be outdoors",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "radiative_fraction_for_zone_heat_gains": {
                    "type": "number",
                    "maximum": 1.0,
                    "minimum": 0.0
                },
                "nominal_energetic_efficiency_for_charging": {
                    "type": "number",
                    "maximum": 1.0,
                    "minimum": 0.0
                },
                "nominal_discharging_energetic_efficiency": {
                    "type": "number",
                    "maximum": 1.0,
                    "minimum": 0.0
                },
                "maximum_storage_capacity": {
                    "type": "number",
                    "units": "J"
                },
                "maximum_power_for_discharging": {
                    "type": "number",
                    "units": "W"
                },
                "maximum_power_for_charging": {
                    "type": "number",
                    "units": "W"
                },
                "initial_state_of_charge": {
                    "type": "number",
                    "units": "J"
                }
            }
        }
    },
    "group": "Electric Load Center-Generator Specifications",
    "name": {
        "type": "string",
        "reference": [
            "ElecStorageList"
        ]
    },
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
            "zone_name": {
                "field_name": "Zone Name",
                "field_type": "a"
            },
            "radiative_fraction_for_zone_heat_gains": {
                "field_name": "Radiative Fraction for Zone Heat Gains",
                "field_type": "n"
            },
            "nominal_energetic_efficiency_for_charging": {
                "field_name": "Nominal Energetic Efficiency for Charging",
                "field_type": "n"
            },
            "nominal_discharging_energetic_efficiency": {
                "field_name": "Nominal Discharging Energetic Efficiency",
                "field_type": "n"
            },
            "maximum_storage_capacity": {
                "field_name": "Maximum Storage Capacity",
                "field_type": "n"
            },
            "maximum_power_for_discharging": {
                "field_name": "Maximum Power for Discharging",
                "field_type": "n"
            },
            "maximum_power_for_charging": {
                "field_name": "Maximum Power for Charging",
                "field_type": "n"
            },
            "initial_state_of_charge": {
                "field_name": "Initial State of Charge",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "zone_name",
            "radiative_fraction_for_zone_heat_gains",
            "nominal_energetic_efficiency_for_charging",
            "nominal_discharging_energetic_efficiency",
            "maximum_storage_capacity",
            "maximum_power_for_discharging",
            "maximum_power_for_charging",
            "initial_state_of_charge"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "zone_name"
            ]
        },
        "numerics": {
            "fields": [
                "radiative_fraction_for_zone_heat_gains",
                "nominal_energetic_efficiency_for_charging",
                "nominal_discharging_energetic_efficiency",
                "maximum_storage_capacity",
                "maximum_power_for_discharging",
                "maximum_power_for_charging",
                "initial_state_of_charge"
            ]
        }
    },
    "type": "object",
    "memo": "Used to model storage of electricity in an electric load center. This is a simple model that does not attempt to represent any of the characteristics of a real storage device such as a battery. The type of power, AC or DC, depends on the configuration chosen as the Electrical Buss Type in the ElectricLoadCenter:Distribution object."
}
```
