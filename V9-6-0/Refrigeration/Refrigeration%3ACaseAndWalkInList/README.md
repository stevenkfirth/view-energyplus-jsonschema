```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "cases_and_walkins": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "case_or_walkin_name": {
                                "type": "string",
                                "note": "Enter the name of a Refrigeration:Case or Refrigeration:WalkIn object.",
                                "data_type": "object_list",
                                "object_list": [
                                    "RefrigerationCaseAndWalkInNames"
                                ]
                            }
                        },
                        "type": "object"
                    }
                }
            }
        }
    },
    "group": "Refrigeration",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "RefrigerationCaseAndWalkInAndListNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "case_or_walkin_name": {
                "field_name": "Case or WalkIn Name",
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
                "case_or_walkin_name"
            ]
        },
        "numerics": {
            "fields": []
        },
        "extensibles": [
            "case_or_walkin_name"
        ],
        "extension": "cases_and_walkins"
    },
    "type": "object",
    "memo": "Provides a list of all the refrigerated cases, walk in coolers, or air chillers cooled by a single refrigeration system. Note that the names of all cases, walk-ins ,air chillers, and CaseAndWalkInLists must be unique. That is, you cannot give a list the same name as one of list items. This list may contain a combination of case and walk-in names OR a list of air chiller names. Air chillers may not be included in any list that also includes cases or walk-ins.",
    "extensible_size": 1.0
}
```
