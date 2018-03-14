---
UID: NF:ndis.NdisMAllocatePort
title: NdisMAllocatePort function
author: windows-driver-content
description: The NdisMAllocatePort function allocates an NDIS port that is associated with a miniport adapter.
old-location: netvista\ndismallocateport.htm
old-project: netvista
ms.assetid: ca3a2a12-ea80-4f77-9742-b0440fb441f7
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisMAllocatePort, NdisMAllocatePort function [Network Drivers Starting with Windows Vista], ndis/NdisMAllocatePort, ndis_ports_ref_c74ffd82-73c0-4e48-98da-d17ddf7976ae.xml, netvista.ndismallocateport
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisMAllocatePort
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMAllocatePort function


## -description


The 
  <b>NdisMAllocatePort</b> function allocates an NDIS port that is associated with a miniport adapter.


## -syntax


````
NDIS_STATUS NdisMAllocatePort(
  _In_    NDIS_HANDLE                MiniportAdapterHandle,
  _Inout_ PNDIS_PORT_CHARACTERISTICS PortCharacteristics
);
````


## -parameters




### -param NdisMiniportHandle

TBD


### -param PortCharacteristics [in, out]

A pointer to an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_port_characteristics.md">
     NDIS_PORT_CHARACTERISTICS</a> structure that defines the characteristics of the port.


#### - MiniportAdapterHandle [in]

The miniport adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of the 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">
     MiniportInitializeEx</a> function.


## -returns



<b>NdisMAllocatePort</b> can return one of the following values:

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
NDIS successfully allocated resources for the port.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
NDIS could not allocate resources for the port.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_CLOSING</b></dt>
</dl>
</td>
<td width="60%">
The port allocation failed because the associated miniport adapter is closing.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_DATA</b></dt>
</dl>
</td>
<td width="60%">
The data that was supplied at the 
       <i>PortCharacteristics</i> parameter was invalid.

</td>
</tr>
</table>
 




## -remarks



The 
    <b>NdisMAllocatePort</b> function allocates resources and a port number for a port that is associated with
    a miniport adapter. The port is not active until the miniport driver issues a 
    <b>NetEventPortActivation</b> Plug and Play (PnP) event for the port.

After the miniport driver activates the port, NDIS generates a PnP notification for the overlying
    drivers. If an overlying driver or user-mode application issues the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569583">OID_GEN_ENUMERATE_PORTS</a> OID to
    enumerate a miniport adapter's ports, NDIS does not include non-active allocated ports in the list of the
    ports.

When 
    <b>NdisMAllocatePort</b> successfully returns, the 
    <b>PortNumber</b> member of the 
    <a href="..\ntddndis\ns-ntddndis-_ndis_port_characteristics.md">
    NDIS_PORT_CHARACTERISTICS</a> structure that the 
    <i>PortCharacteristics</i> parameter specifies is set to the port number that NDIS assigned to the
    port.

After a port is no longer required, the miniport driver should call the 
    <a href="..\ndis\nf-ndis-ndismfreeport.md">NdisMFreePort</a> function to free the port.




## -see-also

<a href="https://msdn.microsoft.com/39c77921-5841-40f5-90ba-0fba89b3b55e">Allocating an NDIS Port</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_port_characteristics.md">NDIS_PORT_CHARACTERISTICS</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndismfreeport.md">NdisMFreePort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569583">OID_GEN_ENUMERATE_PORTS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMAllocatePort function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

