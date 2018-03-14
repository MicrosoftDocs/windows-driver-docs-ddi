---
UID: NF:ndis.NdisIfDeleteIfStackEntry
title: NdisIfDeleteIfStackEntry function
author: windows-driver-content
description: The NdisIfDeleteIfStackEntry function deletes information about the ordering of two network interfaces in the NDIS interface stack.
old-location: netvista\ndisifdeleteifstackentry.htm
old-project: netvista
ms.assetid: 02b4a485-d44b-458c-89f5-1807500b6db8
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisIfDeleteIfStackEntry, NdisIfDeleteIfStackEntry function [Network Drivers Starting with Windows Vista], ndis/NdisIfDeleteIfStackEntry, net_if_functions_ref_dc4a2189-1dc6-43c5-8cef-baf5907d3d60.xml, netvista.ndisifdeleteifstackentry
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Interfaces_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisIfDeleteIfStackEntry
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisIfDeleteIfStackEntry function


## -description


The 
  <b>NdisIfDeleteIfStackEntry</b> function deletes information about the ordering of two network interfaces in
  the NDIS interface stack.


## -syntax


````
VOID NdisIfDeleteIfStackEntry(
  _In_ NET_IFINDEX HigherLayerIfIndex,
  _In_ NET_IFINDEX LowerLayerIfIndex
);
````


## -parameters




### -param HigherLayerIfIndex [in]

The network interface index for the interface that was higher in the stack table.


### -param LowerLayerIfIndex [in]

The network interface index for the interface that was lower in the stack table.


## -returns



None




## -remarks



NDIS drivers call 
    <b>NdisIfDeleteIfStackEntry</b> to delete a stack entry that was previously added by calling the 
    <a href="..\ndis\nf-ndis-ndisifaddifstackentry.md">NdisIfAddIfStackEntry</a> function. NDIS
    deletes the stack entry from its interface stack table if it finds a matching entry.

NDIS maintains an interface stack table (<i>ifStackTable</i> from 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/overview-of-ndis-network-interfaces">RFC 2863</a>). NDIS provides
    the 
    <b>NdisIfAddIfStackEntry</b> and 
    <b>NdisIfDeleteIfStackEntry</b> functions to add and delete entries in this table.




## -see-also

<a href="..\ndis\nf-ndis-ndisifaddifstackentry.md">NdisIfAddIfStackEntry</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisIfDeleteIfStackEntry function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

