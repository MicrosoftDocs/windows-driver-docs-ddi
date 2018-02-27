---
UID: NA:ntpoapi
ms.assetid: 05cffe50-bcb4-3779-8086-d9ec44f199f9
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ntpoapi.h header



This header is used by Windows kernel, Battery, Windows Driver Framework. For more information, see
- [Windows kernel](../_kernel/index.md)
- [Battery](../_battery/index.md)
- [Windows Driver Framework](../_wdf/index.md)

Ntpoapi.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [NtPowerInformation function](nf-ntpoapi-ntpowerinformation.md) | The ZwPowerInformation routine sets or retrieves system power information. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [BATTERY_REPORTING_SCALE structure](ns-ntpoapi-battery_reporting_scale.md) | Battery miniclass drivers fill in this structure in response to certain BatteryMiniQueryInformation requests. |
| [CM_Power_Data_s structure](ns-ntpoapi-cm_power_data_s.md) | The CM_POWER_DATA structure contains information about a device's power management state and capabilities. |
| [_COUNTED_REASON_CONTEXT structure](ns-ntpoapi-_counted_reason_context.md) | The COUNTED_REASON_CONTEXT structure contains one or more strings that give reasons for a power request. |
| [_POWER_PLATFORM_INFORMATION structure](ns-ntpoapi-_power_platform_information.md) | The POWER_PLATFORM_INFORMATION structure contains information about the power capabilities of the system. |
| [_POWER_STATE structure](ns-ntpoapi-_power_state.md) | The POWER_STATE union specifies a system power state value or a device power state value. |
| [_SYSTEM_POWER_STATE_CONTEXT structure](ns-ntpoapi-_system_power_state_context.md) | The SYSTEM_POWER_STATE_CONTEXT structure is a partially opaque system structure that contains information about the previous system power states of a computer. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [*PPOWER_ACTION enumeration](ne-ntpoapi-ppower_action.md) | The POWER_ACTION enumeration identifies the system power actions that can occur on a computer. |
| [POWER_INFORMATION_LEVEL enumeration](ne-ntpoapi-power_information_level.md) | Indicates power level information. |
| [_DEVICE_POWER_STATE enumeration](ne-ntpoapi-_device_power_state.md) | The DEVICE_POWER_STATE enumeration type indicates a device power state. |
| [_MONITOR_DISPLAY_STATE enumeration](ne-ntpoapi-_monitor_display_state.md) | Indicates the power state of the monitor being displayed on. |
| [_POWER_REQUEST_TYPE enumeration](ne-ntpoapi-_power_request_type.md) | The POWER_REQUEST_TYPE enumeration indicates the power request type. |
| [_POWER_STATE_TYPE enumeration](ne-ntpoapi-_power_state_type.md) | The POWER_STATE_TYPE enumeration type indicates that a power state value is a system power state or a device power state. |
| [_SYSTEM_POWER_STATE enumeration](ne-ntpoapi-_system_power_state.md) | The SYSTEM_POWER_STATE enumeration type is used to indicate a system power state. |
