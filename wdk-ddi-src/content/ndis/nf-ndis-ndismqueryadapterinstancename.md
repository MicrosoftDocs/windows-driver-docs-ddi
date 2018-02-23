---
UID: NF:ndis.NdisMQueryAdapterInstanceName
title: NdisMQueryAdapterInstanceName function
author: windows-driver-content
description: The NdisMQueryAdapterInstanceName function retrieves the friendly name of a miniport adapter.
old-location: netvista\ndismqueryadapterinstancename.htm
old-project: netvista
ms.assetid: 7af6ee73-814b-49f8-8641-d3e8dc672ee5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NdisMQueryAdapterInstanceName function [Network Drivers Starting with Windows Vista], NdisMQueryAdapterInstanceName, ndis/NdisMQueryAdapterInstanceName, netvista.ndismqueryadapterinstancename, miniport_ndis_functions_ref_5e04ebd4-3db8-4cb2-a75c-ce67d938804c.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisMQueryAdapterInstanceName
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMQueryAdapterInstanceName function


## -description


The
  <b>NdisMQueryAdapterInstanceName</b> function retrieves the friendly name of a miniport adapter.


## -syntax


````
NDIS_STATUS NdisMQueryAdapterInstanceName(
  _Out_ PNDIS_STRING AdapterInstanceName,
  _In_  NDIS_HANDLE  MiniportAdapterHandle
);
````


## -parameters




### -param pAdapterInstanceName

TBD


### -param MiniportHandle

TBD




#### - AdapterInstanceName [out]

A pointer to a caller-supplied NDIS_STRING type that receives a counted Unicode string. This
     string specifies the friendly name of the interface for the given miniport adapter. For Windows Vista
     and later versions of the Windows operating system, NDIS defines the NDIS_STRING type as a 
     <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> type.


#### - MiniportAdapterHandle [in]

The handle to the miniport adapter that was previously input to the 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">
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
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function to
    set up the miniport adapter for network I/O operations.

<b>NdisMQueryAdapterInstanceName</b> allocates memory for the string that specifies the friendly name.
    After the caller finishes using this memory, the caller must call the 
    <a href="..\ndis\nf-ndis-ndisfreememory.md">NdisFreeMemory</a> function to release the
    memory.

Friendly names are intended to help the user quickly and accurately identify a physical NIC or virtual
    adapter--for example, "PCI Ethernet Adapter" and "Virtual Private Networking Adapter" are considered
    friendly names.




## -see-also

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndisfreememory.md">NdisFreeMemory</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMQueryAdapterInstanceName function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

