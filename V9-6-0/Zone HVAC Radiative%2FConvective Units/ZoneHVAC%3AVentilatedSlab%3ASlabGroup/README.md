```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "data": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "zone_name": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "ZoneNames"
                                ]
                            },
                            "surface_name": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "RadiantSurfaceNames"
                                ]
                            },
                            "core_diameter_for_surface": {
                                "type": "number",
                                "minimum": 0.0,
                                "units": "m"
                            },
                            "core_length_for_surface": {
                                "type": "number",
                                "minimum": 0.0,
                                "units": "m"
                            },
                            "core_numbers_for_surface": {
                                "type": "number",
                                "minimum": 0.0
                            },
                            "slab_inlet_node_name_for_surface": {
                                "type": "string"
                            },
                            "slab_outlet_node_name_for_surface": {
                                "type": "string"
                            }
                        },
                        "type": "object",
                        "required": [
                            "core_diameter_for_surface",
                            "core_length_for_surface",
                            "core_numbers_for_surface",
                            "slab_inlet_node_name_for_surface",
                            "slab_outlet_node_name_for_surface",
                            "surface_name",
                            "zone_name"
                        ]
                    }
                }
            }
        }
    },
    "group": "Zone HVAC Radiative/Convective Units",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "VentSlabGroupNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "zone_name": {
                "field_name": "Zone Name",
                "field_type": "a"
            },
            "surface_name": {
                "field_name": "Surface Name",
                "field_type": "a"
            },
            "core_diameter_for_surface": {
                "field_name": "Core Diameter for Surface",
                "field_type": "n"
            },
            "core_length_for_surface": {
                "field_name": "Core Length for Surface",
                "field_type": "n"
            },
            "core_numbers_for_surface": {
                "field_name": "Core Numbers for Surface",
                "field_type": "n"
            },
            "slab_inlet_node_name_for_surface": {
                "field_name": "Slab Inlet Node Name for Surface",
                "field_type": "a"
            },
            "slab_outlet_node_name_for_surface": {
                "field_name": "Slab Outlet Node Name for Surface",
                "field_type": "a"
            }
        },
        "fields": [
            "name"
        ],
        "alphas": {
            "fields": [
                "name"
            ],
            "extensions": [
                "zone_name",
                "surface_name",
                "slab_inlet_node_name_for_surface",
                "slab_outlet_node_name_for_surface"
            ]
        },
        "numerics": {
            "fields": [],
            "extensions": [
                "core_diameter_for_surface",
                "core_length_for_surface",
                "core_numbers_for_surface"
            ]
        },
        "extensibles": [
            "zone_name",
            "surface_name",
            "core_diameter_for_surface",
            "core_length_for_surface",
            "core_numbers_for_surface",
            "slab_inlet_node_name_for_surface",
            "slab_outlet_node_name_for_surface"
        ],
        "extension": "data"
    },
    "type": "object",
    "memo": "This is used to allow the coordinate control of several ventilated slab system surfaces. Note that the flow fractions must sum up to 1.0. The number of surfaces can be expanded beyond 10, if necessary, by adding more groups to the end of the list",
    "extensible_size": 7.0
}
```
