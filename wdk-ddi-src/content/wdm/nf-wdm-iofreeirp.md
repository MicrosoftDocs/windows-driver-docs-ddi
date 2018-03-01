---
UID: NF:wdm.IoFreeIrp
title: IoFreeIrp function
author: windows-driver-content
description: The IoFreeIrp routine releases a caller-allocated IRP from the caller's IoCompletion routine.
old-location: kernel\iofreeirp.htm
old-project: kernel
ms.assetid: 4a032d44-c6c2-4dce-97ea-28ac47f6ad6c
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IoFreeIrp, IoFreeIrp routine [Kernel-Mode Driver Architecture], k104_fc262cc4-a482-4a92-9f8e-1e5765c9b1d4.xml, kernel.iofreeirp, wdm/IoFreeIrp
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IoAllocateFree, IoBuildDeviceControlNoFree, IoBuildFsdFree, IoBuildSynchronousFsdRequestNoFree, HwStorPortProhibitedDDIs, IoFreeIrp
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoFreeIrp
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoFreeIrp function


## -description


The <b>IoFreeIrp</b> routine releases a caller-allocated IRP from the caller's <a href="..\wdm\nc-wdm-io_completion_routine.md">IoCompletion</a> routine.


## -syntax


````
VOID IoFreeIrp(
  _In_ PIRP Irp
);
````


## -parameters




### -param Irp [in]

Pointer to the IRP that is to be released.


## -returns



None




## -remarks



This routine is the reciprocal to <a href="..\wdm\nf-wdm-ioallocateirp.md">IoAllocateIrp</a> or <a href="..\wdm\nf-wdm-iobuildasynchronousfsdrequest.md">IoBuildAsynchronousFsdRequest</a>. The released IRP must have been allocated by the caller.

This routine also releases an IRP allocated with <a href="..\ntddk\nf-ntddk-iomakeassociatedirp.md">IoMakeAssociatedIrp</a> in which the caller set up its <a href="..\wdm\nc-wdm-io_completion_routine.md">IoCompletion</a> routine that returns STATUS_MORE_PROCESSING_REQUIRED for the associated IRP.

<b>IoFreeIrp</b> does not free any MDLs that might be attached to the IRP. The driver that frees the IRP must explicitly free these MDLs. In addition, if the physical pages that are described by an MDL are locked, the driver must unlock the pages before it frees the MDL. However, the driver does not need to explicitly unmap these pages. Instead, <a href="..\wdm\nf-wdm-iofreemdl.md">IoFreeMdl</a> automatically unmaps the pages when it frees the MDL. For a code example that shows how to free an MDL chain, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565421">Using MDLs</a>.




## -see-also

<a href="..\wdm\nf-wdm-iosetcompletionroutine.md">IoSetCompletionRoutine</a>



<a href="..\wdm\nf-wdm-ioallocateirp.md">IoAllocateIrp</a>



<a href="..\wdm\nc-wdm-io_completion_routine.md">IoCompletion</a>



<a href="..\wdm\nf-wdm-iobuildasynchronousfsdrequest.md">IoBuildAsynchronousFsdRequest</a>



<a href="..\ntddk\nf-ntddk-iomakeassociatedirp.md">IoMakeAssociatedIrp</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoFreeIrp routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

