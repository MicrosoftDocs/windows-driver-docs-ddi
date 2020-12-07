---
UID: NF:ndis.NdisIfGetInterfaceIndexFromNetLuid
title: NdisIfGetInterfaceIndexFromNetLuid function (ndis.h)
description: The NdisIfGetInterfaceIndexFromNetLuid function gets the network interface index that is associated with a NET_LUID value.
old-location: netvista\ndisifgetinterfaceindexfromnetluid.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisIfGetInterfaceIndexFromNetLuid function"]
ms.keywords: NdisIfGetInterfaceIndexFromNetLuid, NdisIfGetInterfaceIndexFromNetLuid function [Network Drivers Starting with Windows Vista], ndis/NdisIfGetInterfaceIndexFromNetLuid, net_if_functions_ref_d375ff1d-3f7f-4f11-8fd3-c41340276d30.xml, netvista.ndisifgetinterfaceindexfromnetluid
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisIfGetInterfaceIndexFromNetLuid
 - ndis/NdisIfGetInterfaceIndexFromNetLuid
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisIfGetInterfaceIndexFromNetLuid
---

# NdisIfGetInterfaceIndexFromNetLuid function


## -description

The 
  <b>NdisIfGetInterfaceIndexFromNetLuid</b> function gets the network interface index that is associated with
  a 
  <a href="/windows/win32/api/ifdef/ns-ifdef-net_luid_lh">NET_LUID</a> value.

## -parameters

### -param NetLuid 

[in]
A 
     <a href="/windows/win32/api/ifdef/ns-ifdef-net_luid_lh">NET_LUID</a> value that identifies a network
     interface.

### -param pIfIndex 

[out]
A pointer to a caller-supplied interface index variable. If 
     <b>NdisIfGetInterfaceIndexFromNetLuid</b> succeeds, NDIS writes the network interface index that is
     associated with the specified NET_LUID to this variable.

## -returns

<b>NdisIfGetInterfaceIndexFromNetLuid</b> returns one of the following status values:

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
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INTERFACE_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisIfGetInterfaceIndexFromNetLuid</b> failed because the specified NET_LUID was not present in the
       list of registered interfaces.

</td>
</tr>
</table>

## -remarks

NDIS drivers can call the 
    <b>NdisIfGetInterfaceIndexFromNetLuid</b> function to get the network interface index that is associated
    with a 
    <a href="/windows/win32/api/ifdef/ns-ifdef-net_luid_lh">NET_LUID</a> value.

For the interfaces that the NDIS proxy provider service manages, NDIS provides the interface index and
    NET_LUID in various driver initialization structures:

<ul>
<li>
Miniport drivers can obtain the interface index and NET_LUID for a miniport adapter in the 
      <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_init_parameters">
      NDIS_MINIPORT_INIT_PARAMETERS</a> structure.

</li>
<li>
Filter drivers can obtain the interface index and NET_LUID for a filter module in the 
      <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_filter_attach_parameters">
      NDIS_FILTER_ATTACH_PARAMETERS</a> structure.

</li>
<li>
Protocol drivers can obtain the interface index and NET_LUID of the highest and the lowest
      interfaces on a driver stack in the 
      <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_bind_parameters">NDIS_BIND_PARAMETERS</a> structure.

</li>
</ul>
NDIS assigns an interface index to a network interface when the interface provider calls the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisifregisterinterface">NdisIfRegisterInterface</a> function.
    An interface provider calls the 
    <a href="/windows-hardware/drivers/network/ndis-make-net-luid">NDIS_MAKE_NET_LUID</a> macro to create the
    NET_LUID value before it registers an interface.

The interface index value can change without a computer restart. Deregistering and re-registering an
    interface that is associated with a NET_LUID value might result in different interface index values. Do
    not confuse the interface index with the NET_LUID index that persists after a computer restarts.

NDIS provides the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisifgetnetluidfrominterfaceindex">
    NdisIfGetNetLuidFromInterfaceIndex</a> function to get the NET_LUID value that is associated with a
    specified interface index.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_bind_parameters">NDIS_BIND_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_filter_attach_parameters">NDIS_FILTER_ATTACH_PARAMETERS</a>



<a href="/windows-hardware/drivers/network/ndis-make-net-luid">NDIS_MAKE_NET_LUID</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_init_parameters">NDIS_MINIPORT_INIT_PARAMETERS</a>



<a href="/windows/win32/api/ifdef/ns-ifdef-net_luid_lh">NET_LUID</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisifgetnetluidfrominterfaceindex">
   NdisIfGetNetLuidFromInterfaceIndex</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisifregisterinterface">NdisIfRegisterInterface</a>
