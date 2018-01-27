---
UID: NF:wdm.IoReuseIrp
title: IoReuseIrp function
author: windows-driver-content
description: The IoReuseIrp routine reinitializes an IRP so that it can be reused.
old-location: kernel\ioreuseirp.htm
old-project: kernel
ms.assetid: 18ad2c76-110f-45a9-986b-67e7c81f256f
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoReuseIrp routine [Kernel-Mode Driver Architecture], IoReuseIrp, wdm/IoReuseIrp, k104_548c8bd2-bc09-4ee6-b373-d244f1f11daa.xml, kernel.ioreuseirp
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
req.irql: <=DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	IoReuseIrp
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoReuseIrp function


## -description


The <b>IoReuseIrp</b> routine reinitializes an IRP so that it can be reused.


## -syntax


````
VOID IoReuseIrp(
  _Inout_ PIRP     Irp,
  _In_    NTSTATUS Status
);
````


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

A driver should use <b>IoReuseIrp</b> only on IRPs it previously allocated either as raw memory or with <a href="..\wdm\nf-wdm-ioallocateirp.md">IoAllocateIrp</a>. In particular, drivers should not use this routine for IRPs created with <a href="..\ntddk\nf-ntddk-iomakeassociatedirp.md">IoMakeAssociatedIrp</a>, <a href="..\wdm\nf-wdm-iobuildsynchronousfsdrequest.md">IoBuildSynchronousFsdRequest</a>, <a href="..\wdm\nf-wdm-iobuildasynchronousfsdrequest.md">IoBuildAsynchronousFsdRequest</a>, or <a href="..\wdm\nf-wdm-iobuilddeviceiocontrolrequest.md">IoBuildDeviceIoControlRequest</a>. 

See <a href="https://msdn.microsoft.com/library/windows/hardware/ff561107">Reusing IRPs</a> for more details on how to reuse IRPs. 



## -see-also

<a href="..\wdm\nf-wdm-ioallocateirp.md">IoAllocateIrp</a>

<a href="..\ntddk\nf-ntddk-iomakeassociatedirp.md">IoMakeAssociatedIrp</a>

<a href="..\wdm\ns-wdm-_irp.md">IRP</a>

<a href="..\wdm\nf-wdm-ioinitializeirp.md">IoInitializeIrp</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoReuseIrp routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

