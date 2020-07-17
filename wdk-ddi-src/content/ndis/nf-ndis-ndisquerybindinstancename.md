---
UID: NF:ndis.NdisQueryBindInstanceName
title: NdisQueryBindInstanceName function (ndis.h)
description: The NdisQueryBindInstanceName function retrieves the friendly name of a physical NIC or a virtual adapter that the calling protocol driver will bind to.
old-location: netvista\ndisquerybindinstancename.htm
tech.root: netvista
ms.assetid: bbba8be8-aa7e-455f-a591-e9d915f137f4
ms.date: 05/02/2018
keywords: ["NdisQueryBindInstanceName function"]
ms.keywords: NdisQueryBindInstanceName, NdisQueryBindInstanceName function [Network Drivers Starting with Windows Vista], ndis/NdisQueryBindInstanceName, netvista.ndisquerybindinstancename, protocol_ndis_functions_ref_96d4e502-200e-4ad5-b66d-6de612a0b7f9.xml
f1_keywords:
 - "ndis/NdisQueryBindInstanceName"
 - "NdisQueryBindInstanceName"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisQueryBindInstanceName (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisQueryBindInstanceName (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: NdisQueryBindInstanceName
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
- NdisQueryBindInstanceName
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisQueryBindInstanceName function


## -description


The 
  <b>NdisQueryBindInstanceName</b> function retrieves the friendly name of a physical NIC or a virtual adapter
  that the calling protocol driver will bind to.


## -parameters




### -param pAdapterInstanceName [out]

A pointer to a caller-supplied NDIS_STRING type that receives a counted Unicode string. This
     string specifies the friendly name of the interface to which the binding refers. This interface is
     either a physical NIC or a virtual adapter. For Microsoft Windows 2000 and later operating systems, NDIS
     defines the NDIS_STRING type as a 
     <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> type.


### -param BindingContext [in]

A handle that identifies the NDIS context area for the bind operation. NDIS passed this handle to
     the 
     <i>BindContext</i> parameter of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">
     ProtocolBindAdapterEx</a> function.


## -returns



<b>NdisQueryBindInstanceName</b> returns NDIS_STATUS_SUCCESS if memory for the string at 
     <i>pAdapterInstanceName</i> was successfully allocated; otherwise, it returns
     NDIS_STATUS_RESOURCES.




## -remarks



A protocol driver uses 
    <b>NdisQueryBindInstanceName</b> to retrieve the friendly name of a physical NIC or a virtual adapter to
    which the protocol driver will be bound. The protocol driver specifies the binding context that NDIS
    provided in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">
    ProtocolBindAdapterEx</a> function.

Protocol drivers can use 
    <b>NdisQueryBindInstanceName</b> to obtain the friendly name before they bind to the adapter.

<b>NdisQueryBindInstanceName</b> allocates memory for the string that specifies the friendly name. After
    the caller finishes using this memory, the caller must call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreememory">NdisFreeMemory</a> function to release the
    memory.

Friendly names are intended to help the user quickly and accurately identify a physical NIC or virtual
    adapter--for example, "PCI Ethernet Adapter" and "Virtual Private Networking Adapter" are considered
    friendly names.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreememory">NdisFreeMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

