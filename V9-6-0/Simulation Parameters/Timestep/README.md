```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "number_of_timesteps_per_hour": {
                    "type": "number",
                    "note": "Number in hour: normal validity 4 to 60: 6 suggested Must be evenly divisible into 60 Allowable values include 1, 2, 3, 4, 5, 6, 10, 12, 15, 20, 30, and 60 Normal 6 is minimum as lower values may cause inaccuracies A minimum value of 20 is suggested for both ConductionFiniteDifference and CombinedHeatAndMoistureFiniteElement surface heat balance algorithms A minimum of 12 is suggested for simulations involving a Vegetated Roof (Material:RoofVegetation).",
                    "default": 6.0,
                    "minimum": 1.0,
                    "maximum": 60.0
                }
            }
        }
    },
    "group": "Simulation Parameters",
    "legacy_idd": {
        "field_info": {
            "number_of_timesteps_per_hour": {
                "field_name": "Number of Timesteps per Hour",
                "field_type": "n"
            }
        },
        "fields": [
            "number_of_timesteps_per_hour"
        ],
        "alphas": {
            "fields": []
        },
        "numerics": {
            "fields": [
                "number_of_timesteps_per_hour"
            ]
        }
    },
    "type": "object",
    "maxProperties": 1,
    "memo": "Specifies the \"basic\" timestep for the simulation. The value entered here is also known as the Zone Timestep. This is used in the Zone Heat Balance Model calculation as the driving timestep for heat transfer and load calculations.",
    "format": "singleLine"
}
```
