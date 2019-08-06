---
UID: NF:ndis.NdisCompleteUnbindAdapterEx
title: NdisCompleteUnbindAdapterEx function (ndis.h)
description: A protocol driver calls the NdisCompleteUnbindAdapterEx function to complete an unbind operation for which the driver's ProtocolUnbindAdapterEx function returned NDIS_STATUS_PENDING.
old-location: netvista\ndiscompleteunbindadapterex.htm
tech.root: netvista
ms.assetid: 3a1daad4-d4b7-4950-be58-73612949fba9
ms.date: 05/02/2018
ms.keywords: NdisCompleteUnbindAdapterEx, NdisCompleteUnbindAdapterEx function [Network Drivers Starting with Windows Vista], ndis/NdisCompleteUnbindAdapterEx, netvista.ndiscompleteunbindadapterex, protocol_ndis_functions_ref_3d1252b7-d653-4bd6-a105-b998ffed694c.xml
ms.topic: function
f1_keywords:
 - "ndis/NdisCompleteUnbindAdapterEx"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Protocol_Driver_Function
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
- NdisCompleteUnbindAdapterEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisCompleteUnbindAdapterEx function


## -description


A protocol driver calls the 
  <b>NdisCompleteUnbindAdapterEx</b> function to complete an unbind operation for which the driver's 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_unbind_adapter_ex">ProtocolUnbindAdapterEx</a> function
  returned NDIS_STATUS_PENDING.


## -parameters




### -param UnbindContext [in]

The handle that NDIS passed to the 
     <i>UnbindContext</i> parameter of the 
     <i>ProtocolUnbindAdapterEx</i> function.


## -returns



None




## -remarks



When a protocol driver returns NDIS_STATUS_PENDING from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_unbind_adapter_ex">
    ProtocolUnbindAdapterEx</a> function, that driver must call 
    <b>NdisCompleteUnbindAdapterEx</b> after the unbind operation is completed.

When the driver calls 
    <b>NdisCompleteUnbindAdapterEx</b>, the driver has finished cleaning up any per-binding context
    information that the driver maintains for the binding, and released any resources that it allocated to
    establish the binding.

On return from 
    <b>NdisCompleteUnbindAdapterEx</b> the 
    <i>UnbindContext</i> handle is invalid. That is, the protocol driver should not pass this handle in calls
    to any 
    <b>Ndis<i>Xxx</i></b> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_unbind_adapter_ex">ProtocolUnbindAdapterEx</a>
 

 

