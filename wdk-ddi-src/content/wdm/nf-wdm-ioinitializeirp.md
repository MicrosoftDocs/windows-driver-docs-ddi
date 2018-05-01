---
UID: NF:wdm.IoInitializeIrp
title: IoInitializeIrp function
author: windows-driver-content
description: The IoInitializeIrp routine initializes a given IRP that was allocated by the caller.
old-location: kernel\ioinitializeirp.htm
old-project: kernel
ms.assetid: 3b5cc1af-ab3b-4583-9ef9-39132789e74f
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: IoInitializeIrp, IoInitializeIrp routine [Kernel-Mode Driver Architecture], k104_5c9dc7a8-747c-4832-a31b-5936e2d3361d.xml, kernel.ioinitializeirp, wdm/IoInitializeIrp
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
req.ddi-compliance: IoReuseIrp, HwStorPortProhibitedDDIs
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
-	IoInitializeIrp
product: Windows
targetos: Windows
req.typenames: 
---

# IoInitializeIrp function


## -description


The <b>IoInitializeIrp</b> routine initializes a given IRP that was allocated by the caller.


## -parameters




### -param Irp [in, out]

Pointer to the IRP to be initialized.


### -param PacketSize [in]

Specifies the size in bytes of the IRP.


### -param StackSize [in]

Specifies the number of stack locations in the IRP. 


## -returns



None




## -remarks



Drivers use <b>IoInitializeIrp</b> to initialize IRPs the driver allocated as raw memory. Do not use <b>IoInitializeIrp</b> to initialize an IRP allocated by <b>IoAllocateIrp</b>. <b>IoAllocateIrp</b> automatically initializes the members of the IRP.

Drivers can use <b>IoInitializeIrp</b> to reinitialize an IRP for reuse only under certain circumstances. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff561107">Reusing IRPs</a> for details.

If the driver associates an MDL with the IRP it allocated, the driver is responsible for releasing the MDL when the IRP is completed.

An intermediate or highest-level driver also can call <b>IoBuildDeviceIoControlRequest</b>, <b>IoBuildAsynchronousFsdRequest</b>, or <b>IoBuildSynchronousFsdRequest</b> to set up requests it sends to lower-level drivers. Only a highest-level driver can call <b>IoMakeAssociatedIrp</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548257">IoAllocateIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548263">IoAllocateMdl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548324">IoBuildPartialMdl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh454223">IoFreeIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549126">IoFreeMdl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549661">IoReuseIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550321">IoSetNextIrpStackLocation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550349">IoSizeOfIrp</a>
 

 

