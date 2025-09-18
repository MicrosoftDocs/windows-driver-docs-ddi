---
UID: NS:wdftimer._WDF_TIMER_CONFIG
title: _WDF_TIMER_CONFIG (wdftimer.h)
description: The WDF_TIMER_CONFIG structure contains configuration information for a framework timer object.
old-location: wdf\wdf_timer_config.htm
tech.root: wdf
ms.date: 09/18/2025
keywords: ["WDF_TIMER_CONFIG structure"]
ms.keywords: "*PWDF_TIMER_CONFIG, DFTimerObjectRef_cacde276-7a83-4a7f-87e1-de043aee4725.xml, PWDF_TIMER_CONFIG, PWDF_TIMER_CONFIG structure pointer, WDF_TIMER_CONFIG, WDF_TIMER_CONFIG structure, _WDF_TIMER_CONFIG, kmdf.wdf_timer_config, wdf.wdf_timer_config, wdftimer/PWDF_TIMER_CONFIG, wdftimer/WDF_TIMER_CONFIG"
req.header: wdftimer.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: WDF_TIMER_CONFIG, *PWDF_TIMER_CONFIG
f1_keywords:
 - _WDF_TIMER_CONFIG
 - wdftimer/_WDF_TIMER_CONFIG
 - PWDF_TIMER_CONFIG
 - wdftimer/PWDF_TIMER_CONFIG
 - WDF_TIMER_CONFIG
 - wdftimer/WDF_TIMER_CONFIG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdftimer.h
api_name:
 - _WDF_TIMER_CONFIG
 - PWDF_TIMER_CONFIG
 - WDF_TIMER_CONFIG
---

# _WDF_TIMER_CONFIG structure

## -description

*[Applies to KMDF and UMDF]*

The **WDF_TIMER_CONFIG** structure contains configuration information for a framework timer object.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field EvtTimerFunc

A pointer to a driver-supplied [EvtTimerFunc](/windows-hardware/drivers/ddi/wdftimer/nc-wdftimer-evt_wdf_timer) callback function, or **NULL**.

### -field Period

A time period, in milliseconds. The framework calls the driver's [EvtTimerFunc](/windows-hardware/drivers/ddi/wdftimer/nc-wdftimer-evt_wdf_timer) callback function repeatedly, whenever the specified number of milliseconds elapses. If this value is zero, the framework does not call the driver's *EvtTimerFunc* callback function repeatedly. Instead, it calls the callback function once, after the [WdfTimerStart](/windows-hardware/drivers/ddi/wdftimer/nf-wdftimer-wdftimerstart) method's *DueTime* has elapsed. (The time period must be zero if [WdfTimerCreate](/windows-hardware/drivers/ddi/wdftimer/nf-wdftimer-wdftimercreate) sets the execution level to [WdfExecutionLevelPassive](/windows-hardware/drivers/ddi/wdfobject/ne-wdfobject-_wdf_execution_level).) The time period cannot be a negative value.

### -field AutomaticSerialization

A Boolean value that, if **TRUE**, indicates that the framework will synchronize execution of the timer object's [EvtTimerFunc](/windows-hardware/drivers/ddi/wdftimer/nc-wdftimer-evt_wdf_timer) callback function with callback functions from other objects that are underneath the timer's parent device object. For more information, see the following Remarks section. If **FALSE**, the framework does not synchronize execution of the *EvtTimerFunc* callback function.

### -field TolerableDelay

Specifies a tolerance, in milliseconds, for the timer period that *Period* specifies and for the initial time interval that the [WdfTimerStart](/windows-hardware/drivers/ddi/wdftimer/nf-wdftimer-wdftimerstart) method's *DueTime* specifies. For a periodic timer, the time interval between two successive timer expirations will be in the range from (*Period* - *TolerableDelay*) to (*Period* + *TolerableDelay*). The initial expiration time will be in the range from *DueTime* to (*DueTime* + *TolerableDelay*). The *TolerableDelay* value cannot be negative.

The **TolerableDelay** member is available in version 1.9 and later versions of KMDF.

In a driver using KMDF 1.13 or UMDF 2.0, you can set this member to **TolerableDelayUnlimited** to specify that the system should not be woken up as a result of this timer's expiration.

