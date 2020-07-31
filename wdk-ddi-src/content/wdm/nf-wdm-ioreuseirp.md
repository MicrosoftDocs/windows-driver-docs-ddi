---
UID: NF:wdm.IoReuseIrp
title: IoReuseIrp function (wdm.h)
description: The IoReuseIrp routine reinitializes an IRP so that it can be reused.
old-location: kernel\ioreuseirp.htm
tech.root: kernel
ms.assetid: 18ad2c76-110f-45a9-986b-67e7c81f256f
ms.date: 04/30/2018
keywords: ["IoReuseIrp function"]
ms.keywords: IoReuseIrp, IoReuseIrp routine [Kernel-Mode Driver Architecture], k104_548c8bd2-bc09-4ee6-b373-d244f1f11daa.xml, kernel.ioreuseirp, wdm/IoReuseIrp
f1_keywords:
 - "wdm/IoReuseIrp"
 - "IoReuseIrp"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoReuseIrp
targetos: Windows
req.typenames: 
---

# IoReuseIrp function


## -description


The <b>IoReuseIrp</b> routine reinitializes an IRP so that it can be reused.


## -parameters




### -param Irp [in, out]

Pointer to the IRP to be reinitialized for reuse. 


### - Iostatus [in]

Specifies the NTSTATUS value to be set in the IRP after it is reinitialized.


## -remarks



Drivers for Windows 2000 and later versions of Windows use <b>IoReuseIrp</b> to reuse an IRP.

A driver should use <b>IoReuseIrp</b> only on IRPs it previously allocated either as raw memory or with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateirp">IoAllocateIrp</a>. In particular, drivers should not use this routine for IRPs created with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iomakeassociatedirp">IoMakeAssociatedIrp</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuildsynchronousfsdrequest">IoBuildSynchronousFsdRequest</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuildasynchronousfsdrequest">IoBuildAsynchronousFsdRequest</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuilddeviceiocontrolrequest">IoBuildDeviceIoControlRequest</a>. 

See <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/reusing-irps">Reusing IRPs</a> for more details on how to reuse IRPs. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateirp">IoAllocateIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioinitializeirp">IoInitializeIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iomakeassociatedirp">IoMakeAssociatedIrp</a>
 

 

