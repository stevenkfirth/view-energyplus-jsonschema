```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "month": {
                    "type": "number",
                    "minimum": 1.0,
                    "maximum": 12.0
                },
                "day_of_month": {
                    "type": "number",
                    "minimum": 1.0,
                    "maximum": 31.0,
                    "note": "must be valid for Month field"
                },
                "day_type": {
                    "type": "string",
                    "note": "Day Type selects the schedules appropriate for this design day",
                    "enum": [
                        "CustomDay1",
                        "CustomDay2",
                        "Friday",
                        "Holiday",
                        "Monday",
                        "Saturday",
                        "SummerDesignDay",
                        "Sunday",
                        "Thursday",
                        "Tuesday",
                        "Wednesday",
                        "WinterDesignDay"
                    ]
                },
                "maximum_dry_bulb_temperature": {
                    "type": "number",
                    "note": "This field is required when field \"Dry-Bulb Temperature Range Modifier Type\" is not \"TemperatureProfileSchedule\".",
                    "units": "C",
                    "minimum": -90.0,
                    "maximum": 70.0
                },
                "daily_dry_bulb_temperature_range": {
                    "type": "number",
                    "note": "Must still produce appropriate maximum dry-bulb (within range) This field is not needed if Dry-Bulb Temperature Range Modifier Type is \"delta\".",
                    "units": "deltaC",
                    "minimum": 0.0,
                    "default": 0.0
                },
                "dry_bulb_temperature_range_modifier_type": {
                    "type": "string",
                    "note": "Type of modifier to the dry-bulb temperature calculated for the timestep",
                    "enum": [
                        "",
                        "DefaultMultipliers",
                        "DifferenceSchedule",
                        "MultiplierSchedule",
                        "TemperatureProfileSchedule"
                    ],
                    "default": "DefaultMultipliers"
                },
                "dry_bulb_temperature_range_modifier_day_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "DayScheduleNames"
                    ],
                    "note": "Only used when previous field is \"MultiplierSchedule\", \"DifferenceSchedule\" or \"TemperatureProfileSchedule\". For type \"MultiplierSchedule\"  the hour/time interval values should specify the fraction (0-1) of the dry-bulb temperature range to be subtracted from the maximum dry-bulb temperature for each timestep in the day For type \"DifferenceSchedule\" the values should specify a number to be subtracted from the maximum dry-bulb temperature for each timestep in the day. Note that numbers in the difference schedule cannot be negative as that would result in a higher maximum than the maximum previously specified. For type \"TemperatureProfileSchedule\" the values should specify the actual dry-bulb temperature for each timestep in the day."
                },
                "humidity_condition_type": {
                    "type": "string",
                    "note": "values/schedules indicated here and in subsequent fields create the humidity values in the 24 hour design day conditions profile.",
                    "enum": [
                        "",
                        "DewPoint",
                        "Enthalpy",
                        "HumidityRatio",
                        "RelativeHumiditySchedule",
                        "WetBulb",
                        "WetBulbProfileDefaultMultipliers",
                        "WetBulbProfileDifferenceSchedule",
                        "WetBulbProfileMultiplierSchedule"
                    ],
                    "default": "WetBulb"
                },
                "wetbulb_or_dewpoint_at_maximum_dry_bulb": {
                    "type": "number",
                    "note": "Wetbulb or dewpoint temperature coincident with the maximum temperature. Required only if field Humidity Condition Type is \"Wetbulb\", \"Dewpoint\", \"WetBulbProfileMultiplierSchedule\", \"WetBulbProfileDifferenceSchedule\", or \"WetBulbProfileDefaultMultipliers\"",
                    "units": "C"
                },
                "humidity_condition_day_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "DayScheduleNames"
                    ],
                    "note": "Only used when Humidity Condition Type is \"RelativeHumiditySchedule\", \"WetBulbProfileMultiplierSchedule\", or \"WetBulbProfileDifferenceSchedule\" For type \"RelativeHumiditySchedule\", the hour/time interval values should specify relative humidity (percent) from 0.0 to 100.0. For type \"WetBulbProfileMultiplierSchedule\" the hour/time interval values should specify the fraction (0-1) of the wet-bulb temperature range to be subtracted from the maximum wet-bulb temperature for each timestep in the day (units = Fraction) For type \"WetBulbProfileDifferenceSchedule\" the values should specify a number to be subtracted from the maximum wet-bulb temperature for each timestep in the day. (units = deltaC)"
                },
                "humidity_ratio_at_maximum_dry_bulb": {
                    "type": "number",
                    "note": "Humidity ratio coincident with the maximum temperature (constant humidity ratio throughout day). Required only if field Humidity Condition Type is \"HumidityRatio\".",
                    "units": "kgWater/kgDryAir"
                },
                "enthalpy_at_maximum_dry_bulb": {
                    "type": "number",
                    "note": "Enthalpy coincident with the maximum temperature. Required only if field Humidity Condition Type is \"Enthalpy\".",
                    "units": "J/kg"
                },
                "daily_wet_bulb_temperature_range": {
                    "type": "number",
                    "units": "deltaC",
                    "note": "Required only if Humidity Condition Type = \"WetbulbProfileMultiplierSchedule\" or \"WetBulbProfileDefaultMultipliers\""
                },
                "barometric_pressure": {
                    "type": "number",
                    "note": "This field's value is also checked against the calculated \"standard barometric pressure\" for the location. If out of range (>10%) or blank, then is replaced by standard value.",
                    "units": "Pa",
                    "minimum": 31000.0,
                    "maximum": 120000.0,
                    "ip-units": "inHg"
                },
                "wind_speed": {
                    "type": "number",
                    "units": "m/s",
                    "minimum": 0.0,
                    "maximum": 40.0,
                    "ip-units": "miles/hr"
                },
                "wind_direction": {
                    "type": "number",
                    "units": "deg",
                    "minimum": 0.0,
                    "maximum": 360.0,
                    "note": "North=0.0 East=90.0 0 and 360 are the same direction."
                },
                "rain_indicator": {
                    "type": "string",
                    "note": "Yes is raining (all day), No is not raining",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "No"
                },
                "snow_indicator": {
                    "type": "string",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "No",
                    "note": "Yes is Snow on Ground, No is no Snow on Ground"
                },
                "daylight_saving_time_indicator": {
                    "type": "string",
                    "note": "Yes -- use schedules modified for Daylight Saving Time Schedules. No - do not use schedules modified for Daylight Saving Time Schedules",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "No"
                },
                "solar_model_indicator": {
                    "type": "string",
                    "enum": [
                        "",
                        "ASHRAEClearSky",
                        "ASHRAETau",
                        "ASHRAETau2017",
                        "Schedule",
                        "ZhangHuang"
                    ],
                    "default": "ASHRAEClearSky"
                },
                "beam_solar_day_schedule_name": {
                    "type": "string",
                    "note": "if Solar Model Indicator = Schedule, then beam schedule name (for day)",
                    "data_type": "object_list",
                    "object_list": [
                        "DayScheduleNames"
                    ]
                },
                "diffuse_solar_day_schedule_name": {
                    "type": "string",
                    "note": "if Solar Model Indicator = Schedule, then diffuse schedule name (for day)",
                    "data_type": "object_list",
                    "object_list": [
                        "DayScheduleNames"
                    ]
                },
                "ashrae_clear_sky_optical_depth_for_beam_irradiance_taub_": {
                    "type": "number",
                    "units": "dimensionless",
                    "note": "Required if Solar Model Indicator = ASHRAETau or ASHRAETau2017 ASHRAETau2017 solar model can be used with 2013 and 2017 HOF matching taub",
                    "minimum": 0.0,
                    "maximum": 1.2,
                    "default": 0.0
                },
                "ashrae_clear_sky_optical_depth_for_diffuse_irradiance_taud_": {
                    "type": "number",
                    "units": "dimensionless",
                    "note": "Required if Solar Model Indicator = ASHRAETau or ASHRAETau2017 ASHRAETau2017 solar model can be used with 2013 and 2017 HOF matching taud",
                    "minimum": 0.0,
                    "maximum": 3.0,
                    "default": 0.0
                },
                "sky_clearness": {
                    "type": "number",
                    "note": "Used if Sky Model Indicator = ASHRAEClearSky or ZhangHuang 0.0 is totally unclear, 1.0 is totally clear",
                    "minimum": 0.0,
                    "maximum": 1.2,
                    "default": 0.0
                },
                "maximum_number_warmup_days": {
                    "type": "number",
                    "note": "If used this design day will be run with a custom limit on the maximum number of days that are repeated for warmup. Limiting the number of warmup days can improve run time."
                },
                "begin_environment_reset_mode": {
                    "type": "string",
                    "note": "If used this can control if you want the thermal history to be reset at the beginning of the design day. When using a series of similiar design days, this field can be used to retain warmup state from the previous design day.",
                    "enum": [
                        "",
                        "FullResetAtBeginEnvironment",
                        "SuppressAllBeginEnvironmentResets"
                    ],
                    "default": "FullResetAtBeginEnvironment"
                }
            },
            "required": [
                "month",
                "day_of_month",
                "day_type",
                "wind_speed",
                "wind_direction"
            ]
        }
    },
    "group": "Location and Climate",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "RunPeriodsAndDesignDays"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "month": {
                "field_name": "Month",
                "field_type": "n"
            },
            "day_of_month": {
                "field_name": "Day of Month",
                "field_type": "n"
            },
            "day_type": {
                "field_name": "Day Type",
                "field_type": "a"
            },
            "maximum_dry_bulb_temperature": {
                "field_name": "Maximum Dry-Bulb Temperature",
                "field_type": "n"
            },
            "daily_dry_bulb_temperature_range": {
                "field_name": "Daily Dry-Bulb Temperature Range",
                "field_type": "n"
            },
            "dry_bulb_temperature_range_modifier_type": {
                "field_name": "Dry-Bulb Temperature Range Modifier Type",
                "field_type": "a"
            },
            "dry_bulb_temperature_range_modifier_day_schedule_name": {
                "field_name": "Dry-Bulb Temperature Range Modifier Day Schedule Name",
                "field_type": "a"
            },
            "humidity_condition_type": {
                "field_name": "Humidity Condition Type",
                "field_type": "a"
            },
            "wetbulb_or_dewpoint_at_maximum_dry_bulb": {
                "field_name": "Wetbulb or DewPoint at Maximum Dry-Bulb",
                "field_type": "n"
            },
            "humidity_condition_day_schedule_name": {
                "field_name": "Humidity Condition Day Schedule Name",
                "field_type": "a"
            },
            "humidity_ratio_at_maximum_dry_bulb": {
                "field_name": "Humidity Ratio at Maximum Dry-Bulb",
                "field_type": "n"
            },
            "enthalpy_at_maximum_dry_bulb": {
                "field_name": "Enthalpy at Maximum Dry-Bulb",
                "field_type": "n"
            },
            "daily_wet_bulb_temperature_range": {
                "field_name": "Daily Wet-Bulb Temperature Range",
                "field_type": "n"
            },
            "barometric_pressure": {
                "field_name": "Barometric Pressure",
                "field_type": "n"
            },
            "wind_speed": {
                "field_name": "Wind Speed",
                "field_type": "n"
            },
            "wind_direction": {
                "field_name": "Wind Direction",
                "field_type": "n"
            },
            "rain_indicator": {
                "field_name": "Rain Indicator",
                "field_type": "a"
            },
            "snow_indicator": {
                "field_name": "Snow Indicator",
                "field_type": "a"
            },
            "daylight_saving_time_indicator": {
                "field_name": "Daylight Saving Time Indicator",
                "field_type": "a"
            },
            "solar_model_indicator": {
                "field_name": "Solar Model Indicator",
                "field_type": "a"
            },
            "beam_solar_day_schedule_name": {
                "field_name": "Beam Solar Day Schedule Name",
                "field_type": "a"
            },
            "diffuse_solar_day_schedule_name": {
                "field_name": "Diffuse Solar Day Schedule Name",
                "field_type": "a"
            },
            "ashrae_clear_sky_optical_depth_for_beam_irradiance_taub_": {
                "field_name": "ASHRAE Clear Sky Optical Depth for Beam Irradiance (taub)",
                "field_type": "n"
            },
            "ashrae_clear_sky_optical_depth_for_diffuse_irradiance_taud_": {
                "field_name": "ASHRAE Clear Sky Optical Depth for Diffuse Irradiance (taud)",
                "field_type": "n"
            },
            "sky_clearness": {
                "field_name": "Sky Clearness",
                "field_type": "n"
            },
            "maximum_number_warmup_days": {
                "field_name": "Maximum Number Warmup Days",
                "field_type": "n"
            },
            "begin_environment_reset_mode": {
                "field_name": "Begin Environment Reset Mode",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "month",
            "day_of_month",
            "day_type",
            "maximum_dry_bulb_temperature",
            "daily_dry_bulb_temperature_range",
            "dry_bulb_temperature_range_modifier_type",
            "dry_bulb_temperature_range_modifier_day_schedule_name",
            "humidity_condition_type",
            "wetbulb_or_dewpoint_at_maximum_dry_bulb",
            "humidity_condition_day_schedule_name",
            "humidity_ratio_at_maximum_dry_bulb",
            "enthalpy_at_maximum_dry_bulb",
            "daily_wet_bulb_temperature_range",
            "barometric_pressure",
            "wind_speed",
            "wind_direction",
            "rain_indicator",
            "snow_indicator",
            "daylight_saving_time_indicator",
            "solar_model_indicator",
            "beam_solar_day_schedule_name",
            "diffuse_solar_day_schedule_name",
            "ashrae_clear_sky_optical_depth_for_beam_irradiance_taub_",
            "ashrae_clear_sky_optical_depth_for_diffuse_irradiance_taud_",
            "sky_clearness",
            "maximum_number_warmup_days",
            "begin_environment_reset_mode"
        ],
        "alphas": {
            "fields": [
                "name",
                "day_type",
                "dry_bulb_temperature_range_modifier_type",
                "dry_bulb_temperature_range_modifier_day_schedule_name",
                "humidity_condition_type",
                "humidity_condition_day_schedule_name",
                "rain_indicator",
                "snow_indicator",
                "daylight_saving_time_indicator",
                "solar_model_indicator",
                "beam_solar_day_schedule_name",
                "diffuse_solar_day_schedule_name",
                "begin_environment_reset_mode"
            ]
        },
        "numerics": {
            "fields": [
                "month",
                "day_of_month",
                "maximum_dry_bulb_temperature",
                "daily_dry_bulb_temperature_range",
                "wetbulb_or_dewpoint_at_maximum_dry_bulb",
                "humidity_ratio_at_maximum_dry_bulb",
                "enthalpy_at_maximum_dry_bulb",
                "daily_wet_bulb_temperature_range",
                "barometric_pressure",
                "wind_speed",
                "wind_direction",
                "ashrae_clear_sky_optical_depth_for_beam_irradiance_taub_",
                "ashrae_clear_sky_optical_depth_for_diffuse_irradiance_taud_",
                "sky_clearness",
                "maximum_number_warmup_days"
            ]
        }
    },
    "type": "object",
    "memo": "The design day object creates the parameters for the program to create the 24 hour weather profile that can be used for sizing as well as running to test the other simulation parameters. Parameters in this include a date (month and day), a day type (which uses the appropriate schedules for either sizing or simple tests), min/max temperatures, wind speeds, and solar radiation values."
}
```
