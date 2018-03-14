---
UID: NA:wdftimer
ms.assetid: 2e3461b3-e5d1-3020-83c8-4e3a677d10f1
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wdftimer.h header



This header is used by Windows Driver Framework. For more information, see
- [Windows Driver Framework](../_wdf/index.md)

Wdftimer.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [WDF_TIMER_CONFIG_INIT function](nf-wdftimer-wdf_timer_config_init.md) | The WDF_TIMER_CONFIG_INIT function initializes a WDF_TIMER_CONFIG structure for a timer that will use a single due time. |
| [WDF_TIMER_CONFIG_INIT_PERIODIC function](nf-wdftimer-wdf_timer_config_init_periodic.md) | The WDF_TIMER_CONFIG_INIT_PERIODIC function initializes a WDF_TIMER_CONFIG structure for a periodic timer. |
| [WdfTimerCreate function](nf-wdftimer-wdftimercreate.md) | The WdfTimerCreate method creates a framework timer object. |
| [WdfTimerGetParentObject function](nf-wdftimer-wdftimergetparentobject.md) | The WdfTimerGetParentObject method returns a handle to the parent object of a specified framework timer object. |
| [WdfTimerStart function](nf-wdftimer-wdftimerstart.md) | The WdfTimerStart method starts a timer's clock. |
| [WdfTimerStop function](nf-wdftimer-wdftimerstop.md) | The WdfTimerStop method stops a timer's clock. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_WDF_TIMER_CONFIG structure](ns-wdftimer-_wdf_timer_config.md) | The WDF_TIMER_CONFIG structure contains configuration information for a framework timer object. |
