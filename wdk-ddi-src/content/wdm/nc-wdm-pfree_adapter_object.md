---
UID: NC:wdm.PFREE_ADAPTER_OBJECT
title: PFREE_ADAPTER_OBJECT (wdm.h)
description: The FreeAdapterObject routine releases the specified adapter object after a driver has completed all DMA operations.
old-location: kernel\freeadapterobject.htm
tech.root: kernel
ms.assetid: 4A63AAEF-8DBD-4969-8D05-EA06A17D4B61
ms.date: 04/30/2018
ms.keywords: FreeAdapterObject, FreeAdapterObject callback function [Kernel-Mode Driver Architecture], PFREE_ADAPTER_OBJECT, PFREE_ADAPTER_OBJECT callback, kernel.freeadapterobject, wdm/FreeAdapterObject
ms.topic: callback
f1_keywords:
 - "wdm/FreeAdapterObject"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdm.h
api_name:
- FreeAdapterObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFREE_ADAPTER_OBJECT callback function


## -description


The  <b>FreeAdapterObject</b> routine releases the specified adapter object after a driver has completed all DMA operations.


## -parameters




### -param DmaAdapter [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a> structure. This structure is the adapter object that is to be released. This object represents the driver's bus-master DMA device or system DMA channel. The caller obtained this pointer from a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> routine.


### -param AllocationAction [in]

The type of deallocation that the calling driver requests. Set this parameter to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_io_allocation_action">IO_ALLOCATION_ACTION</a> enumeration value. For more information, see the Remarks section.


## -returns



None




## -remarks



<b>FreeAdapterObject</b>
      is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a>
      structure. Drivers obtain the address of this routine by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION3. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

If <i>AllocationAction</i> = <b>DeallocateObject</b>, the <b>FreeAdapterObject</b> call releases the adapter object, and releases any map registers that might be allocated for this object.

If <i>AllocationAction</i> = <b>DeallocateObjectKeepRegisters</b>, the <b>FreeAdapterObject</b> call releases the adapter object, but does not release any map registers. In this case, the driver must explicitly release any allocated map registers by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-pfree_map_registers">FreeMapRegisters</a> routine.

If <i>AllocationAction</i> = <b>KeepObject</b>, the <b>FreeAdapterObject</b> call has no effect.

<b>FreeAdapterObject</b> can be used to deallocate DMA resources that are allocated by calls to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-pallocate_adapter_channel_ex">AllocateAdapterChannelEx</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-pget_scatter_gather_list_ex">GetScatterGatherListEx</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-pbuild_scatter_gather_list_ex">BuildScatterGatherListEx</a> routines. If the driver calls one of these routines synchronously, the <i>ExecutionRoutine</i> parameter is optional and can be omitted. In this case, the driver can use the adapter object and map registers that are allocated by the call. After the driver initiates the DMA transfer, the driver can call <b>FreeAdapterObject</b> to deallocate the adapter object and, if necessary, the map registers.

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-pfree_adapter_channel">FreeAdapterChannel</a> routine is similar to <b>FreeAdapterObject</b>. <b>FreeAdapterChannel</b> always releases the adapter object and any allocated map registers. This behavior is similar to that of <b>FreeAdapterObject</b> if <i>AllocationAction</i> = <b>DeallocateObject</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-driver_control">AdapterControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-driver_list_control">AdapterListControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-pallocate_adapter_channel">AllocateAdapterChannel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-pallocate_adapter_channel_ex">AllocateAdapterChannelEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-pbuild_scatter_gather_list_ex">BuildScatterGatherListEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-pfree_adapter_channel">FreeAdapterChannel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-pfree_map_registers">FreeMapRegisters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-pget_scatter_gather_list_ex">GetScatterGatherListEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_io_allocation_action">IO_ALLOCATION_ACTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>
 

 

