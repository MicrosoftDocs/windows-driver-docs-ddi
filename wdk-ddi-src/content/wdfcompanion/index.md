---
UID: NA:wdfcompanion
ms.assetid: 1609183e-a1be-32bc-a0f3-d29aa7003475
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wdfcompanion.h header



This header is used by Windows Driver Framework. For more information, see
- [Windows Driver Framework](../_wdf/index.md)

Wdfcompanion.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [WDF_COMPANION_EVENT_CALLBACKS_INIT function](nf-wdfcompanion-wdf_companion_event_callbacks_init.md) | For internal use only. |
| [WDF_TASK_QUEUE_CONFIG_INIT function](nf-wdfcompanion-wdf_task_queue_config_init.md) | For internal use only. |
| [WdfCompanionCreate function](nf-wdfcompanion-wdfcompanioncreate.md) | For internal use only. |
| [WdfCompanionCreateTaskQueue function](nf-wdfcompanion-wdfcompanioncreatetaskqueue.md) | For internal use only. |
| [WdfCompanionWdmGetSecureDeviceHandle function](nf-wdfcompanion-wdfcompanionwdmgetsecuredevicehandle.md) | For internal use only. |
| [WdfDeviceInitSetCompanionEventCallbacks function](nf-wdfcompanion-wdfdeviceinitsetcompanioneventcallbacks.md) | For internal use only. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_WDF_COMPANION_POST_D0_EXIT callback](nc-wdfcompanion-evt_wdf_companion_post_d0_exit.md) | For internal use only. |
| [EVT_WDF_COMPANION_POST_RELEASE_HARDWARE callback](nc-wdfcompanion-evt_wdf_companion_post_release_hardware.md) | For internal use only. |
| [EVT_WDF_COMPANION_PRE_D0_ENTRY callback](nc-wdfcompanion-evt_wdf_companion_pre_d0_entry.md) | For internal use only. |
| [EVT_WDF_COMPANION_PRE_PREPARE_HARDWARE callback](nc-wdfcompanion-evt_wdf_companion_pre_prepare_hardware.md) | For internal use only. |
| [EVT_WDF_TASK_QUEUE_TASK_EXECUTE_SYNC callback](nc-wdfcompanion-evt_wdf_task_queue_task_execute_sync.md) | For internal use only. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_WDF_COMPANION_EVENT_CALLBACKS structure](ns-wdfcompanion-_wdf_companion_event_callbacks.md) | For internal use only. |
| [_WDF_TASK_QUEUE_CONFIG structure](ns-wdfcompanion-_wdf_task_queue_config.md) | For internal use only. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_WDF_TASK_QUEUE_DISPATCH_TYPE enumeration](ne-wdfcompanion-_wdf_task_queue_dispatch_type.md) | For internal use only. |
