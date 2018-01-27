---
UID: NF:wdm.IoInitializeIrp
title: IoInitializeIrp function
author: windows-driver-content
description: The IoInitializeIrp routine initializes a given IRP that was allocated by the caller.
old-location: kernel\ioinitializeirp.htm
old-project: kernel
ms.assetid: 3b5cc1af-ab3b-4583-9ef9-39132789e74f
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k104_5c9dc7a8-747c-4832-a31b-5936e2d3361d.xml, IoInitializeIrp, kernel.ioinitializeirp, wdm/IoInitializeIrp, IoInitializeIrp routine [Kernel-Mode Driver Architecture]
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
req.irql: <= DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	IoInitializeIrp
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoInitializeIrp function


## -description


The <b>IoInitializeIrp</b> routine initializes a given IRP that was allocated by the caller.


## -syntax


````
VOID IoInitializeIrp(
  _Inout_ PIRP   Irp,
  _In_    USHORT PacketSize,
  _In_    CCHAR  StackSize
);
````


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

<a href="..\wdm\nf-wdm-ioallocatemdl.md">IoAllocateMdl</a>

<a href="..\wdm\nf-wdm-iosetnextirpstacklocation.md">IoSetNextIrpStackLocation</a>

<a href="..\wdm\nf-wdm-iofreeirp.md">IoFreeIrp</a>

<a href="..\wdm\ns-wdm-_irp.md">IRP</a>

<a href="..\wdm\nf-wdm-ioreuseirp.md">IoReuseIrp</a>

<a href="..\wdm\nf-wdm-iobuildpartialmdl.md">IoBuildPartialMdl</a>

<a href="..\wdm\nf-wdm-iosizeofirp.md">IoSizeOfIrp</a>

<a href="..\wdm\nf-wdm-iofreemdl.md">IoFreeMdl</a>

<a href="..\wdm\nf-wdm-ioallocateirp.md">IoAllocateIrp</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoInitializeIrp routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

