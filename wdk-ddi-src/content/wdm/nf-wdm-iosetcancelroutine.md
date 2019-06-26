---
UID: NF:wdm.IoSetCancelRoutine
title: IoSetCancelRoutine function (wdm.h)
description: The IoSetCancelRoutine routine sets up a driver-supplied Cancel routine to be called if a given IRP is canceled.
old-location: kernel\iosetcancelroutine.htm
tech.root: kernel
ms.assetid: 5bc81897-6463-4588-9348-78a1954216bd
ms.date: 04/30/2018
ms.keywords: IoSetCancelRoutine, IoSetCancelRoutine routine [Kernel-Mode Driver Architecture], k104_a9ac44bc-fe8a-4392-b9f8-d9a90a03fbc0.xml, kernel.iosetcancelroutine, wdm/IoSetCancelRoutine
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrpCancelField, StartIoCancel
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: DISPATCH_LEVEL (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoSetCancelRoutine
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoSetCancelRoutine function


## -description


The <b>IoSetCancelRoutine</b> routine sets up a driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterextensionrequest-cancel">Cancel</a> routine to be called if a given IRP is canceled. 


## -parameters




### -param Irp [in]

Pointer to the IRP being put into or removed from a cancelable state.


### -param CancelRoutine [in]

Specifies the entry point of the caller-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterextensionrequest-cancel">Cancel</a> routine to be called if the specified IRP is canceled or is <b>NULL</b> if the given IRP is being removed from the cancelable state. This routine is declared as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
(*PDRIVER_CANCEL)(
    IN PDEVICE_OBJECT DeviceObject,
    IN PIRP Irp
    );</pre>
</td>
</tr>
</table></span></div>

## -returns



<b>IoSetCancelRoutine</b> returns the previous value of <i>Irp</i>-><b>CancelRoutine</b>. If no <i>Cancel</i> routine was previously set, or if IRP cancellation is already in progress, <b>IoSetCancelRoutine</b> returns <b>NULL</b>.




## -remarks



This routine can disable the <i>Cancel</i> routine currently set in an IRP.

A driver must hold the system cancel spin lock when calling this routine if the driver uses the I/O manager-supplied device queue in the device object. The driver runs at IRQL = DISPATCH_LEVEL after calling <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff548196(v=vs.85)">IoAcquireCancelSpinLock</a> until it releases the cancel spin lock with <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff549550(v=vs.85)">IoReleaseCancelSpinLock</a>.

If the driver manages its own queues of IRPs, then the driver need not hold the cancel spin lock when calling this routine. <b>IoSetCancelRoutine</b> uses an interlocked exchange intrinsic to set the address of the <i>Cancel</i> routine as an atomic operation. Reduced usage of the cancel spin lock can improve driver performance and overall system performance.

Driver <i>Cancel</i> routines are called at IRQL = DISPATCH_LEVEL with the cancel spin lock held. The <i>Cancel</i> routine must release the cancel spin lock before it returns control.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff548196(v=vs.85)">IoAcquireCancelSpinLock</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff549550(v=vs.85)">IoReleaseCancelSpinLock</a>
 

 

