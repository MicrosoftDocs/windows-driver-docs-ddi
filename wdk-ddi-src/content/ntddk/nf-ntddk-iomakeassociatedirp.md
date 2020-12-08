---
UID: NF:ntddk.IoMakeAssociatedIrp
title: IoMakeAssociatedIrp function (ntddk.h)
description: This routine is reserved for use by file systems and file system filter drivers.
old-location: kernel\iomakeassociatedirp.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["IoMakeAssociatedIrp function"]
ms.keywords: IoMakeAssociatedIrp, IoMakeAssociatedIrp routine [Kernel-Mode Driver Architecture], k104_35615730-15a8-4959-8c4d-8e9b4a186e10.xml, kernel.iomakeassociatedirp, ntddk/IoMakeAssociatedIrp
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoMakeAssociatedIrp
 - ntddk/IoMakeAssociatedIrp
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoMakeAssociatedIrp
---

# IoMakeAssociatedIrp function


## -description

This routine is reserved for use by file systems and file system filter drivers. The <b>IoMakeAssociatedIrp</b> routine allocates and initializes an IRP to be associated with a master IRP sent to a highest-level driver, allowing the caller to split the original request and send associated IRPs on to lower-level drivers.

## -parameters

### -param Irp 

[in]
Pointer to the master IRP that was input to a highest-level driver's Dispatch routine.

### -param StackSize 

[in]
Specifies the number of stack locations to be allocated for the associated IRP. The value must be at least equal to the <i>StackSize</i> of the next-lower driver's device object, but the associated IRP can have an additional stack location for the caller.

## -returns

<b>IoMakeAssociatedIrp</b> returns a pointer to the associated IRP or returns a <b>NULL</b> pointer if an IRP cannot be allocated.

## -remarks

Only a highest-level driver can call this routine.

The I/O manager completes the master IRP automatically when lower drivers have completed all associated IRPs as long as the caller has not set its <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_completion_routine">IoCompletion</a> routine in an associated IRP and returned STATUS_MORE_PROCESSING_REQUIRED from its <i>IoCompletion</i> routine. In these circumstances, the caller must explicitly complete the master IRP when that driver has determined that all associated IRPs were completed.

Only the master IRP is associated with a thread; associated IRPs are not. For this reason, the I/O manager cannot call <a href="/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprinterextensionrequest-cancel">Cancel</a> routines for associated IRPs when a thread exits. When the master IRP's thread exits, the I/O manager calls the master IRP's <i>Cancel</i> routine. The <i>Cancel</i> routine is responsible for tracking down all associated IRPs and calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocancelirp">IoCancelIrp</a> to cancel them.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateirp">IoAllocateIrp</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuildasynchronousfsdrequest">IoBuildAsynchronousFsdRequest</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuilddeviceiocontrolrequest">IoBuildDeviceIoControlRequest</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuildsynchronousfsdrequest">IoBuildSynchronousFsdRequest</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocalldriver">IoCallDriver</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetcompletionroutine">IoSetCompletionRoutine</a>
