---
UID: NF:ndis.NdisAllocateIoWorkItem
title: NdisAllocateIoWorkItem function (ndis.h)
description: NDIS drivers call the NdisAllocateIoWorkItem function to allocate a work item. For more information, see NDIS I/O Work Items.
old-location: netvista\ndisallocateioworkitem.htm
tech.root: netvista
ms.assetid: 54977838-381e-4c86-a6ca-646202fdc619
ms.date: 05/02/2018
keywords: ["NdisAllocateIoWorkItem function"]
ms.keywords: NdisAllocateIoWorkItem, NdisAllocateIoWorkItem function [Network Drivers Starting with Windows Vista], ndis/NdisAllocateIoWorkItem, ndis_work_items_ref_c227456a-4847-40db-b530-a772f4fd4dc3.xml, netvista.ndisallocateioworkitem
f1_keywords:
 - "ndis/NdisAllocateIoWorkItem"
 - "NdisAllocateIoWorkItem"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Init_NdisAllocateIoWorkItem, Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisAllocateIoWorkItem
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisAllocateIoWorkItem function


## -description


NDIS drivers call the 
  <b>NdisAllocateIoWorkItem</b> function to allocate a work item. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-i-o-work-items">NDIS I/O Work Items</a>.


## -parameters




### -param NdisObjectHandle [in]

The handle of an NDIS object that is associated with a device object or driver object.


## -returns



If 
     <b>NdisAllocateIoWorkItem</b> successfully allocates a work item, it returns a handle to the work item.
     If it fails, 
     <b>NdisAllocateIoWorkItem</b> returns <b>NULL</b>.




## -remarks



NDIS miniport drivers pass 
    <b>NdisAllocateIoWorkItem</b> either of two handles: the adapter handle that NDIS passed to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function or
    the miniport driver handle that NDIS returned when the miniport driver called 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">
    NdisMRegisterMiniportDriver</a>.

NDIS filter drivers can pass 
    <b>NdisAllocateIoWorkItem</b> the filter driver handle that NDIS returned when the filter driver called 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfregisterfilterdriver">NdisFRegisterFilterDriver</a>.

NDIS miniport drivers and filter drivers can also pass 
    <b>NdisAllocateIoWorkItem</b> the NDIS device handle that NDIS returned when the driver called 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterdeviceex">NdisRegisterDeviceEx</a>. 
    <b>NdisAllocateIoWorkItem</b> gets the device object or driver object that is associated with the handle
    and passes the device object or driver object to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateworkitem">IoAllocateWorkItem</a> function.

<div class="alert"><b>Note</b>  Protocol drivers cannot use 
    <b>NdisAllocateIoWorkItem</b> because NDIS does not associate protocol drivers with device objects or
    driver objects.</div>
<div> </div>
NDIS drivers call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisqueueioworkitem">NdisQueueIoWorkItem</a> function to queue
    work items. After a driver calls 
    <b>NdisQueueIoWorkItem</b>, NDIS calls the driver-specified callback function at IRQL = PASSIVE_LEVEL.
    This can improve system performance by allowing the current function to end immediately and the driver to
    do work later at a lower IRQL.

NDIS drivers must call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreeioworkitem">NdisFreeIoWorkItem</a> function to free the
    resources associated with a work item that 
    <b>NdisAllocateIoWorkItem</b> allocated.

Drivers can call
    <b>NdisFreeIoWorkItem</b> in the callback routine that is passed to 
    <b>NdisQueueIoWorkItem</b>.

If a miniport driver used the handle that NDIS passed to 
    <i>MiniportInitializeEx</i> when it called 
    <b>NdisAllocateIoWorkItem</b>, the work item must be freed before or in the call to the drivers 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a> function.

If a miniport driver used the handle that 
    <b>NdisMRegisterMiniportDriver</b> returned when the driver called 
    <b>NdisAllocateIoWorkItem</b>, the driver must free the work item before the driver unloads.

In general, a driver must free the work item before the driver unloads.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateworkitem">IoAllocateWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-i-o-work-items">NDIS I/O Work Items</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfregisterfilterdriver">NdisFRegisterFilterDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreeioworkitem">NdisFreeIoWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisqueueioworkitem">NdisQueueIoWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterdeviceex">NdisRegisterDeviceEx</a>
 

 

