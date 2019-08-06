---
UID: NF:ndis.NdisMAllocatePort
title: NdisMAllocatePort function (ndis.h)
description: The NdisMAllocatePort function allocates an NDIS port that is associated with a miniport adapter.
old-location: netvista\ndismallocateport.htm
tech.root: netvista
ms.assetid: ca3a2a12-ea80-4f77-9742-b0440fb441f7
ms.date: 05/02/2018
ms.keywords: NdisMAllocatePort, NdisMAllocatePort function [Network Drivers Starting with Windows Vista], ndis/NdisMAllocatePort, ndis_ports_ref_c74ffd82-73c0-4e48-98da-d17ddf7976ae.xml, netvista.ndismallocateport
ms.topic: function
f1_keywords:
 - "ndis/NdisMAllocatePort"
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
- NdisMAllocatePort
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMAllocatePort function


## -description


The 
  <b>NdisMAllocatePort</b> function allocates an NDIS port that is associated with a miniport adapter.


## -parameters




### -param NdisMiniportHandle

The miniport adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">
     MiniportInitializeEx</a> function.

### -param PortCharacteristics [in, out]

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_port_characteristics">
     NDIS_PORT_CHARACTERISTICS</a> structure that defines the characteristics of the port.

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
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-enumerate-ports">OID_GEN_ENUMERATE_PORTS</a> OID to
    enumerate a miniport adapter's ports, NDIS does not include non-active allocated ports in the list of the
    ports.

When 
    <b>NdisMAllocatePort</b> successfully returns, the 
    <b>PortNumber</b> member of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_port_characteristics">
    NDIS_PORT_CHARACTERISTICS</a> structure that the 
    <i>PortCharacteristics</i> parameter specifies is set to the port number that NDIS assigned to the
    port.

After a port is no longer required, the miniport driver should call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismfreeport">NdisMFreePort</a> function to free the port.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/allocating-an-ndis-port">Allocating an NDIS Port</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_port_characteristics">NDIS_PORT_CHARACTERISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismfreeport">NdisMFreePort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-enumerate-ports">OID_GEN_ENUMERATE_PORTS</a>
 

 

