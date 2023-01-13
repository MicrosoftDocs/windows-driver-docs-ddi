---
UID: NF:wdm.ExSetTimerResolution
title: ExSetTimerResolution function (wdm.h)
description: The ExSetTimerResolution routine modifies the frequency at which the system clock interrupts. Use this routine with extreme caution (see the following Remarks section).
tech.root: kernel
ms.date: 01/12/2023
keywords: ["ExSetTimerResolution function"]
ms.keywords: ExSetTimerResolution, ExSetTimerResolution routine [Kernel-Mode Driver Architecture], k102_09179649-af93-434f-92e0-844a2bdf34dc.xml, kernel.exsettimerresolution, wdm/ExSetTimerResolution
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlExApcLte2, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: IRQL <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ExSetTimerResolution
 - wdm/ExSetTimerResolution
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExSetTimerResolution
---

## -description

The **ExSetTimerResolution** routine modifies the frequency at which the system clock interrupts. Use this routine with extreme caution (see the following Remarks section).

## -parameters

### -param DesiredTime [in]

Specifies the amount of time that should elapse between each timer interrupt, in 100-nanosecond units. The minimum value is approximately 10,000 (1 millisecond) but can vary slightly by platform. (This parameter is ignored if *SetResolution* is **FALSE**.)

### -param SetResolution [in]

If **TRUE**, the call is a request to set the clock interrupt frequency to the value specified by *DesiredTime*. If **FALSE**, the call is a request to restore the clock interrupt frequency to the system's default value, which is platform-specific.

## -returns

**ExSetTimerResolution** returns the new timer resolution, in 100-nanosecond units.

## -remarks

To set the timer resolution, a driver calls this routine passing **TRUE** as the parameter for *SetResolution*. The following rules apply:

- The routine changes the clock interrupt frequency only if the specified  *DesiredTime* value is less than the current setting.

- If a driver requests a *DesiredTime* value that is greater than what is currently set, the routine just returns the current setting.

- If a driver requests a *DesiredTime* value that is less than the system clock can support, the routine uses the smallest resolution the system can support, and returns that value.

If you use this routine to change the clock interrupt frequency, your driver must restore the default interrupt frequency, typically by making the following call before being unloaded:

```cpp
ExSetTimerResolution (0, FALSE);
```

If multiple drivers have attempted to modify the clock interrupt frequency, the system does not restore the default frequency until all of these drivers have called this routine with a *SetResolution* value of **FALSE**.

The result of changing the clock interrupt frequency is system-wide and can have a severely negative effect on system performance. Also note that higher clock interrupt frequencies can shorten a system's battery life.

During the processing of an [IRP_MJ_POWER](/windows-hardware/drivers/kernel/irp-mj-power) request, the power manager holds a lock on a resource that **ExSetTimerResolution** must acquire to complete. Consequently, a deadlock will occur if a driver directly or indirectly calls **ExSetTimerResolution** while processing a power request, and then waits for the call to **ExSetTimerResolution** to return before the driver completes the power request. For more information about safely calling **ExSetTimerResolution** while processing a power IRP, see [Calling ExSetTimerResolution While Processing a Power IRP](/windows-hardware/drivers/kernel/calling-exsettimerresolution-while-processing-a-power-irp).

## -see-also

[KeSetTimerEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-kesettimerex)
