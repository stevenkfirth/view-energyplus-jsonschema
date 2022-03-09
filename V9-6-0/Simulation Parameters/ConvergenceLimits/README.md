```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "minimum_system_timestep": {
                    "type": "number",
                    "units": "minutes",
                    "note": "0 sets the minimum to the zone timestep (ref: Timestep) 1 is normal (ratchet down to 1 minute) setting greater than zone timestep (in minutes) will effectively set to zone timestep",
                    "minimum": 0.0,
                    "maximum": 60.0
                },
                "maximum_hvac_iterations": {
                    "type": "number",
                    "default": 20.0,
                    "minimum": 1.0
                },
                "minimum_plant_iterations": {
                    "type": "number",
                    "note": "Controls the minimum number of plant system solver iterations within a single HVAC iteration Larger values will increase runtime but might improve solution accuracy for complicated plant systems Complex plants include: several interconnected loops, heat recovery, thermal load following generators, etc.",
                    "default": 2.0,
                    "minimum": 1.0
                },
                "maximum_plant_iterations": {
                    "type": "number",
                    "note": "Controls the maximum number of plant system solver iterations within a single HVAC iteration Smaller values might decrease runtime but could decrease solution accuracy for complicated plant systems",
                    "default": 8.0,
                    "minimum": 2.0
                }
            }
        }
    },
    "group": "Simulation Parameters",
    "legacy_idd": {
        "field_info": {
            "minimum_system_timestep": {
                "field_name": "Minimum System Timestep",
                "field_type": "n"
            },
            "maximum_hvac_iterations": {
                "field_name": "Maximum HVAC Iterations",
                "field_type": "n"
            },
            "minimum_plant_iterations": {
                "field_name": "Minimum Plant Iterations",
                "field_type": "n"
            },
            "maximum_plant_iterations": {
                "field_name": "Maximum Plant Iterations",
                "field_type": "n"
            }
        },
        "fields": [
            "minimum_system_timestep",
            "maximum_hvac_iterations",
            "minimum_plant_iterations",
            "maximum_plant_iterations"
        ],
        "alphas": {
            "fields": []
        },
        "numerics": {
            "fields": [
                "minimum_system_timestep",
                "maximum_hvac_iterations",
                "minimum_plant_iterations",
                "maximum_plant_iterations"
            ]
        }
    },
    "type": "object",
    "maxProperties": 1,
    "memo": "Specifies limits on HVAC system simulation timesteps and iterations. This item is an advanced feature that should be used only with caution."
}
```
