---
UID: NF:wdm.IoReuseIrp
title: IoReuseIrp function
author: windows-driver-content
description: The IoReuseIrp routine reinitializes an IRP so that it can be reused.
old-location: kernel\ioreuseirp.htm
old-project: kernel
ms.assetid: 18ad2c76-110f-45a9-986b-67e7c81f256f
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: IoReuseIrp, IoReuseIrp routine [Kernel-Mode Driver Architecture], k104_548c8bd2-bc09-4ee6-b373-d244f1f11daa.xml, kernel.ioreuseirp, wdm/IoReuseIrp
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IoReuseIrp, IoReuseIrp2, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoReuseIrp
product: Windows
targetos: Windows
req.typenames: 
---

# IoReuseIrp function


## -description


The <b>IoReuseIrp</b> routine reinitializes an IRP so that it can be reused.


## -parameters




### -param Irp [in, out]

Pointer to the IRP to be reinitialized for reuse. 


### -param Iostatus

TBD




#### - Status [in]

Specifies the NTSTATUS value to be set in the IRP after it is reinitialized.


## -returns



None




## -remarks



Drivers for Windows 2000 and later versions of Windows use <b>IoReuseIrp</b> to reuse an IRP.

A driver should use <b>IoReuseIrp</b> only on IRPs it previously allocated either as raw memory or with <a href="https://msdn.microsoft.com/library/windows/hardware/ff548257">IoAllocateIrp</a>. In particular, drivers should not use this routine for IRPs created with <a href="https://msdn.microsoft.com/library/windows/hardware/ff549397">IoMakeAssociatedIrp</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548330">IoBuildSynchronousFsdRequest</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548310">IoBuildAsynchronousFsdRequest</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548318">IoBuildDeviceIoControlRequest</a>. 

See <a href="https://msdn.microsoft.com/library/windows/hardware/ff561107">Reusing IRPs</a> for more details on how to reuse IRPs. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548257">IoAllocateIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549315">IoInitializeIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549397">IoMakeAssociatedIrp</a>
 

 

