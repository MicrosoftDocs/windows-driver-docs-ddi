---
UID: NF:ntddk.IoMakeAssociatedIrp
title: IoMakeAssociatedIrp function
author: windows-driver-content
description: This routine is reserved for use by file systems and file system filter drivers.
old-location: kernel\iomakeassociatedirp.htm
old-project: kernel
ms.assetid: 96dd78f1-8b71-4707-8b66-20d80c198f81
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.iomakeassociatedirp, ntddk/IoMakeAssociatedIrp, IoMakeAssociatedIrp routine [Kernel-Mode Driver Architecture], k104_35615730-15a8-4959-8c4d-8e9b4a186e10.xml, IoMakeAssociatedIrp
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoMakeAssociatedIrp
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---

# IoMakeAssociatedIrp function


## -description


This routine is reserved for use by file systems and file system filter drivers. The <b>IoMakeAssociatedIrp</b> routine allocates and initializes an IRP to be associated with a master IRP sent to a highest-level driver, allowing the caller to split the original request and send associated IRPs on to lower-level drivers.


## -syntax


````
PIRP IoMakeAssociatedIrp(
  _In_ PIRP  Irp,
  _In_ CCHAR StackSize
);
````


## -parameters




### -param Irp [in]

Pointer to the master IRP that was input to a highest-level driver's Dispatch routine.


### -param StackSize [in]

Specifies the number of stack locations to be allocated for the associated IRP. The value must be at least equal to the <i>StackSize</i> of the next-lower driver's device object, but the associated IRP can have an additional stack location for the caller. 


## -returns



<b>IoMakeAssociatedIrp</b> returns a pointer to the associated IRP or returns a <b>NULL</b> pointer if an IRP cannot be allocated.




## -remarks



Only a highest-level driver can call this routine.

The I/O manager completes the master IRP automatically when lower drivers have completed all associated IRPs as long as the caller has not set its <a href="..\wdm\nc-wdm-io_completion_routine.md">IoCompletion</a> routine in an associated IRP and returned STATUS_MORE_PROCESSING_REQUIRED from its <i>IoCompletion</i> routine. In these circumstances, the caller must explicitly complete the master IRP when that driver has determined that all associated IRPs were completed.

Only the master IRP is associated with a thread; associated IRPs are not. For this reason, the I/O manager cannot call <a href="https://msdn.microsoft.com/library/windows/hardware/hh406716">Cancel</a> routines for associated IRPs when a thread exits. When the master IRP's thread exits, the I/O manager calls the master IRP's <i>Cancel</i> routine. The <i>Cancel</i> routine is responsible for tracking down all associated IRPs and calling <a href="..\wdm\nf-wdm-iocancelirp.md">IoCancelIrp</a> to cancel them.




## -see-also

<a href="..\wdm\nf-wdm-iosetcompletionroutine.md">IoSetCompletionRoutine</a>



<a href="..\wdm\nf-wdm-iobuildsynchronousfsdrequest.md">IoBuildSynchronousFsdRequest</a>



<a href="..\wdm\nf-wdm-iobuilddeviceiocontrolrequest.md">IoBuildDeviceIoControlRequest</a>



<a href="..\wdm\nf-wdm-iobuildasynchronousfsdrequest.md">IoBuildAsynchronousFsdRequest</a>



<a href="..\wdm\ns-wdm-_irp.md">IRP</a>



<a href="..\wdm\nf-wdm-ioallocateirp.md">IoAllocateIrp</a>



<a href="..\wdm\nf-wdm-iosetcompletionroutine.md">IoSetCompletionRoutine</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoMakeAssociatedIrp routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

