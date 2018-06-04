---
UID: NF:ndis.NdisMQueryAdapterInstanceName
title: NdisMQueryAdapterInstanceName function
author: windows-driver-content
description: The NdisMQueryAdapterInstanceName function retrieves the friendly name of a miniport adapter.
old-location: netvista\ndismqueryadapterinstancename.htm
old-project: netvista
ms.assetid: 7af6ee73-814b-49f8-8641-d3e8dc672ee5
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NdisMQueryAdapterInstanceName, NdisMQueryAdapterInstanceName function [Network Drivers Starting with Windows Vista], miniport_ndis_functions_ref_5e04ebd4-3db8-4cb2-a75c-ce67d938804c.xml, ndis/NdisMQueryAdapterInstanceName, netvista.ndismqueryadapterinstancename
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 5.1, and NDIS 6.0 and later. For NDIS 5.1 drivers, see       NdisMQueryAdapterInstanceName (NDIS 5.1).
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miniport_Driver_Function
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
-	NdisMQueryAdapterInstanceName
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMQueryAdapterInstanceName function


## -description


The
  <b>NdisMQueryAdapterInstanceName</b> function retrieves the friendly name of a miniport adapter.


## -parameters




### -param pAdapterInstanceName

A pointer to a caller-supplied NDIS_STRING type that receives a counted Unicode string. This
     string specifies the friendly name of the interface for the given miniport adapter. For Windows Vista
     and later versions of the Windows operating system, NDIS defines the NDIS_STRING type as a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> type.

### -param MiniportHandle

The handle to the miniport adapter that was previously input to the 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">
     MiniportInitializeEx</a> function.

## -returns



Returns NDIS_STATUS_SUCCESS if memory for the string at 
     <i>AdapterInstanceName</i> was successfully allocated; otherwise, it returns
     NDIS_STATUS_RESOURCES.




## -remarks



A miniport driver uses 
    <b>NdisMQueryAdapterInstanceName</b> to retrieve the friendly name of an interface that the miniport
    driver controls. This interface is either a physical NIC or a virtual adapter and is called a 
    <i>miniport adapter</i>. The miniport driver specifies the handle to a miniport adapter in 
    <i>MiniportAdapterHandle</i> . This handle to the miniport adapter is passed to the miniport driver's 
    <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> function to
    set up the miniport adapter for network I/O operations.

<b>NdisMQueryAdapterInstanceName</b> allocates memory for the string that specifies the friendly name.
    After the caller finishes using this memory, the caller must call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562577">NdisFreeMemory</a> function to release the
    memory.

Friendly names are intended to help the user quickly and accurately identify a physical NIC or virtual
    adapter--for example, "PCI Ethernet Adapter" and "Virtual Private Networking Adapter" are considered
    friendly names.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562577">NdisFreeMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

