---
UID: NF:wdm.IoGetDmaAdapter
title: IoGetDmaAdapter function (wdm.h)
description: The IoGetDmaAdapter routine returns a pointer to the DMA adapter structure for a physical device object.
old-location: kernel\iogetdmaadapter.htm
tech.root: kernel
ms.assetid: fa108ef4-54b8-4c6a-9d77-25e6b9e2c09d
ms.date: 04/30/2018
keywords: ["IoGetDmaAdapter function"]
ms.keywords: IoGetDmaAdapter, IoGetDmaAdapter routine [Kernel-Mode Driver Architecture], k104_36398d16-2a22-4a85-a260-265aa9c54bbd.xml, kernel.iogetdmaadapter, wdm/IoGetDmaAdapter
f1_keywords:
 - "wdm/IoGetDmaAdapter"
 - "IoGetDmaAdapter"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoGetDmaAdapter
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoGetDmaAdapter function


## -description


The <b>IoGetDmaAdapter</b> routine returns a pointer to the DMA adapter structure for a physical device object.


## -parameters




### -param PhysicalDeviceObject [in, optional]

Pointer to the physical device object for the device requesting the DMA adapter structure.


### -param DeviceDescription [in]

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_description">DEVICE_DESCRIPTION</a> structure, which describes the attributes of the physical device. Regardless of the version set in the DEVICE_DESCRIPTION structure, this function always returns `DMA_ADAPTER->Version == 1`.


### -param NumberOfMapRegisters [out]

A pointer to, on output, the maximum number of map registers that the driver can allocate for any DMA transfer operation. 


## -returns



<b>IoGetDmaAdapter</b> returns a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a> structure, which contains pointers to functions that support system-defined DMA operations. If the structure cannot be allocated, the routine returns <b>NULL</b>.  See version comment above in description of *DeviceDescription* parameter.




## -remarks



Before calling this routine, a driver must zero-initialize the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_description">DEVICE_DESCRIPTION</a> structure pointed to by <i>DeviceDescription</i> and then add the relevant information for its device to this structure.

On success, the <b>DmaOperations</b> member of the routine's return value points to a <b>DMA_ADAPTER</b> structure. This structure contains a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a> structure, which is a table of pointers to functions that the driver can subsequently use to perform DMA operations. The version of this structure that the routine returns is determined as follows:

<ul>
<li> If the driver sets the <b>Version</b> member of the <b>DEVICE_DESCRIPTION</b> structure to DEVICE_DESCRIPTION_VERSION or DEVICE_DESCRIPTION_VERSION1, the returned <b>DMA_ADAPTER</b> structure points to version 1 of the <b>DMA_OPERATIONS</b> structure.</li>
<li> If the driver sets <b>Version</b> = DEVICE_DESCRIPTION_VERSION2, the returned <b>DMA_ADAPTER</b> structure points to version 2 of the <b>DMA_OPERATIONS</b> structure if version 2 is supported; otherwise, the routine returns <b>NULL</b>. Drivers must check to see if version 2 is supported before attempting to use any version 2 function.</li>
<li>If the driver sets <b>Version</b> = DEVICE_DESCRIPTION_VERSION3, the returned <b>DMA_ADAPTER</b> structure points to version 3 of the <b>DMA_OPERATIONS</b> structure if version 3 is supported; otherwise, the routine returns <b>NULL</b>. Drivers must check to see if version 3 is supported before attempting to use any version 3 function. Version 3 is supported starting with Windows 8.</li>
</ul>
A PnP driver calls <b>IoGetDmaAdapter</b> when its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a> routine is called or when it handles a PnP <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-start-device">IRP_MN_START_DEVICE</a> request for a device. This IRP includes information about the device's hardware resources that the driver must supply in the <i>DeviceDescription</i> structure.

The caller uses the <b>MaximumLength</b> member in the <i>DeviceDescription</i> structure to indicate the optimal number of map registers it can use. The I/O manager will attempt to allocate enough map registers to accommodate a DMA transfer operation of this maximum size. On output, the I/O manager returns, in the <i>NumberOfMapRegisters</i> parameter, the number of map registers that it allocates. Drivers should check the returned value; there is no guarantee a driver will receive the same number of map registers it requested.

To free the adapter object, the driver should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pput_dma_adapter">PutDmaAdapter</a> through the pointer returned in the <b>DMA_ADAPTER</b> structure.

<div class="alert"><b>Note</b>  As previously described, <b>IoGetDmaAdapter</b> returns <b>NULL</b> if it does not support the version of the <b>DMA_ADAPTER</b> structure that is specified by <i>DeviceDescription-</i>&gt;<b>Version</b>. Callers should rely on this behavior to determine whether the routine returns a pointer to the requested version of the <b>DMA_ADAPTER</b> structure. When <b>IoGetDmaAdapter</b> returns a pointer to version 1 or version 2 or version 3 of the <b>DMA_ADAPTER</b> structure, the <b>Version</b> member of this structure is always set to 1. Thus, the caller cannot use the <b>Version</b> member of the returned <b>DMA_ADAPTER</b> structure to distinguish between versions 1, 2 and 3 of this structure.</div>

<div> </div>

## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_description">DEVICE_DESCRIPTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-start-device">IRP_MN_START_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pput_dma_adapter">PutDmaAdapter</a>
 

 

