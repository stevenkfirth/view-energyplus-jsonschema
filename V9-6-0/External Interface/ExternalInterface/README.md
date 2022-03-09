```
{
    "ExternalInterface": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "name_of_external_interface": {
                        "type": "string",
                        "note": "Name of External Interface Currently, the only valid entries are PtolemyServer, FunctionalMockupUnitImport, and FunctionalMockupUnitExport.",
                        "enum": [
                            "FunctionalMockupUnitExport",
                            "FunctionalMockupUnitImport",
                            "PtolemyServer"
                        ]
                    }
                },
                "required": [
                    "name_of_external_interface"
                ]
            }
        },
        "group": "External Interface",
        "legacy_idd": {
            "field_info": {
                "name_of_external_interface": {
                    "field_name": "Name of External Interface",
                    "field_type": "a"
                }
            },
            "fields": [
                "name_of_external_interface"
            ],
            "alphas": {
                "fields": [
                    "name_of_external_interface"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "This object activates the external interface of EnergyPlus. If the object ExternalInterface is present, then all ExtnernalInterface:* objects will receive their values from the BCVTB interface or from FMUs at each zone time step. If this object is not present, then the values of these objects will be fixed at the value declared in the \"initial value\" field of the corresponding object, and a warning will be written to the EnergyPlus error file."
    }
}
```