If  **UseHighResolutionTimer** is **WdfTrue**, you must set **TolerableDelay** to zero. Otherwise, [WdfTimerCreate](/windows-hardware/drivers/ddi/wdftimer/nf-wdftimer-wdftimercreate) returns a failure code.

For more information about this member, see the following Remarks section.

### -field UseHighResolutionTimer

KMDF only

This member is available starting with KMDF version 1.13.

A [WDF_TRI_STATE](/windows-hardware/drivers/ddi/wdftypes/ne-wdftypes-_wdf_tri_state)-typed value. If this value is **WdfTrue**, the framework uses a high resolution timer that has an accuracy of one millisecond.  If the value is **WdfFalse** or **WdfDefault**, the framework uses a standard timer that has an accuracy matching the system clock tick interval, which is by default 15.6 milliseconds.

> [!WARNING]
> If you set **UseHighResolutionTimer** to **WdfTrue**, you must call [WdfTimerStart](/windows-hardware/drivers/ddi/wdftimer/nf-wdftimer-wdftimerstart) with the *DueTime* parameter set to a negative value.  Otherwise, the call causes the system to crash.

If  **UseHighResolutionTimer** is **WdfTrue**, you must set **TolerableDelay** to zero. Otherwise, [WdfTimerCreate](/windows-hardware/drivers/ddi/wdftimer/nf-wdftimer-wdftimercreate) returns a failure code.

## -remarks

The **WDF_TIMER_CONFIG** structure is used as input to the [WdfTimerCreate](/windows-hardware/drivers/ddi/wdftimer/nf-wdftimer-wdftimercreate) method. To initialize a **WDF_TIMER_CONFIG** structure, your driver must call either [WDF_TIMER_CONFIG_INIT](/windows-hardware/drivers/ddi/wdftimer/nf-wdftimer-wdf_timer_config_init) or [WDF_TIMER_CONFIG_INIT_PERIODIC](/windows-hardware/drivers/ddi/wdftimer/nf-wdftimer-wdf_timer_config_init_periodic).

Setting the **AutomaticSerialization** member of **WDF_TIMER_CONFIG** to **TRUE** has no effect if the parent object's [synchronization scope](/windows-hardware/drivers/ddi/wdfobject/ne-wdfobject-_wdf_synchronization_scope) is set to **WdfSynchronizationScopeNone**.

If the parent device object's execution level is **WdfExecutionLevelPassive**, you can set the **AutomaticSerialization** member to **TRUE** only if the timer object represents a [passive-level timer](/windows-hardware/drivers/wdf/using-timers).

If a driver uses the **TolerableDelay** member, the operating system can group together expiration times that are close together and process them all at once. If the operating system can handle the expirations of multiple timers at once, it can potentially keep the computer in a low-power state for longer periods of time to increase battery life.

If the **TolerableDelay** member is **TolerableDelayUnlimited**, the system will not return to its fully on (S0) state to service the timer if it is in a low-power (S*x*) state when the timer expires. A driver can specify **TolerableDelayUnlimited** to increase battery life when the timer is related to a non-critical periodic operation.

Setting **UseHighResolutionTimer** to **WdfTrue** will enable a high-resolution timer object instead of a regular timer and may result in decreased battery life. Only use this if a higher resolution is actually needed. For more information and alternatives see the dedicated article on [high-resolution timers](/windows-hardware/drivers/kernel/high-resolution-timers).

For more information about **AutomaticSerialization** and synchronizing driver callback functions, see [Synchronization Techniques for Framework-Based Drivers](/windows-hardware/drivers/wdf/synchronization-techniques-for-wdf-drivers).

For more information about framework timer objects, see [Using Timers](/windows-hardware/drivers/wdf/using-timers).

## -see-also

- [EvtTimerFunc](/windows-hardware/drivers/ddi/wdftimer/nc-wdftimer-evt_wdf_timer)
- [WDF_TIMER_CONFIG_INIT](/windows-hardware/drivers/ddi/wdftimer/nf-wdftimer-wdf_timer_config_init)
- [WDF_TIMER_CONFIG_INIT_PERIODIC](/windows-hardware/drivers/ddi/wdftimer/nf-wdftimer-wdf_timer_config_init_periodic)
- [WdfTimerCreate](/windows-hardware/drivers/ddi/wdftimer/nf-wdftimer-wdftimercreate)
- [WdfTimerStart](/windows-hardware/drivers/ddi/wdftimer/nf-wdftimer-wdftimerstart)
