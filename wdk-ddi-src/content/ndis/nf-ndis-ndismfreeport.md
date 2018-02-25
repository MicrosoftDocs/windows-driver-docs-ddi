---
UID: NF:ndis.NdisMFreePort
title: NdisMFreePort function
author: windows-driver-content
description: The NdisMFreePort function frees an NDIS port that was previously allocated with the NdisMAllocatePort function.
old-location: netvista\ndismfreeport.htm
old-project: netvista
ms.assetid: 38d53977-ada2-41b9-8b6a-a3bd691f4525
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , F, M, N, NdisMFreePort, NdisMFreePort function [Network Drivers Starting with Windows Vista], P, d, e, i, ndis/NdisMFreePort, ndis_ports_ref_b5b73dda-9bc0-4d7d-a265-d50d1436c8f4.xml, netvista.ndismfreeport, o, r, s, t"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
-	NdisMFreePort
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMFreePort function


## -description


The 
  <b>NdisMFreePort</b> function frees an NDIS port that was previously allocated with the 
  <a href="..\ndis\nf-ndis-ndismallocateport.md">NdisMAllocatePort</a> function.


## -syntax


````
NDIS_STATUS NdisMFreePort(
  _In_ NDIS_HANDLE      MiniportAdapterHandle,
  _In_ NDIS_PORT_NUMBER PortNumber
);
````


## -parameters




### -param NdisMiniportHandle

TBD


### -param PortNumber [in]

The number of the NDIS port that NDIS should free. The 
     <i>PortNumber</i> value is an NDIS_PORT_NUMBER value, which has a ULONG data type. NDIS provided the port
     number in the 
     <b>PortNumber</b> member of the 
     <a href="..\ntddndis\ns-ntddndis-_ndis_port_characteristics.md">
     NDIS_PORT_CHARACTERISTICS</a> structure when the miniport driver called the 
     <a href="..\ndis\nf-ndis-ndismallocateport.md">NdisMAllocatePort</a> function. 
     

The port number can be a number from 1 through 0xffffff. You cannot set 
     <i>PortNumber</i> to zero, which indicates the default port.


#### - MiniportAdapterHandle [in]

The miniport adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of the 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">
     MiniportInitializeEx</a> function.


## -returns



<b>NdisMFreePort</b> can return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
NDIS successfully freed the resources for the port.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_PORT</b></dt>
</dl>
</td>
<td width="60%">
NDIS could not free the resources for the port because the port number was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_PORT_STATE</b></dt>
</dl>
</td>
<td width="60%">
NDIS could not free the resources for the port because the port was is in a state where the free
       operation is invalid. To free the port, the port must be in the allocated state.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_DATA</b></dt>
</dl>
</td>
<td width="60%">
The port number that was supplied at the 
       <i>PortNumber</i> parameter was invalid.

</td>
</tr>
</table>
 




## -remarks



If a miniport driver allocated a port by calling the 
    <a href="..\ndis\nf-ndis-ndismallocateport.md">NdisMAllocatePort</a> function, the driver
    must free the port before it returns from its 
    <a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a> function. If the miniport
    driver activated the port by issuing a 
    <b>NetEventPortActivation</b> Plug and Play (PnP) event, the driver must issue a 
    <b>NetEventPortDeactivation</b> PnP event for the port before freeing the port.

When a miniport driver calls <b>NdisMFreePort</b> to free a port, NDIS also frees the port number that is assigned to the freed port so that NDIS can reuse the port number.

The miniport driver must not attempt to free the default port.




## -see-also

<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>



<a href="..\ndis\nf-ndis-ndismallocateport.md">NdisMAllocatePort</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/a9edf83f-9226-4c75-a04e-1879a05df24c">Default NDIS Port</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_port_characteristics.md">NDIS_PORT_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/ae7b608d-6105-4fdc-b805-0f0101d7c218">Freeing an NDIS Port</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMFreePort function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

