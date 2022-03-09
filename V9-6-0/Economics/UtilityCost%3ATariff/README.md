```
{
    "UtilityCost:Tariff": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "output_meter_name": {
                        "type": "string",
                        "note": "The name of any standard meter or custom meter or but usually set to either Electricity:Facility or Gas:Facility",
                        "data_type": "external_list",
                        "external_list": [
                            "autoRDDmeter"
                        ]
                    },
                    "conversion_factor_choice": {
                        "type": "string",
                        "enum": [
                            "CCF",
                            "MCF",
                            "MJ",
                            "MMBtu",
                            "Therm",
                            "UserDefined",
                            "gal",
                            "kBtu",
                            "kWh",
                            "kgal",
                            "m3"
                        ],
                        "note": "A choice that allows several different predefined conversion factors to be used; otherwise user defined conversion factors are used as defined in the next two fields. If left blank m3 is used for water meters and kWh are used for all other meters."
                    },
                    "energy_conversion_factor": {
                        "type": "number",
                        "note": "Is a multiplier used to convert energy into the units specified by the utility in their tariff. If left blank it defaults to 1 (no conversion). This field should will be used only if Conversion Factor Choice is set to UserDefined. Within EnergyPlus energy always has units of J (joules). For conversion from J to kWh use the value of 0.0000002778. This is also used for all objects that reference the UtilityCost:Tariff."
                    },
                    "demand_conversion_factor": {
                        "type": "number",
                        "note": "Is a multiplier used to convert demand into the units specified by the utility in their tariff. If left blank it defaults to 1 (no conversion). This field should will be used only if Conversion Factor Choice is set to UserDefined. Within EnergyPlus demand always has units of J/s (joules/sec) which equivalent to W (watts). For conversion from W to kW use the value of 0.001. This is also used for all objects that reference the UtilityCost:Tariff."
                    },
                    "time_of_use_period_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "The name of the schedule that defines the time-of-use periods that occur each day. The values for the different variables are: 1 for Peak. 2 for Shoulder. 3 for OffPeak. 4 for MidPeak. The following variables are created automatically if these different periods are used in the schedule and include: TotalEnergy, TotalDemand, PeakEnergy, PeakDemand, ShoulderEnergy, ShoulderDemand, OffPeakEnergy, OffPeakDemand, MidPeakEnergy, MidPeakDemand Some special variables are created that include: PeakExceedsOffPeak, OffPeakExceedsPeak, PeakExceedsMidPeak, MidPeakExceedsPeak, PeakExceedsShoulder, ShoulderExceedsPeak, Others include: PeakAndShoulderEnergy, PeakAndShoulderDemand, PeakAndMidPeakEnergy, PeakAndMidPeakDemand, ShoulderAndOffPeakEnergy, ShoulderAndOffPeakDemand, PeakAndOffPeakEnergy, PeakAndOffPeakDemand, RealTimePriceCosts, AboveCustomerBaseCosts, BelowCustomerBaseCosts, AboveCustomerBaseEnergy, BelowCustomerBaseEnergy"
                    },
                    "season_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "The name of a schedule that defines the seasons. The schedule values are: 1 for Winter. 2 for Spring. 3 for Summer. 4 for Autumn. Variables are automatically created if a season schedule is used. These variables are set to 1 within the season and 0 for the months that are not in the season. The variables are: IsWinter, IsNotWinter, IsSpring, IsNotSpring, IsSummer, IsNotSummer, IsAutumn, IsNotAutumn."
                    },
                    "month_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "The name of the schedule that defines the billing periods of the year. Normally this entry is allowed to default and a schedule will be internally used that has the breaks between billing periods occurring at the same time as the breaks between months i.e. at midnight prior to the first day of the month. If other billing periods are used such as two month cycles or a single bill for an entire season such as some natural gas companies do in the summer then the month schedule may be used to redefine it. Make sure that the month schedule and season schedule are consistent otherwise an error will be issued."
                    },
                    "demand_window_length": {
                        "type": "string",
                        "enum": [
                            "Day",
                            "FullHour",
                            "HalfHour",
                            "QuarterHour",
                            "Week"
                        ],
                        "note": "The determination of demand can vary by utility. Some utilities use the peak instantaneous demand measured but most use a fifteen minute average demand or a one hour average demand. Some gas utilities measure demand as the use during the peak day or peak week."
                    },
                    "monthly_charge_or_variable_name": {
                        "note": "The fixed monthly service charge that many utilities have. The entry may be numeric and gets added to the ServiceCharges variable or if a variable name is entered here its values for each month are used.",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string"
                            }
                        ]
                    },
                    "minimum_monthly_charge_or_variable_name": {
                        "note": "The minimum total charge for the tariff or if a variable name is entered here its values for each month are used.",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string"
                            }
                        ]
                    },
                    "real_time_pricing_charge_schedule_name": {
                        "type": "string",
                        "note": "Used with real time pricing rates. The name of a schedule that contains the cost of energy for that particular time period of the year. Real time rates can be modeled using a charge schedule with the actual real time prices entered in the schedule.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "customer_baseline_load_schedule_name": {
                        "type": "string",
                        "note": "Used with real time pricing rates. The name of a schedule that contains the baseline energy use for the customer. Many real time rates apply the charges as a credit or debit only to the difference between the baseline use and the actual use.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "group_name": {
                        "type": "string",
                        "note": "The group name of the tariff such as distribution transmission supplier etc. If more than one tariff with the same group name is present and qualifies only the lowest cost tariff is used. Usually the group name field is left blank which results in all tariffs using the same meter variable being compared and the lowest cost one being selected."
                    },
                    "buy_or_sell": {
                        "type": "string",
                        "enum": [
                            "",
                            "BuyFromUtility",
                            "NetMetering",
                            "SellToUtility"
                        ],
                        "default": "BuyFromUtility",
                        "note": "Sets whether the tariff is used for buying selling or both to the utility. This should be allowed to default to buyFromUtility unless a power generation system is included in the building that may generate more power than the building needs during the year"
                    }
                },
                "required": [
                    "output_meter_name"
                ]
            }
        },
        "group": "Economics",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "UtilityCostTariffs"
            ],
            "note": "The name of the tariff. Tariffs are sometimes called rates. The name is used in identifying the output results and in associating all of the charges and other objects that make up a tariff."
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "output_meter_name": {
                    "field_name": "Output Meter Name",
                    "field_type": "a"
                },
                "conversion_factor_choice": {
                    "field_name": "Conversion Factor Choice",
                    "field_type": "a"
                },
                "energy_conversion_factor": {
                    "field_name": "Energy Conversion Factor",
                    "field_type": "n"
                },
                "demand_conversion_factor": {
                    "field_name": "Demand Conversion Factor",
                    "field_type": "n"
                },
                "time_of_use_period_schedule_name": {
                    "field_name": "Time of Use Period Schedule Name",
                    "field_type": "a"
                },
                "season_schedule_name": {
                    "field_name": "Season Schedule Name",
                    "field_type": "a"
                },
                "month_schedule_name": {
                    "field_name": "Month Schedule Name",
                    "field_type": "a"
                },
                "demand_window_length": {
                    "field_name": "Demand Window Length",
                    "field_type": "a"
                },
                "monthly_charge_or_variable_name": {
                    "field_name": "Monthly Charge or Variable Name",
                    "field_type": "a"
                },
                "minimum_monthly_charge_or_variable_name": {
                    "field_name": "Minimum Monthly Charge or Variable Name",
                    "field_type": "a"
                },
                "real_time_pricing_charge_schedule_name": {
                    "field_name": "Real Time Pricing Charge Schedule Name",
                    "field_type": "a"
                },
                "customer_baseline_load_schedule_name": {
                    "field_name": "Customer Baseline Load Schedule Name",
                    "field_type": "a"
                },
                "group_name": {
                    "field_name": "Group Name",
                    "field_type": "a"
                },
                "buy_or_sell": {
                    "field_name": "Buy Or Sell",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "output_meter_name",
                "conversion_factor_choice",
                "energy_conversion_factor",
                "demand_conversion_factor",
                "time_of_use_period_schedule_name",
                "season_schedule_name",
                "month_schedule_name",
                "demand_window_length",
                "monthly_charge_or_variable_name",
                "minimum_monthly_charge_or_variable_name",
                "real_time_pricing_charge_schedule_name",
                "customer_baseline_load_schedule_name",
                "group_name",
                "buy_or_sell"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "output_meter_name",
                    "conversion_factor_choice",
                    "time_of_use_period_schedule_name",
                    "season_schedule_name",
                    "month_schedule_name",
                    "demand_window_length",
                    "monthly_charge_or_variable_name",
                    "minimum_monthly_charge_or_variable_name",
                    "real_time_pricing_charge_schedule_name",
                    "customer_baseline_load_schedule_name",
                    "group_name",
                    "buy_or_sell"
                ]
            },
            "numerics": {
                "fields": [
                    "energy_conversion_factor",
                    "demand_conversion_factor"
                ]
            }
        },
        "type": "object",
        "memo": "Defines the name of a utility cost tariff, the type of tariff, and other details about the overall tariff. Each other object that is part of the tariff model references the tariff name. See UtilityCost:Charge:Simple, UtilityCost:Charge:Block, UtilityCost:Ratchet, UtilityCost:Qualify, UtilityCost:Variable and UtilityCost:Computation objects."
    }
}
```
