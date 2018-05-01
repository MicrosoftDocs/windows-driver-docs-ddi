---
UID: NF:wdm.IoFreeIrp
title: IoFreeIrp function
author: windows-driver-content
description: The IoFreeIrp routine releases a caller-allocated IRP from the caller's IoCompletion routine.
old-location: kernel\iofreeirp.htm
old-project: kernel
ms.assetid: 4a032d44-c6c2-4dce-97ea-28ac47f6ad6c
ms.author: windowsdriverdev
ms.date: 4/5/2018
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
req.typenames: 
---

# IoFreeIrp function


## -description


The <b>IoFreeIrp</b> routine releases a caller-allocated IRP from the caller's <a href="https://msdn.microsoft.com/library/windows/hardware/ff548354">IoCompletion</a> routine.


## -parameters




### -param Irp [in]

Pointer to the IRP that is to be released.


## -returns



None




## -remarks



This routine is the reciprocal to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548257">IoAllocateIrp</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548310">IoBuildAsynchronousFsdRequest</a>. The released IRP must have been allocated by the caller.

This routine also releases an IRP allocated with <a href="https://msdn.microsoft.com/library/windows/hardware/ff549397">IoMakeAssociatedIrp</a> in which the caller set up its <a href="https://msdn.microsoft.com/library/windows/hardware/ff548354">IoCompletion</a> routine that returns STATUS_MORE_PROCESSING_REQUIRED for the associated IRP.

<b>IoFreeIrp</b> does not free any MDLs that might be attached to the IRP. The driver that frees the IRP must explicitly free these MDLs. In addition, if the physical pages that are described by an MDL are locked, the driver must unlock the pages before it frees the MDL. However, the driver does not need to explicitly unmap these pages. Instead, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549126">IoFreeMdl</a> automatically unmaps the pages when it frees the MDL. For a code example that shows how to free an MDL chain, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565421">Using MDLs</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548257">IoAllocateIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548310">IoBuildAsynchronousFsdRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548354">IoCompletion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549397">IoMakeAssociatedIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549679">IoSetCompletionRoutine</a>
 

 

