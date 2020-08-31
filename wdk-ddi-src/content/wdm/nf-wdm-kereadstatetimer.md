---
UID: NF:wdm.KeReadStateTimer
title: KeReadStateTimer function (wdm.h)
description: The KeReadStateTimer routine reads the current state of a timer object.
old-location: kernel\kereadstatetimer.htm
tech.root: kernel
ms.assetid: 0f7fc534-4a81-42e0-a3e6-8b91baa28b55
ms.date: 04/30/2018
keywords: ["KeReadStateTimer function"]
ms.keywords: KeReadStateTimer, KeReadStateTimer routine [Kernel-Mode Driver Architecture], k105_8e101501-f419-40ff-91cd-a8aee0ffcbc8.xml, kernel.kereadstatetimer, wdm/KeReadStateTimer
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KeReadStateTimer
 - wdm/KeReadStateTimer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeReadStateTimer
---

# KeReadStateTimer function


## -description

The <b>KeReadStateTimer</b> routine reads the current state of a timer object.

## -parameters

### -param Timer 

[in]
A pointer to an initialized timer object, for which the caller provides the storage.

## -returns

<b>KeReadStateTimer</b> returns <b>TRUE</b> if the current state of the timer object is signaled; otherwise, it returns <b>FALSE</b>.

## -remarks

This routine provides an efficient way to poll the signal state of a timer. <b>KeReadStateTimer</b> reads the state of the timer without synchronizing its access to the timer. Do not assume that accesses of a timer state by <b>KeReadStateTimer</b> are mutually exclusive of accesses by routines, such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kesettimer">KeSetTimer</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitforsingleobject">KeWaitForSingleObject</a>, that do synchronize their access to the timer state.

For more information about timer objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/timer-objects-and-dpcs">Timer Objects and DPCs</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KTIMER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kecanceltimer">KeCancelTimer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializetimer">KeInitializeTimer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kesettimer">KeSetTimer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitforsingleobject">KeWaitForSingleObject</a>

