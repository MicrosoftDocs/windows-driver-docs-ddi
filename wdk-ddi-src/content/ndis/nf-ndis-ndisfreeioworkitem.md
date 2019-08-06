---
UID: NF:ndis.NdisFreeIoWorkItem
title: NdisFreeIoWorkItem function (ndis.h)
description: NDIS drivers call the NdisFreeIoWorkItem function to free a specified work item.
old-location: netvista\ndisfreeioworkitem.htm
tech.root: netvista
ms.assetid: ddc2f96b-fa2c-43c1-960f-7f8e06a5b22d
ms.date: 05/02/2018
ms.keywords: NdisFreeIoWorkItem, NdisFreeIoWorkItem function [Network Drivers Starting with Windows Vista], ndis/NdisFreeIoWorkItem, ndis_work_items_ref_50b3859f-f34b-4cae-b7ef-935f1aae82cb.xml, netvista.ndisfreeioworkitem
ms.topic: function
f1_keywords:
 - "ndis/NdisFreeIoWorkItem"
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
- NdisFreeIoWorkItem
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFreeIoWorkItem function


## -description


NDIS drivers call the
  <b>NdisFreeIoWorkItem</b> function to free a specified work item.


## -parameters




### -param NdisIoWorkItemHandle [in]

A handle to a private <b>NDIS_IO_WORKITEM</b> structure that was returned by a previous call to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisallocateioworkitem">
     NdisAllocateIoWorkItem</a> function.


## -returns



None




## -remarks



<b>NdisFreeIoWorkItem</b> calls 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iofreeworkitem">IoFreeWorkItem</a> to free the structure that is
    specified by the
    <i>NdisIoWorkItemHandle</i> parameter.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iofreeworkitem">IoFreeWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-i-o-work-items">NDIS I/O Work Items</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisallocateioworkitem">NdisAllocateIoWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisqueueioworkitem">NdisQueueIoWorkItem</a>
 

 

