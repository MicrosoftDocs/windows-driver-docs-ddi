---
UID: NF:ndis.NdisQueryAdapterInstanceName
title: NdisQueryAdapterInstanceName function
author: windows-driver-content
description: The NdisQueryAdapterInstanceName function retrieves the friendly name of a physical NIC or a virtual adapter that the calling protocol driver is bound to.
old-location: netvista\ndisqueryadapterinstancename.htm
old-project: netvista
ms.assetid: bd6fade6-9b9b-4b38-8e53-c70c40c1165f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , A, I, N, NdisQueryAdapterInstanceName, NdisQueryAdapterInstanceName function [Network Drivers Starting with Windows Vista], Q, a, c, d, e, i, m, n, ndis/NdisQueryAdapterInstanceName, netvista.ndisqueryadapterinstancename, p, protocol_ndis_functions_ref_e9e2070d-3b82-43a6-8964-92296de4c896.xml, r, s, t, u, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisQueryAdapterInstanceName
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisQueryAdapterInstanceName function


## -description


The 
  <b>NdisQueryAdapterInstanceName</b> function retrieves the friendly name of a physical NIC or a virtual
  adapter that the calling protocol driver is bound to.


## -syntax


````
NDIS_STATUS NdisQueryAdapterInstanceName(
  _Out_ PNDIS_STRING AdapterInstanceName,
  _In_  NDIS_HANDLE  NdisBindingHandle
);
````


## -parameters




### -param pAdapterInstanceName

TBD


### -param NdisBindingHandle [in]

A handle that identifies the binding to the target physical NIC or virtual adapter of the
     next-lower driver to which the caller is bound. Typically, 
     <i>NdisBindingHandle</i> was returned by the 
     <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function.


#### - AdapterInstanceName [out]

A pointer to a caller-supplied NDIS_STRING type that receives a counted Unicode string. This
     string specifies the friendly name of the interface to which the binding refers. This interface is
     either a physical NIC or a virtual adapter. For Windows 2000 and later, NDIS defines the NDIS_STRING
     type as a 
     <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> type.


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
    <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function to retrieve
    this handle.

<b>NdisQueryAdapterInstanceName</b> allocates memory for the string that specifies the friendly name.
    After the caller finishes using this memory, the caller must call the 
    <a href="..\ndis\nf-ndis-ndisfreememory.md">NdisFreeMemory</a> function to release the
    memory.

Friendly names are intended to help the user quickly and accurately identify a physical NIC or virtual
    adapter--for example, "PCI Ethernet Adapter" and "Virtual Private Networking Adapter" are considered
    friendly names.




## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>



<a href="..\ndis\nf-ndis-ndisfreememory.md">NdisFreeMemory</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisQueryAdapterInstanceName function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

