---
UID: NF:wdm.KeInitializeTimerEx
title: KeInitializeTimerEx function (wdm.h)
description: The KeInitializeTimerEx routine initializes an extended kernel timer object.
old-location: kernel\keinitializetimerex.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["KeInitializeTimerEx function"]
ms.keywords: KeInitializeTimerEx, KeInitializeTimerEx routine [Kernel-Mode Driver Architecture], k105_62ca8d08-a87a-4cbd-80fa-18b646b8500d.xml, kernel.keinitializetimerex, wdm/KeInitializeTimerEx
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlKeDispatchLte, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - KeInitializeTimerEx
 - wdm/KeInitializeTimerEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeInitializeTimerEx
---

# KeInitializeTimerEx function


## -description

The <b>KeInitializeTimerEx</b> routine initializes an extended kernel timer object.

## -parameters

### -param Timer [out]


Pointer to a timer object, for which the caller provides the storage.

### -param Type [in]


Specifies the type of the timer object, either <b>NotificationTimer</b> or <b>SynchronizationTimer</b>.

## -remarks

The timer object is initialized to a not-signaled state.

Storage for a timer object must be resident: in the device extension of a driver-created device object, in the controller extension of a driver-created controller object, or in nonpaged pool allocated by the caller.

When a notification timer expires, all waiting threads are released and the timer remains in the signaled state until it is explicitly reset. When a synchronization timer expires, it is set to a signaled state until a single waiting thread is released and then the timer is reset to a not-signaled state.

Callers of <b>KeInitializeTimerEx</b> should be running at IRQL = DISPATCH_LEVEL or lower. It is best to initialize timers at IRQL = PASSIVE_LEVEL.

For more information about timer objects, see <a href="/windows-hardware/drivers/kernel/timer-objects-and-dpcs">Timer Objects and DPCs</a>.

Use <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kesettimer">KeSetTimer</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kesettimerex">KeSetTimerEx</a> to define when the timer will expire.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kecanceltimer">KeCancelTimer</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kereadstatetimer">KeReadStateTimer</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kesettimer">KeSetTimer</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kesettimerex">KeSetTimerEx</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitformultipleobjects">KeWaitForMultipleObjects</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitforsingleobject">KeWaitForSingleObject</a>
