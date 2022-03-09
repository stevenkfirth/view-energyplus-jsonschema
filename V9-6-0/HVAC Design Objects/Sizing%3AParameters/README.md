```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "heating_sizing_factor": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 1.0
                },
                "cooling_sizing_factor": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 1.0
                },
                "timesteps_in_averaging_window": {
                    "type": "number",
                    "note": "blank => set the timesteps in averaging window to Number of Timesteps per Hour resulting in a 1 hour averaging window default is number of timesteps for 1 hour averaging window",
                    "minimum": 1.0
                }
            }
        }
    },
    "group": "HVAC Design Objects",
    "legacy_idd": {
        "field_info": {
            "heating_sizing_factor": {
                "field_name": "Heating Sizing Factor",
                "field_type": "n"
            },
            "cooling_sizing_factor": {
                "field_name": "Cooling Sizing Factor",
                "field_type": "n"
            },
            "timesteps_in_averaging_window": {
                "field_name": "Timesteps in Averaging Window",
                "field_type": "n"
            }
        },
        "fields": [
            "heating_sizing_factor",
            "cooling_sizing_factor",
            "timesteps_in_averaging_window"
        ],
        "alphas": {
            "fields": []
        },
        "numerics": {
            "fields": [
                "heating_sizing_factor",
                "cooling_sizing_factor",
                "timesteps_in_averaging_window"
            ]
        }
    },
    "type": "object",
    "maxProperties": 1,
    "memo": "Specifies global heating and cooling sizing factors/ratios. These ratios are applied at the zone level to all of the zone heating and cooling loads and air flow rates. Then these new loads and air flow rates are used to calculate the system level flow rates and capacities and are used in all component sizing calculations. Specifies the width (in load timesteps) of a moving average window which is used to smooth the peak load across more than one timestep.",
    "min_fields": 1.0
}
```
