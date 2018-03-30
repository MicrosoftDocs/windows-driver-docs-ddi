---
UID: NA:pmi
ms.assetid: d1e1b40a-26b6-3527-9981-b4f25be1e45f
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Pmi.h header



This header is used by Power metering. For more information, see
- [Power metering](../_powermeter/index.md)

Pmi.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_PMI_BUDGETING_CONFIGURATION structure](ns-pmi-_pmi_budgeting_configuration.md) | The PMI_BUDGETING_CONFIGURATION structure contains information about the current power budget of a power meter. A power budget defines how much power that the system can consume from the set of power supplies monitored by the power meter. |
| [_PMI_CAPABILITIES structure](ns-pmi-_pmi_capabilities.md) | The PMI_CAPABILITIES structure contains information about the power metering and budgeting capabilities of a power meter. |
| [_PMI_CONFIGURATION structure](ns-pmi-_pmi_configuration.md) | The PMI_CONFIGURATION structure contains information about the current power metering and budgeting configuration of a power meter. |
| [_PMI_EVENT structure](ns-pmi-_pmi_event.md) | The PMI_EVENT structure contains information about a power metering and budgeting event that is signaled through the Power Meter Interface (PMI). |
| [_PMI_MEASUREMENT_CONFIGURATION structure](ns-pmi-_pmi_measurement_configuration.md) | The PMI_MEASUREMENT_CONFIGURATION structure contains information about the current power measurement configuration of a power meter. |
| [_PMI_MEASUREMENT_DATA structure](ns-pmi-_pmi_measurement_data.md) | The PMI_MEASUREMENT_DATA structure contains the current power measurement that is collected by a power meter. |
| [_PMI_METERED_HARDWARE_INFORMATION structure](ns-pmi-_pmi_metered_hardware_information.md) | The PMI_METERED_HARDWARE_INFORMATION structure contains information about one or more power supplies that are monitored by the power meter. |
| [_PMI_REPORTED_CAPABILITIES structure](ns-pmi-_pmi_reported_capabilities.md) | The PMI_REPORTED_CAPABILITIES structure contains information about the type of power metering and budgeting capabilities a power meter supports. Additionally, this structure contains asset information about the power meter itself. |
| [_PMI_THRESHOLD_CONFIGURATION structure](ns-pmi-_pmi_threshold_configuration.md) | The PMI_THRESHOLD_CONFIGURATION structure contains information about the threshold configuration of the power meter. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_PMI_GET_CAPABILITIES IOCTL](ni-pmi-ioctl_pmi_get_capabilities.md) | The IOCTL_PMI_GET_CAPABILITIES request obtains the capability and asset information about a power meter. |
| [IOCTL_PMI_GET_CONFIGURATION IOCTL](ni-pmi-ioctl_pmi_get_configuration.md) | The IOCTL_PMI_GET_CONFIGURATION request returns information about the current configuration of a power meter. |
| [IOCTL_PMI_GET_MEASUREMENT IOCTL](ni-pmi-ioctl_pmi_get_measurement.md) | The IOCTL_PMI_GET_MEASUREMENT request returns the current measurement data from a power meter. |
| [IOCTL_PMI_REGISTER_EVENT_NOTIFY IOCTL](ni-pmi-ioctl_pmi_register_event_notify.md) | The IOCTL_PMI_REGISTER_EVENT_NOTIFY request registers the IOCTL initiator to be notified about a power meter event. When the event occurs, the Power Meter Interface (PMI) completes the IOCTL request and returns information about the event. |
| [IOCTL_PMI_SET_CONFIGURATION IOCTL](ni-pmi-ioctl_pmi_set_configuration.md) | The IOCTL_PMI_SET_CONFIGURATION request sets the configuration data for a power meter. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [PMI_CAPABILITIES_TYPE enumeration](ne-pmi-pmi_capabilities_type.md) | The PMI_CAPABILITIES_TYPE enumeration defines the type of capabilities data that is referenced by the Capability member of the PMI_CAPABILITIES structure. |
| [PMI_CONFIGURATION_TYPE enumeration](ne-pmi-pmi_configuration_type.md) | The PMI_CONFIGURATION_TYPE enumeration defines the type of PMI configuration data that is referenced by the Configuration member of the PMI_CONFIGURATION structure. |
| [PMI_EVENT_TYPE enumeration](ne-pmi-pmi_event_type.md) | The PMI_EVENT_TYPE enumeration defines the type of PMI power meter event that is returned through the successful completion of an IOCTL_PMI_REGISTER_EVENT_NOTIFY request. |
| [PMI_MEASUREMENT_TYPE enumeration](ne-pmi-pmi_measurement_type.md) | The PMI_MEASUREMENT_TYPE enumeration defines the source of the PMI measurement data. |
| [PMI_MEASUREMENT_UNIT enumeration](ne-pmi-pmi_measurement_unit.md) | The PMI_MEASUREMENT_UNIT enumeration defines the units of the PMI measurement data. |
