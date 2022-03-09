```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "fluid_to_radiant_surface_heat_transfer_model": {
                    "type": "string",
                    "note": "This parameter identifies how the heat transfer between fluid being circulated through the radiant system and the radiant system (slab) is modeled. ConvectionOnly means that only convection between the fluid and the inside surface of the pipe is modeled using a conventional equation for flow inside a pipe. ISOStandard models convection between the fluid and the inside of of the pipe and conduction through the pipe material using equations specific to ISO Standard 11855-2.",
                    "enum": [
                        "",
                        "ConvectionOnly",
                        "ISOStandard"
                    ],
                    "default": "ConvectionOnly"
                },
                "hydronic_tubing_inside_diameter": {
                    "type": "number",
                    "units": "m",
                    "exclusiveMinimum": 0.0,
                    "default": 0.013,
                    "ip-units": "in"
                },
                "hydronic_tubing_outside_diameter": {
                    "type": "number",
                    "units": "m",
                    "exclusiveMinimum": 0.0,
                    "default": 0.016,
                    "ip-units": "in"
                },
                "hydronic_tubing_conductivity": {
                    "type": "number",
                    "note": "Conductivity of the tubing/piping material",
                    "units": "W/m-K",
                    "exclusiveMinimum": 0.0,
                    "default": 0.35
                },
                "temperature_control_type": {
                    "type": "string",
                    "note": "Temperature used to control system",
                    "enum": [
                        "",
                        "MeanAirTemperature",
                        "MeanRadiantTemperature",
                        "OperativeTemperature",
                        "OutdoorDryBulbTemperature",
                        "OutdoorWetBulbTemperature",
                        "RunningMeanOutdoorDryBulbTemperature",
                        "SurfaceFaceTemperature",
                        "SurfaceInteriorTemperature"
                    ],
                    "default": "MeanAirTemperature"
                },
                "running_mean_outdoor_dry_bulb_temperature_weighting_factor": {
                    "type": "number",
                    "note": "this is the weighting factor in the equation that calculate the running mean outdoor dry-bulb temperature as a weighted average of the previous day\u00e2\u20ac\u2122s running mean outdoor dry-bulb temperature and the previous day\u00e2\u20ac\u2122s average outdoor dry-bulb temperature this value is only used by EnergyPlus when the user elects to use the RunningMeanOutdoorDryBulbTemperature control type",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.8
                },
                "motor_efficiency": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.9
                },
                "fraction_of_motor_inefficiencies_to_fluid_stream": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0
                },
                "condensation_control_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "Off",
                        "SimpleOff",
                        "VariableOff"
                    ],
                    "default": "SimpleOff"
                },
                "condensation_control_dewpoint_offset": {
                    "type": "number",
                    "units": "C",
                    "default": 1.0
                },
                "changeover_delay_time_period_schedule": {
                    "type": "string",
                    "note": "Changeover delay schedule name for this system. Schedule value <= 0 allows changeover with no delay The schedule values are interpretted as hours. If this field is blank, the system allows changeover with no delay",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                }
            }
        }
    },
    "group": "Zone HVAC Radiative/Convective Units",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "RadiantDesignObject"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "fluid_to_radiant_surface_heat_transfer_model": {
                "field_name": "Fluid to Radiant Surface Heat Transfer Model",
                "field_type": "a"
            },
            "hydronic_tubing_inside_diameter": {
                "field_name": "Hydronic Tubing Inside Diameter",
                "field_type": "n"
            },
            "hydronic_tubing_outside_diameter": {
                "field_name": "Hydronic Tubing Outside Diameter",
                "field_type": "n"
            },
            "hydronic_tubing_conductivity": {
                "field_name": "Hydronic Tubing Conductivity",
                "field_type": "n"
            },
            "temperature_control_type": {
                "field_name": "Temperature Control Type",
                "field_type": "a"
            },
            "running_mean_outdoor_dry_bulb_temperature_weighting_factor": {
                "field_name": "Running Mean Outdoor Dry-Bulb Temperature Weighting Factor",
                "field_type": "n"
            },
            "motor_efficiency": {
                "field_name": "Motor Efficiency",
                "field_type": "n"
            },
            "fraction_of_motor_inefficiencies_to_fluid_stream": {
                "field_name": "Fraction of Motor Inefficiencies to Fluid Stream",
                "field_type": "n"
            },
            "condensation_control_type": {
                "field_name": "Condensation Control Type",
                "field_type": "a"
            },
            "condensation_control_dewpoint_offset": {
                "field_name": "Condensation Control Dewpoint Offset",
                "field_type": "n"
            },
            "changeover_delay_time_period_schedule": {
                "field_name": "Changeover Delay Time Period Schedule",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "fluid_to_radiant_surface_heat_transfer_model",
            "hydronic_tubing_inside_diameter",
            "hydronic_tubing_outside_diameter",
            "hydronic_tubing_conductivity",
            "temperature_control_type",
            "running_mean_outdoor_dry_bulb_temperature_weighting_factor",
            "motor_efficiency",
            "fraction_of_motor_inefficiencies_to_fluid_stream",
            "condensation_control_type",
            "condensation_control_dewpoint_offset",
            "changeover_delay_time_period_schedule"
        ],
        "alphas": {
            "fields": [
                "name",
                "fluid_to_radiant_surface_heat_transfer_model",
                "temperature_control_type",
                "condensation_control_type",
                "changeover_delay_time_period_schedule"
            ]
        },
        "numerics": {
            "fields": [
                "hydronic_tubing_inside_diameter",
                "hydronic_tubing_outside_diameter",
                "hydronic_tubing_conductivity",
                "running_mean_outdoor_dry_bulb_temperature_weighting_factor",
                "motor_efficiency",
                "fraction_of_motor_inefficiencies_to_fluid_stream",
                "condensation_control_dewpoint_offset"
            ]
        }
    },
    "type": "object",
    "min_fields": 11.0
}
```
