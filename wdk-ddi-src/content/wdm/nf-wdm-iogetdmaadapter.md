---
UID: NF:wdm.IoGetDmaAdapter
title: IoGetDmaAdapter function
author: windows-driver-content
description: The IoGetDmaAdapter routine returns a pointer to the DMA adapter structure for a physical device object.
old-location: kernel\iogetdmaadapter.htm
old-project: kernel
ms.assetid: fa108ef4-54b8-4c6a-9d77-25e6b9e2c09d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , A, D, G, I, IoGetDmaAdapter, IoGetDmaAdapter routine [Kernel-Mode Driver Architecture], a, d, e, k104_36398d16-2a22-4a85-a260-265aa9c54bbd.xml, kernel.iogetdmaadapter, m, o, p, r, t, wdm/IoGetDmaAdapter"
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
req.ddi-compliance: IrqlIoPassive5, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoGetDmaAdapter
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoGetDmaAdapter function


## -description


The <b>IoGetDmaAdapter</b> routine returns a pointer to the DMA adapter structure for a physical device object.


## -syntax


````
struct _DMA_ADAPTER* IoGetDmaAdapter(
  _In_opt_ PDEVICE_OBJECT             PhysicalDeviceObject,
  _In_     struct _DEVICE_DESCRIPTION *DeviceDescription,
  _Out_    PULONG                     NumberOfMapRegisters
);
````


## -parameters




### -param PhysicalDeviceObject [in, optional]

Pointer to the physical device object for the device requesting the DMA adapter structure.


### -param DeviceDescription [in]

Pointer to a <a href="..\wdm\ns-wdm-_device_description.md">DEVICE_DESCRIPTION</a> structure, which describes the attributes of the physical device. 


### -param NumberOfMapRegisters [out]

A pointer to, on output, the maximum number of map registers that the driver can allocate for any DMA transfer operation. 


## -returns



<b>IoGetDmaAdapter</b> returns a pointer to a <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure, which contains pointers to functions that support system-defined DMA operations. If the structure cannot be allocated, the routine returns <b>NULL</b>. 




## -remarks



Before calling this routine, a driver must zero-initialize the <a href="..\wdm\ns-wdm-_device_description.md">DEVICE_DESCRIPTION</a> structure pointed to by <i>DeviceDescription</i> and then add the relevant information for its device to this structure.

On success, the <b>DmaOperations</b> member of the routine's return value points to a <b>DMA_ADAPTER</b> structure. This structure contains a pointer to a <a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a> structure, which is a table of pointers to functions that the driver can subsequently use to perform DMA operations. The version of this structure that the routine returns is determined as follows:

<ul>
<li> If the driver sets the <b>Version</b> member of the <b>DEVICE_DESCRIPTION</b> structure to DEVICE_DESCRIPTION_VERSION or DEVICE_DESCRIPTION_VERSION1, the returned <b>DMA_ADAPTER</b> structure points to version 1 of the <b>DMA_OPERATIONS</b> structure.</li>
<li> If the driver sets <b>Version</b> = DEVICE_DESCRIPTION_VERSION2, the returned <b>DMA_ADAPTER</b> structure points to version 2 of the <b>DMA_OPERATIONS</b> structure if version 2 is supported; otherwise, the routine returns <b>NULL</b>. Drivers must check to see if version 2 is supported before attempting to use any version 2 function.</li>
<li>If the driver sets <b>Version</b> = DEVICE_DESCRIPTION_VERSION3, the returned <b>DMA_ADAPTER</b> structure points to version 3 of the <b>DMA_OPERATIONS</b> structure if version 3 is supported; otherwise, the routine returns <b>NULL</b>. Drivers must check to see if version 3 is supported before attempting to use any version 3 function. Version 3 is supported starting with Windows 8.</li>
</ul>
A PnP driver calls <b>IoGetDmaAdapter</b> when its <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> routine is called or when it handles a PnP <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a> request for a device. This IRP includes information about the device's hardware resources that the driver must supply in the <i>DeviceDescription</i> structure.

The caller uses the <b>MaximumLength</b> member in the <i>DeviceDescription</i> structure to indicate the optimal number of map registers it can use. The I/O manager will attempt to allocate enough map registers to accommodate a DMA transfer operation of this maximum size. On output, the I/O manager returns, in the <i>NumberOfMapRegisters</i> parameter, the number of map registers that it allocates. Drivers should check the returned value; there is no guarantee a driver will receive the same number of map registers it requested.

To free the adapter object, the driver should call <a href="..\wdm\nc-wdm-pput_dma_adapter.md">PutDmaAdapter</a> through the pointer returned in the <b>DMA_ADAPTER</b> structure.

<div class="alert"><b>Note</b>  As previously described, <b>IoGetDmaAdapter</b> returns <b>NULL</b> if it does not support the version of the <b>DMA_ADAPTER</b> structure that is specified by <i>DeviceDescription-</i>&gt;<b>Version</b>. Callers should rely on this behavior to determine whether the routine returns a pointer to the requested version of the <b>DMA_ADAPTER</b> structure. When <b>IoGetDmaAdapter</b> returns a pointer to version 1 or version 2 of the <b>DMA_ADAPTER</b> structure, the <b>Version</b> member of this structure is always set to 1. Thus, the caller cannot use the <b>Version</b> member of the returned <b>DMA_ADAPTER</b> structure to distinguish between versions 1 and 2 of this structure.</div>
<div> </div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a>



<a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>



<a href="..\wdm\nc-wdm-pput_dma_adapter.md">PutDmaAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a>



<a href="..\wdm\ns-wdm-_device_description.md">DEVICE_DESCRIPTION</a>



<a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoGetDmaAdapter routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

