---
UID: NF:ndis.NdisIfDeleteIfStackEntry
title: NdisIfDeleteIfStackEntry function
author: windows-driver-content
description: The NdisIfDeleteIfStackEntry function deletes information about the ordering of two network interfaces in the NDIS interface stack.
old-location: netvista\ndisifdeleteifstackentry.htm
tech.root: netvista
ms.assetid: 02b4a485-d44b-458c-89f5-1807500b6db8
ms.author: windowsdriverdev
ms.date: 5/2/2018
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisIfDeleteIfStackEntry function


## -description


The 
  <b>NdisIfDeleteIfStackEntry</b> function deletes information about the ordering of two network interfaces in
  the NDIS interface stack.


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
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562693">NdisIfAddIfStackEntry</a> function. NDIS
    deletes the stack entry from its interface stack table if it finds a matching entry.

NDIS maintains an interface stack table (<i>ifStackTable</i> from 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/overview-of-ndis-network-interfaces">RFC 2863</a>). NDIS provides
    the 
    <b>NdisIfAddIfStackEntry</b> and 
    <b>NdisIfDeleteIfStackEntry</b> functions to add and delete entries in this table.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562693">NdisIfAddIfStackEntry</a>
 

 

