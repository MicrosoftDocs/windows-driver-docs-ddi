---
UID: TP:powermeter
ms.assetid: 87d19931-d859-3aff-b7ce-1b0060d965a5
ms.author: windowsdriverdev
ms.date: 01/18/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Power metering


Overview of the Power metering technology.

To develop Power metering, you need these headers:

 * [hpmi.h](..\hpmi\index.md)
 * [pmi.h](..\pmi\index.md)

For the programming guide, see [Power metering](https://docs.microsoft.com/en-us/windows-hardware/drivers/powermeter).

## Structures

| Title   | Description   |
| ---- |:---- |
| [_HPMI_BATTERY_UTILIZATION_HINT structure](..\hpmi\ns-hpmi-_hpmi_battery_utilization_hint.md) | This hint indicates if the OEM Battery Manager should attempt to save as much charge as possible in the non-hot swappable batteries (i.e. |
| [_HPMI_QUERY_CAPABILITIES structure](..\hpmi\ns-hpmi-_hpmi_query_capabilities.md) | The HPMI_QUERY_CAPABILITIES structure is used to query HPMI capabilities. |
| [_HPMI_QUERY_CAPABILITIES_RESPONSE structure](..\hpmi\ns-hpmi-_hpmi_query_capabilities_response.md) | HPMI_QUERY_CAPABILITIES_RESPONSE is a structure used to return information about software defined batteries (SDB). |
| [_PMI_BUDGETING_CONFIGURATION structure](..\pmi\ns-pmi-_pmi_budgeting_configuration.md) | The PMI_BUDGETING_CONFIGURATION structure contains information about the current power budget of a power meter. A power budget defines how much power that the system can consume from the set of power supplies monitored by the power meter. |
| [_PMI_CAPABILITIES structure](..\pmi\ns-pmi-_pmi_capabilities.md) | The PMI_CAPABILITIES structure contains information about the power metering and budgeting capabilities of a power meter. |
| [_PMI_CONFIGURATION structure](..\pmi\ns-pmi-_pmi_configuration.md) | The PMI_CONFIGURATION structure contains information about the current power metering and budgeting configuration of a power meter. |
| [_PMI_EVENT structure](..\pmi\ns-pmi-_pmi_event.md) | The PMI_EVENT structure contains information about a power metering and budgeting event that is signaled through the Power Meter Interface (PMI). |
| [_PMI_MEASUREMENT_CONFIGURATION structure](..\pmi\ns-pmi-_pmi_measurement_configuration.md) | The PMI_MEASUREMENT_CONFIGURATION structure contains information about the current power measurement configuration of a power meter. |
| [_PMI_MEASUREMENT_DATA structure](..\pmi\ns-pmi-_pmi_measurement_data.md) | The PMI_MEASUREMENT_DATA structure contains the current power measurement that is collected by a power meter. |
| [_PMI_METERED_HARDWARE_INFORMATION structure](..\pmi\ns-pmi-_pmi_metered_hardware_information.md) | The PMI_METERED_HARDWARE_INFORMATION structure contains information about one or more power supplies that are monitored by the power meter. |
| [_PMI_REPORTED_CAPABILITIES structure](..\pmi\ns-pmi-_pmi_reported_capabilities.md) | The PMI_REPORTED_CAPABILITIES structure contains information about the type of power metering and budgeting capabilities a power meter supports. Additionally, this structure contains asset information about the power meter itself. |
| [_PMI_THRESHOLD_CONFIGURATION structure](..\pmi\ns-pmi-_pmi_threshold_configuration.md) | The PMI_THRESHOLD_CONFIGURATION structure contains information about the threshold configuration of the power meter. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [PMI_CAPABILITIES_TYPE enumeration](..\pmi\ne-pmi-pmi_capabilities_type.md) | The PMI_CAPABILITIES_TYPE enumeration defines the type of capabilities data that is referenced by the Capability member of the PMI_CAPABILITIES structure. |
| [PMI_CONFIGURATION_TYPE enumeration](..\pmi\ne-pmi-pmi_configuration_type.md) | The PMI_CONFIGURATION_TYPE enumeration defines the type of PMI configuration data that is referenced by the Configuration member of the PMI_CONFIGURATION structure. |
| [PMI_EVENT_TYPE enumeration](..\pmi\ne-pmi-pmi_event_type.md) | The PMI_EVENT_TYPE enumeration defines the type of PMI power meter event that is returned through the successful completion of an IOCTL_PMI_REGISTER_EVENT_NOTIFY request. |
| [PMI_MEASUREMENT_TYPE enumeration](..\pmi\ne-pmi-pmi_measurement_type.md) | The PMI_MEASUREMENT_TYPE enumeration defines the source of the PMI measurement data. |
| [PMI_MEASUREMENT_UNIT enumeration](..\pmi\ne-pmi-pmi_measurement_unit.md) | The PMI_MEASUREMENT_UNIT enumeration defines the units of the PMI measurement data. |
| [_HPMI_HINT_BOOL enumeration](..\hpmi\ne-hpmi-_hpmi_hint_bool.md) | Boolean type value used to track availability of HPMI hint data. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_HPMI_BATTERY_UTILIZATION_HINT IOCTL](..\hpmi\ni-hpmi-ioctl_hpmi_battery_utilization_hint.md) | Set command sent to HPMI to provide battery utilization hints. |
| [IOCTL_HPMI_QUERY_CAPABILITIES IOCTL](..\hpmi\ni-hpmi-ioctl_hpmi_query_capabilities.md) | The IOCTL_HPMI_QUERY_CAPABILITIES command is sent to query features supported by HPMI and Windows services requested by HPMI. Windows will issue this IOCL to HPMI once after a new HPMI driver instance is discovered. |
| [IOCTL_PMI_GET_CAPABILITIES IOCTL](..\pmi\ni-pmi-ioctl_pmi_get_capabilities.md) | The IOCTL_PMI_GET_CAPABILITIES request obtains the capability and asset information about a power meter. |
| [IOCTL_PMI_GET_CONFIGURATION IOCTL](..\pmi\ni-pmi-ioctl_pmi_get_configuration.md) | The IOCTL_PMI_GET_CONFIGURATION request returns information about the current configuration of a power meter. |
| [IOCTL_PMI_GET_MEASUREMENT IOCTL](..\pmi\ni-pmi-ioctl_pmi_get_measurement.md) | The IOCTL_PMI_GET_MEASUREMENT request returns the current measurement data from a power meter. |
| [IOCTL_PMI_REGISTER_EVENT_NOTIFY IOCTL](..\pmi\ni-pmi-ioctl_pmi_register_event_notify.md) | The IOCTL_PMI_REGISTER_EVENT_NOTIFY request registers the IOCTL initiator to be notified about a power meter event. When the event occurs, the Power Meter Interface (PMI) completes the IOCTL request and returns information about the event. |
| [IOCTL_PMI_SET_CONFIGURATION IOCTL](..\pmi\ni-pmi-ioctl_pmi_set_configuration.md) | The IOCTL_PMI_SET_CONFIGURATION request sets the configuration data for a power meter. |
