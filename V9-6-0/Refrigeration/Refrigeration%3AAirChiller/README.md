```
{
    "Refrigeration:AirChiller": {
        "patternProperties": {
            "^.*\\S.*$": {
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
                    "capacity_rating_type": {
                        "type": "string",
                        "note": "In each case, select the rating option that corresponds to the expected service conditions. For example, U.S. manufacturers quote a separate Unit Load Factor for wet or frosted coils. If the evaporating temperature is less than 0C, input the frosted coil value. Within the European convention, select SC1, 2, 3, 4, or 5 depending upon the expected evaporating temperature.",
                        "enum": [
                            "CapacityTotalSpecificConditions",
                            "EuropeanSC1NominalWet",
                            "EuropeanSC1Standard",
                            "EuropeanSC2NominalWet",
                            "EuropeanSC2Standard",
                            "EuropeanSC3NominalWet",
                            "EuropeanSC3Standard",
                            "EuropeanSC4NominalWet",
                            "EuropeanSC4Standard",
                            "EuropeanSC5NominalWet",
                            "EuropeanSC5Standard",
                            "FixedLinear",
                            "UnitLoadFactorSensibleOnly"
                        ]
                    },
                    "rated_unit_load_factor": {
                        "type": "number",
                        "units": "W/K",
                        "note": "The sensible cooling capacity in watts (W/C) at rated conditions. The value entered for this field must be greater than zero, with no default value. This value is only used if the Capacity Rating Type is UnitLoadFactorSensibleOnly. The value given must be based upon the difference between the chiller inlet and outlet air temperatures, not on the difference between the zone mean temperature and the outlet air temperature"
                    },
                    "rated_capacity": {
                        "type": "number",
                        "units": "W",
                        "note": "This value is only used if the Capacity Rating Type is NOT UnitLoadFactorSensibleOnly. For CapacityTotalSpecificConditions, this capacity includes both sensible and latent at the conditions given in the next two fields. Note that the European Standard ratings are sensible only and the European Nominal ratings include latent capacity as well. The value given here must correspond to the capacity rating type given previously"
                    },
                    "rated_relative_humidity": {
                        "type": "number",
                        "units": "percent",
                        "maximum": 100.0,
                        "default": 85.0,
                        "note": "This field is ONLY used if the Capacity Rating Type is CapacityTotalSpecificConditions and represents the relative humidity at rated conditions. The default is 85."
                    },
                    "rated_cooling_source_temperature": {
                        "type": "number",
                        "note": "If DXEvaporator, use evaporating temperature (saturated suction temperature) If BrineCoil, use Brine entering temperature used to set minimum suction pressure for DX systems and minimum brine temp for secondary systems",
                        "units": "C",
                        "minimum": -70.0,
                        "maximum": 40.0
                    },
                    "rated_temperature_difference_dt1": {
                        "type": "number",
                        "units": "deltaC",
                        "minimum": 0.0,
                        "maximum": 20.0,
                        "note": "The rated difference between the air entering the refrigeration chiller and the cooling source temperature in degC."
                    },
                    "maximum_temperature_difference_between_inlet_air_and_evaporating_temperature": {
                        "type": "number",
                        "units": "deltaC",
                        "minimum": 0.0,
                        "maximum": 25.0,
                        "note": "The maximum difference between the air entering the refrigeration chiller and the cooling source temperature in degC used to limit capacity during pull-down. defaults to 1.3 times the Rated Temperature Difference DT1"
                    },
                    "coil_material_correction_factor": {
                        "type": "number",
                        "units": "dimensionless",
                        "default": 1.0,
                        "note": "This is the manufacturer's correction factor for coil material corresponding to rating"
                    },
                    "refrigerant_correction_factor": {
                        "type": "number",
                        "units": "dimensionless",
                        "default": 1.0,
                        "note": "This is the manufacturer's correction factor for refrigerant corresponding to rating"
                    },
                    "capacity_correction_curve_type": {
                        "type": "string",
                        "note": "In each case, select the correction curve type that corresponds to the rating type. default LinearSHR60 unless Capacity Rating Type = CapacityTotalSpecificConditions",
                        "enum": [
                            "European",
                            "LinearSHR60",
                            "QuadraticSHR",
                            "TabularRHxDT1xTRoom"
                        ]
                    },
                    "capacity_correction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "TrivariateFunctions",
                            "UnivariateFunctions"
                        ],
                        "note": "Should be blank for LinearSHR60 correction curve type"
                    },
                    "shr60_correction_factor": {
                        "type": "number",
                        "units": "dimensionless",
                        "default": 1.48,
                        "maximum": 1.67,
                        "note": "only used when the capacity correction curve type is LinearSHR60"
                    },
                    "rated_total_heating_power": {
                        "type": "number",
                        "units": "W",
                        "note": "Include total for all heater power Do not include defrost heater power"
                    },
                    "heating_power_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Values will be used to multiply the total heating power Values in the schedule should be between 0.0 and 1.0 Defaults to always on if schedule name left blank."
                    },
                    "fan_speed_control_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Fixed",
                            "FixedLinear",
                            "TwoSpeed",
                            "VariableSpeed"
                        ],
                        "default": "Fixed"
                    },
                    "rated_fan_power": {
                        "type": "number",
                        "units": "W",
                        "default": 375.0,
                        "minimum": 0.0
                    },
                    "rated_air_flow": {
                        "type": "number",
                        "units": "m3/s"
                    },
                    "minimum_fan_air_flow_ratio": {
                        "type": "number",
                        "note": "Minimum air flow fraction through fan",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "default": 0.2
                    },
                    "defrost_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Electric",
                            "HotFluid",
                            "None",
                            "OffCycle"
                        ],
                        "default": "Electric",
                        "note": "HotFluid includes either hot gas defrost for a DX system or Hot Brine defrost if this walk in is cooled by brine from a secondary chiller"
                    },
                    "defrost_control_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "TemperatureTermination",
                            "TimeSchedule"
                        ],
                        "default": "TimeSchedule"
                    },
                    "defrost_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "The schedule values should be 0 (off) or 1 (on)"
                    },
                    "defrost_drip_down_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "The schedule values should be 0 (off) or 1 (on) The start time for each defrost period in this drip-down schedule should coincide with the start time for each defrost period in the defrost schedule (previous input field). The length of each defrost drip-down period must be greater than or equal to the corresponding defrost period specified in the defrost schedule. This extra time allows the melted frost to drip from the coil before refrigeration is restarted."
                    },
                    "defrost_power": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0,
                        "note": "needed for all defrost types except none and offcycle"
                    },
                    "temperature_termination_defrost_fraction_to_ice": {
                        "type": "number",
                        "units": "dimensionless",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0,
                        "note": "This is the portion of the defrost energy that is available to melt frost Needed only for defrost control type TemperatureTermination defaults to 0.7 for electric defrost and to 0.3 for hot fluid defrost"
                    },
                    "vertical_location": {
                        "type": "string",
                        "enum": [
                            "",
                            "Ceiling",
                            "Floor",
                            "Middle"
                        ],
                        "default": "Middle"
                    },
                    "average_refrigerant_charge_inventory": {
                        "type": "number",
                        "units": "kg",
                        "default": 0.0,
                        "note": "This value is only used if the Cooling Source Type is DXEvaporator"
                    }
                },
                "required": [
                    "capacity_rating_type",
                    "rated_cooling_source_temperature",
                    "rated_temperature_difference_dt1",
                    "rated_total_heating_power",
                    "rated_air_flow",
                    "defrost_schedule_name"
                ]
            }
        },
        "group": "Refrigeration",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "RefrigerationAirChillerNames",
                "RefrigerationCaseAndWalkInAndListNames",
                "RefrigerationCaseAndWalkInNames"
            ]
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
                "capacity_rating_type": {
                    "field_name": "Capacity Rating Type",
                    "field_type": "a"
                },
                "rated_unit_load_factor": {
                    "field_name": "Rated Unit Load Factor",
                    "field_type": "n"
                },
                "rated_capacity": {
                    "field_name": "Rated Capacity",
                    "field_type": "n"
                },
                "rated_relative_humidity": {
                    "field_name": "Rated Relative Humidity",
                    "field_type": "n"
                },
                "rated_cooling_source_temperature": {
                    "field_name": "Rated Cooling Source Temperature",
                    "field_type": "n"
                },
                "rated_temperature_difference_dt1": {
                    "field_name": "Rated Temperature Difference DT1",
                    "field_type": "n"
                },
                "maximum_temperature_difference_between_inlet_air_and_evaporating_temperature": {
                    "field_name": "Maximum Temperature Difference Between Inlet Air and Evaporating Temperature",
                    "field_type": "n"
                },
                "coil_material_correction_factor": {
                    "field_name": "Coil Material Correction Factor",
                    "field_type": "n"
                },
                "refrigerant_correction_factor": {
                    "field_name": "Refrigerant Correction Factor",
                    "field_type": "n"
                },
                "capacity_correction_curve_type": {
                    "field_name": "Capacity Correction Curve Type",
                    "field_type": "a"
                },
                "capacity_correction_curve_name": {
                    "field_name": "Capacity Correction Curve Name",
                    "field_type": "a"
                },
                "shr60_correction_factor": {
                    "field_name": "SHR60 Correction Factor",
                    "field_type": "n"
                },
                "rated_total_heating_power": {
                    "field_name": "Rated Total Heating Power",
                    "field_type": "n"
                },
                "heating_power_schedule_name": {
                    "field_name": "Heating Power Schedule Name",
                    "field_type": "a"
                },
                "fan_speed_control_type": {
                    "field_name": "Fan Speed Control Type",
                    "field_type": "a"
                },
                "rated_fan_power": {
                    "field_name": "Rated Fan Power",
                    "field_type": "n"
                },
                "rated_air_flow": {
                    "field_name": "Rated Air Flow",
                    "field_type": "n"
                },
                "minimum_fan_air_flow_ratio": {
                    "field_name": "Minimum Fan Air Flow Ratio",
                    "field_type": "n"
                },
                "defrost_type": {
                    "field_name": "Defrost Type",
                    "field_type": "a"
                },
                "defrost_control_type": {
                    "field_name": "Defrost Control Type",
                    "field_type": "a"
                },
                "defrost_schedule_name": {
                    "field_name": "Defrost Schedule Name",
                    "field_type": "a"
                },
                "defrost_drip_down_schedule_name": {
                    "field_name": "Defrost Drip-Down Schedule Name",
                    "field_type": "a"
                },
                "defrost_power": {
                    "field_name": "Defrost Power",
                    "field_type": "n"
                },
                "temperature_termination_defrost_fraction_to_ice": {
                    "field_name": "Temperature Termination Defrost Fraction to Ice",
                    "field_type": "n"
                },
                "vertical_location": {
                    "field_name": "Vertical Location",
                    "field_type": "a"
                },
                "average_refrigerant_charge_inventory": {
                    "field_name": "Average Refrigerant Charge Inventory",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "capacity_rating_type",
                "rated_unit_load_factor",
                "rated_capacity",
                "rated_relative_humidity",
                "rated_cooling_source_temperature",
                "rated_temperature_difference_dt1",
                "maximum_temperature_difference_between_inlet_air_and_evaporating_temperature",
                "coil_material_correction_factor",
                "refrigerant_correction_factor",
                "capacity_correction_curve_type",
                "capacity_correction_curve_name",
                "shr60_correction_factor",
                "rated_total_heating_power",
                "heating_power_schedule_name",
                "fan_speed_control_type",
                "rated_fan_power",
                "rated_air_flow",
                "minimum_fan_air_flow_ratio",
                "defrost_type",
                "defrost_control_type",
                "defrost_schedule_name",
                "defrost_drip_down_schedule_name",
                "defrost_power",
                "temperature_termination_defrost_fraction_to_ice",
                "vertical_location",
                "average_refrigerant_charge_inventory"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "capacity_rating_type",
                    "capacity_correction_curve_type",
                    "capacity_correction_curve_name",
                    "heating_power_schedule_name",
                    "fan_speed_control_type",
                    "defrost_type",
                    "defrost_control_type",
                    "defrost_schedule_name",
                    "defrost_drip_down_schedule_name",
                    "vertical_location"
                ]
            },
            "numerics": {
                "fields": [
                    "rated_unit_load_factor",
                    "rated_capacity",
                    "rated_relative_humidity",
                    "rated_cooling_source_temperature",
                    "rated_temperature_difference_dt1",
                    "maximum_temperature_difference_between_inlet_air_and_evaporating_temperature",
                    "coil_material_correction_factor",
                    "refrigerant_correction_factor",
                    "shr60_correction_factor",
                    "rated_total_heating_power",
                    "rated_fan_power",
                    "rated_air_flow",
                    "minimum_fan_air_flow_ratio",
                    "defrost_power",
                    "temperature_termination_defrost_fraction_to_ice",
                    "average_refrigerant_charge_inventory"
                ]
            }
        },
        "type": "object",
        "memo": "Works in conjunction with a refrigeration chiller set, compressor rack, a refrigeration system, or a refrigeration secondary system to simulate the performance of an air chiller, similar to one found in a refrigerated warehouse. Energy use for fans and heaters is modeled based on inputs for nominal power, schedules, and control type. The air chiller model accounts for the sensible and latent heat exchange with the surrounding environment.",
        "min_fields": 23.0
    }
}
```
