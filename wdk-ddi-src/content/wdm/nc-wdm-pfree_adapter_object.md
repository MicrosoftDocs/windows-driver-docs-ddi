---
UID: NC:wdm.PFREE_ADAPTER_OBJECT
title: PFREE_ADAPTER_OBJECT
author: windows-driver-content
description: The FreeAdapterObject routine releases the specified adapter object after a driver has completed all DMA operations.
old-location: kernel\freeadapterobject.htm
old-project: kernel
ms.assetid: 4A63AAEF-8DBD-4969-8D05-EA06A17D4B61
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.freeadapterobject, FreeAdapterObject, FreeAdapterObject callback function [Kernel-Mode Driver Architecture], FreeAdapterObject, PFREE_ADAPTER_OBJECT, PFREE_ADAPTER_OBJECT, wdm/FreeAdapterObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdm.h
apiname:
-	FreeAdapterObject
product: Windows
targetos: Windows
req.typenames: "*PWDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME"
req.product: Windows 10 or later.
---

# PFREE_ADAPTER_OBJECT callback


## -description


The  <b>FreeAdapterObject</b> routine releases the specified adapter object after a driver has completed all DMA operations.


## -prototype


````
PFREE_ADAPTER_OBJECT FreeAdapterObject;

VOID FreeAdapterObject(
  _In_ PDMA_ADAPTER         DmaAdapter,
  _In_ IO_ALLOCATION_ACTION AllocationAction
)
{ ... }
````


## -parameters




### -param DmaAdapter [in]

A pointer to a <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure. This structure is the adapter object that is to be released. This object represents the driver's bus-master DMA device or system DMA channel. The caller obtained this pointer from a previous call to the <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a> routine.


### -param AllocationAction [in]

The type of deallocation that the calling driver requests. Set this parameter to an <a href="..\wdm\ne-wdm-_io_allocation_action.md">IO_ALLOCATION_ACTION</a> enumeration value. For more information, see the Remarks section.


## -returns



None




## -remarks



<b>FreeAdapterObject</b>
      is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a 
     <a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>
      structure. Drivers obtain the address of this routine by calling <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION3. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

If <i>AllocationAction</i> = <b>DeallocateObject</b>, the <b>FreeAdapterObject</b> call releases the adapter object, and releases any map registers that might be allocated for this object.

If <i>AllocationAction</i> = <b>DeallocateObjectKeepRegisters</b>, the <b>FreeAdapterObject</b> call releases the adapter object, but does not release any map registers. In this case, the driver must explicitly release any allocated map registers by calling the <a href="..\wdm\nc-wdm-pfree_map_registers.md">FreeMapRegisters</a> routine.

If <i>AllocationAction</i> = <b>KeepObject</b>, the <b>FreeAdapterObject</b> call has no effect.

<b>FreeAdapterObject</b> can be used to deallocate DMA resources that are allocated by calls to the <a href="..\wdm\nc-wdm-pallocate_adapter_channel_ex.md">AllocateAdapterChannelEx</a>, <a href="..\wdm\nc-wdm-pget_scatter_gather_list_ex.md">GetScatterGatherListEx</a>, and <a href="..\wdm\nc-wdm-pbuild_scatter_gather_list_ex.md">BuildScatterGatherListEx</a> routines. If the driver calls one of these routines synchronously, the <i>ExecutionRoutine</i> parameter is optional and can be omitted. In this case, the driver can use the adapter object and map registers that are allocated by the call. After the driver initiates the DMA transfer, the driver can call <b>FreeAdapterObject</b> to deallocate the adapter object and, if necessary, the map registers.

The <a href="..\wdm\nc-wdm-pfree_adapter_channel.md">FreeAdapterChannel</a> routine is similar to <b>FreeAdapterObject</b>. <b>FreeAdapterChannel</b> always releases the adapter object and any allocated map registers. This behavior is similar to that of <b>FreeAdapterObject</b> if <i>AllocationAction</i> = <b>DeallocateObject</b>.




## -see-also

<a href="..\wdm\nc-wdm-driver_list_control.md">AdapterListControl</a>



<a href="..\wdm\nc-wdm-pallocate_adapter_channel.md">AllocateAdapterChannel</a>



<a href="..\wdm\nc-wdm-driver_control.md">AdapterControl</a>



<a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a>



<a href="..\wdm\nc-wdm-pbuild_scatter_gather_list_ex.md">BuildScatterGatherListEx</a>



<a href="..\wdm\ns-wdm-_dma_adapter_info.md">DMA_ADAPTER</a>



<a href="..\wdm\nc-wdm-pget_scatter_gather_list_ex.md">GetScatterGatherListEx</a>



<a href="..\wdm\nc-wdm-pfree_map_registers.md">FreeMapRegisters</a>



<a href="..\wdm\nc-wdm-pfree_adapter_channel.md">FreeAdapterChannel</a>



<a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>



<a href="..\wdm\ne-wdm-_io_allocation_action.md">IO_ALLOCATION_ACTION</a>



<a href="..\wdm\nc-wdm-pallocate_adapter_channel_ex.md">AllocateAdapterChannelEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PFREE_ADAPTER_OBJECT callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

