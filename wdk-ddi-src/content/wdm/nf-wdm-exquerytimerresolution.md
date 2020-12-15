---
UID: NF:wdm.ExQueryTimerResolution
title: ExQueryTimerResolution function (wdm.h)
description: The ExQueryTimerResolution routine reports the range of timer resolutions that are supported by the system clock.
old-location: kernel\exquerytimerresolution.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["ExQueryTimerResolution function"]
ms.keywords: ExQueryTimerResolution, ExQueryTimerResolution routine [Kernel-Mode Driver Architecture], kernel.exquerytimerresolution, wdm/ExQueryTimerResolution
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntoskrnl.lib
req.dll: 
req.irql: Any level.
targetos: Windows
req.typenames: 
f1_keywords:
 - ExQueryTimerResolution
 - wdm/ExQueryTimerResolution
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ntoskrnl.lib
 - ntoskrnl.dll
api_name:
 - ExQueryTimerResolution
---

# ExQueryTimerResolution function


## -description

The <b>ExQueryTimerResolution</b> routine reports the range of timer resolutions that are supported by the system clock.

## -parameters

### -param MaximumTime 

[out]
A pointer to a location to which the routine writes the maximum time interval, in 100-nanosecond units, between successive ticks of the system clock. A <i>tick</i> is an interrupt caused by the system clock timer.

### -param MinimumTime 

[out]
A pointer to a location to which the routine writes the minimum time interval, in 100-nanosecond units, between successive ticks of the system clock.

### -param CurrentTime 

[out]
A pointer to a location to which the routine writes the current time interval, in 100-nanosecond units, between successive ticks of the system clock.

## -remarks

If your driver calls the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exsettimerresolution">ExSetTimerResolution</a> routine to change the time interval between successive system clock interrupts, the driver can first call <b>ExQueryTimerResolution</b> to determine the range of intervals supported by the system clock.

When your driver calls a routine such as <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kesettimerex">KeSetTimerEx</a> to set a timer, the accuracy of the timer depends on the resolution of the system clock. For more information, see <a href="/windows-hardware/drivers/kernel/timer-accuracy">Timer Accuracy</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exsettimerresolution">ExSetTimerResolution</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kesettimerex">KeSetTimerEx</a>
