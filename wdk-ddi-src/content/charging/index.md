---
UID: NA:charging
ms.assetid: ea5ea45e-3345-3551-94ef-8fd0f279aa6b
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Charging.h header



This header is used by Battery. For more information, see
- [Battery](../_battery/index.md)

Charging.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_BATTERYPROVISIONINGSTATUS structure](ns-charging-_batteryprovisioningstatus.md) | This structure is for internal use only. |
| [_CAD_POWER_SOURCE_INFO structure](ns-charging-_cad_power_source_info.md) | This structure is for internal use only. |
| [_CAD_POWER_SOURCE_INFO_USB structure](ns-charging-_cad_power_source_info_usb.md) | This structure is for internal use only. |
| [_CHARGINGSTATUSCOMPLETE structure](ns-charging-_chargingstatuscomplete.md) | This structure is for internal use only. |
| [_CONFIGURABLE_CHARGER_PROPERTY_HEADER structure](ns-charging-_configurable_charger_property_header.md) | The CONFIGURABLE_CHARGER_PROPERTY_HEADER structure is a header that is used to create your own structure as an input to IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY. |
| [_POWERSOURCESTATUS structure](ns-charging-_powersourcestatus.md) | This struct is for internal use only. |
| [_POWERSOURCEUPDATE structure](ns-charging-_powersourceupdate.md) | This structure is for internal use only. |
| [_POWERSOURCEUPDATEEX structure](ns-charging-_powersourceupdateex.md) | This structure is for internal use only. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_CAD_DISABLE_CHARGING IOCTL](ni-charging-ioctl_cad_disable_charging.md) | This IOCTL is for internal use only. |
| [IOCTL_CAD_GET_BATTERY_PROVISIONING_STATUS IOCTL](ni-charging-ioctl_cad_get_battery_provisioning_status.md) | This IOCTL is for internal use only. |
| [IOCTL_CAD_GET_CHARGING_STATUS_COMPLETE IOCTL](ni-charging-ioctl_cad_get_charging_status_complete.md) | This IOCTL is for internal use only. |
| [IOCTL_CAD_POWER_SOURCE_UPDATE_EX IOCTL](ni-charging-ioctl_cad_power_source_update_ex.md) | This IOCTL is for internal use only. |
| [IOCTL_INTERNAL_CAD_POWER_SOURCE_UPDATE IOCTL](ni-charging-ioctl_internal_cad_power_source_update.md) | This IOCTL is for internal use only. |
| [IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY IOCTL](ni-charging-ioctl_internal_configure_charger_property.md) | The IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY control code is sent from a configurable charger to a device that handles configurable chargers. It configures charger properties. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_POWERSOURCEID enumeration](ne-charging-_powersourceid.md) | This enum is for internal use only. |
