---
UID: NF:ndis.NdisQueryAdapterInstanceName
title: NdisQueryAdapterInstanceName function (ndis.h)
description: The NdisQueryAdapterInstanceName function retrieves the friendly name of a physical NIC or a virtual adapter that the calling protocol driver is bound to.
old-location: netvista\ndisqueryadapterinstancename.htm
tech.root: netvista
ms.assetid: bd6fade6-9b9b-4b38-8e53-c70c40c1165f
ms.date: 05/02/2018
keywords: ["NdisQueryAdapterInstanceName function"]
ms.keywords: NdisQueryAdapterInstanceName, NdisQueryAdapterInstanceName function [Network Drivers Starting with Windows Vista], ndis/NdisQueryAdapterInstanceName, netvista.ndisqueryadapterinstancename, protocol_ndis_functions_ref_e9e2070d-3b82-43a6-8964-92296de4c896.xml
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisQueryAdapterInstanceName   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisQueryAdapterInstanceName   (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisQueryAdapterInstanceName
 - ndis/NdisQueryAdapterInstanceName
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisQueryAdapterInstanceName
---

# NdisQueryAdapterInstanceName function


## -description

The 
  <b>NdisQueryAdapterInstanceName</b> function retrieves the friendly name of a physical NIC or a virtual
  adapter that the calling protocol driver is bound to.

## -parameters

### -param pAdapterInstanceName

A pointer to a caller-supplied NDIS_STRING type that receives a counted Unicode string. This
     string specifies the friendly name of the interface to which the binding refers. This interface is
     either a physical NIC or a virtual adapter. For Windows 2000 and later, NDIS defines the NDIS_STRING
     type as a 
     <a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> type.

### -param NdisBindingHandle 

[in]
A handle that identifies the binding to the target physical NIC or virtual adapter of the
     next-lower driver to which the caller is bound. Typically, 
     <i>NdisBindingHandle</i> was returned by the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a> function.

## -returns

<b>NdisQueryAdapterInstanceName</b> returns NDIS_STATUS_SUCCESS if memory for the string at 
     <i>AdapterInstanceName</i> was successfully allocated; otherwise, it returns
     NDIS_STATUS_RESOURCES.

## -remarks

A protocol driver uses 
    <b>NdisQueryAdapterInstanceName</b> to retrieve the friendly name of a physical NIC or a virtual adapter
    to which the protocol driver is bound. The protocol driver specifies the handle to such a NIC or virtual
    adapter in 
    <i>NdisBindingHandle</i> . The protocol driver calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a> function to retrieve
    this handle.

<b>NdisQueryAdapterInstanceName</b> allocates memory for the string that specifies the friendly name.
    After the caller finishes using this memory, the caller must call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreememory">NdisFreeMemory</a> function to release the
    memory.

Friendly names are intended to help the user quickly and accurately identify a physical NIC or virtual
    adapter--for example, "PCI Ethernet Adapter" and "Virtual Private Networking Adapter" are considered
    friendly names.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreememory">NdisFreeMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>

