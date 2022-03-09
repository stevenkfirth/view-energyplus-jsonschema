```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "reports": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "report_name": {
                                "type": "string",
                                "enum": [
                                    "AdaptiveComfortSummary",
                                    "AirLoopComponentLoadSummary",
                                    "AirLoopSystemComponentEnergyUseMonthly",
                                    "AirLoopSystemComponentLoadsMonthly",
                                    "AirLoopSystemEnergyAndWaterUseMonthly",
                                    "AllMonthly",
                                    "AllSummary",
                                    "AllSummaryAndMonthly",
                                    "AllSummaryAndSizingPeriod",
                                    "AllSummaryMonthlyAndSizingPeriod",
                                    "AnnualBuildingUtilityPerformanceSummary",
                                    "AverageOutdoorConditionsMonthly",
                                    "BoilerReportMonthly",
                                    "CO2ResilienceSummary",
                                    "ChillerReportMonthly",
                                    "ClimaticDataSummary",
                                    "CoilReportMonthly",
                                    "CoilSizingDetails",
                                    "ComfortReportSimple55Monthly",
                                    "ComponentCostEconomicsSummary",
                                    "ComponentSizingSummary",
                                    "CondLoopDemandReportMonthly",
                                    "DXReportMonthly",
                                    "DaylightingReportMonthly",
                                    "DemandEndUseComponentsSummary",
                                    "EconomicResultSummary",
                                    "ElectricComponentsOfPeakDemandMonthly",
                                    "EndUseEnergyConsumptionCoalMonthly",
                                    "EndUseEnergyConsumptionDieselMonthly",
                                    "EndUseEnergyConsumptionElectricityMonthly",
                                    "EndUseEnergyConsumptionFuelOilMonthly",
                                    "EndUseEnergyConsumptionGasolineMonthly",
                                    "EndUseEnergyConsumptionNaturalGasMonthly",
                                    "EndUseEnergyConsumptionOtherFuelsMonthly",
                                    "EndUseEnergyConsumptionPropaneMonthly",
                                    "EnergyConsumptionCoalGasolineMonthly",
                                    "EnergyConsumptionDieselFuelOilMonthly",
                                    "EnergyConsumptionDistrictHeatingCoolingMonthly",
                                    "EnergyConsumptionElectricityGeneratedPropaneMonthly",
                                    "EnergyConsumptionElectricityNaturalGasMonthly",
                                    "EnergyConsumptionOtherFuelsMonthly",
                                    "EnergyMeters",
                                    "EnvelopeSummary",
                                    "EquipmentSummary",
                                    "FacilityComponentLoadSummary",
                                    "FanReportMonthly",
                                    "GeneratorReportMonthly",
                                    "HVACSizingSummary",
                                    "HeatEmissionsReportMonthly",
                                    "HeatEmissionsSummary",
                                    "InitializationSummary",
                                    "InputVerificationandResultsSummary",
                                    "LEEDSummary",
                                    "LifeCycleCostReport",
                                    "LightingSummary",
                                    "MechanicalVentilationLoadsMonthly",
                                    "ObjectCountSummary",
                                    "OccupantComfortDataSummaryMonthly",
                                    "OutdoorAirDetails",
                                    "OutdoorAirSummary",
                                    "OutdoorConditionsMaximumDewPointMonthly",
                                    "OutdoorConditionsMaximumDryBulbMonthly",
                                    "OutdoorConditionsMaximumWetBulbMonthly",
                                    "OutdoorConditionsMinimumDryBulbMonthly",
                                    "OutdoorGroundConditionsMonthly",
                                    "PeakEnergyEndUseCoalMonthly",
                                    "PeakEnergyEndUseDieselMonthly",
                                    "PeakEnergyEndUseElectricityPart1Monthly",
                                    "PeakEnergyEndUseElectricityPart2Monthly",
                                    "PeakEnergyEndUseFuelOilMonthly",
                                    "PeakEnergyEndUseGasolineMonthly",
                                    "PeakEnergyEndUseNaturalGasMonthly",
                                    "PeakEnergyEndUseOtherFuelsMonthly",
                                    "PeakEnergyEndUsePropaneMonthly",
                                    "PeakSpaceGainsMonthly",
                                    "PlantLoopDemandReportMonthly",
                                    "PumpReportMonthly",
                                    "SensibleHeatGainSummary",
                                    "SetpointsNotMetWithTemperaturesMonthly",
                                    "ShadingSummary",
                                    "SourceEnergyEndUseComponentsSummary",
                                    "SpaceGainComponentsAtCoolingPeakMonthly",
                                    "SpaceGainsMonthly",
                                    "Standard62.1Summary",
                                    "SurfaceShadowingSummary",
                                    "SystemSummary",
                                    "TariffReport",
                                    "ThermalResilienceSummary",
                                    "TowerReportMonthly",
                                    "UnglazedTranspiredSolarCollectorSummaryMonthly",
                                    "VisualResilienceSummary",
                                    "WaterHeaterReportMonthly",
                                    "WindowACReportMonthly",
                                    "WindowEnergyReportMonthly",
                                    "WindowEnergyZoneSummaryMonthly",
                                    "WindowReportMonthly",
                                    "WindowZoneSummaryMonthly",
                                    "ZoneComponentLoadSummary",
                                    "ZoneCoolingSummaryMonthly",
                                    "ZoneElectricSummaryMonthly",
                                    "ZoneHeatingSummaryMonthly",
                                    "ZoneTemperatureOscillationReportMonthly"
                                ]
                            }
                        },
                        "type": "object"
                    }
                }
            }
        }
    },
    "group": "Output Reporting",
    "legacy_idd": {
        "field_info": {
            "report_name": {
                "field_name": "Report Name",
                "field_type": "a"
            }
        },
        "fields": [],
        "alphas": {
            "fields": [],
            "extensions": [
                "report_name"
            ]
        },
        "numerics": {
            "fields": []
        },
        "extensibles": [
            "report_name"
        ],
        "extension": "reports"
    },
    "type": "object",
    "maxProperties": 1,
    "memo": "This object allows the user to call report types that are predefined and will appear with the other tabular reports. These predefined reports are sensitive to the OutputControl:Table:Style object and appear in the same files as the tabular reports. The entries for this object is a list of the predefined reports that should appear in the tabular report output file.",
    "extensible_size": 1.0
}
```
