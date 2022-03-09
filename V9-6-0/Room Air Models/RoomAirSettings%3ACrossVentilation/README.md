```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "zone_name": {
                    "type": "string",
                    "note": "Name of Zone being described. Any existing zone name",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "gain_distribution_schedule_name": {
                    "type": "string",
                    "note": "Distribution of the convective heat gains between the jet and recirculation zones. 0<= Accepted Value <= 1. In the CV model 1 means all convective gains in the jet region.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "airflow_region_used_for_thermal_comfort_evaluation": {
                    "type": "string",
                    "note": "Required field whenever thermal comfort is predicted defines Air temperature and Airflow velocity that will be used in the Fanger model conditions must refer to one of the two regions: jet or recirculation",
                    "enum": [
                        "Jet",
                        "Recirculation"
                    ]
                }
            },
            "required": [
                "zone_name",
                "gain_distribution_schedule_name"
            ]
        }
    },
    "group": "Room Air Models",
    "legacy_idd": {
        "field_info": {
            "zone_name": {
                "field_name": "Zone Name",
                "field_type": "a"
            },
            "gain_distribution_schedule_name": {
                "field_name": "Gain Distribution Schedule Name",
                "field_type": "a"
            },
            "airflow_region_used_for_thermal_comfort_evaluation": {
                "field_name": "Airflow Region Used for Thermal Comfort Evaluation",
                "field_type": "a"
            }
        },
        "fields": [
            "zone_name",
            "gain_distribution_schedule_name",
            "airflow_region_used_for_thermal_comfort_evaluation"
        ],
        "alphas": {
            "fields": [
                "zone_name",
                "gain_distribution_schedule_name",
                "airflow_region_used_for_thermal_comfort_evaluation"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "This UCSD Cross Ventilation Room Air Model provides a simple model for heat transfer and vertical temperature profile prediction in cross ventilated rooms. The model distinguishes two regions in the room, the main jet region and the recirculations, and predicts characteristic airflow velocities and average air temperatures. Used with RoomAirModelType = CrossVentilation."
}
```
