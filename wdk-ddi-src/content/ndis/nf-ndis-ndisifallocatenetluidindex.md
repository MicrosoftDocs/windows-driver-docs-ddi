---
UID: NF:ndis.NdisIfAllocateNetLuidIndex
title: NdisIfAllocateNetLuidIndex function (ndis.h)
description: The NdisIfAllocateNetLuidIndex function allocates a NET_LUID index for an NDIS network interface provider.
old-location: netvista\ndisifallocatenetluidindex.htm
tech.root: netvista
ms.assetid: bc62da04-242a-4d9a-8a85-2342a1b3e628
ms.date: 05/02/2018
keywords: ["NdisIfAllocateNetLuidIndex function"]
ms.keywords: NdisIfAllocateNetLuidIndex, NdisIfAllocateNetLuidIndex function [Network Drivers Starting with Windows Vista], ndis/NdisIfAllocateNetLuidIndex, net_if_functions_ref_3ffcc5c8-7475-475d-8732-dc59ee632285.xml, netvista.ndisifallocatenetluidindex
f1_keywords:
 - "ndis/NdisIfAllocateNetLuidIndex"
 - "NdisIfAllocateNetLuidIndex"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisIfAllocateNetLuidIndex
targetos: Windows
req.typenames: 
---

# NdisIfAllocateNetLuidIndex function


## -description


The 
  <b>NdisIfAllocateNetLuidIndex</b> function allocates a 
  <a href="https://docs.microsoft.com/windows/win32/api/ifdef/ns-ifdef-net_luid_lh">NET_LUID</a> index for an NDIS network interface
  provider.


## -parameters




### -param ifType

The Internet Assigned Numbers Authority (IANA) interface type for an index. For example,
     IF_TYPE_ETHERNET_CSMACD (6) is the value for 
     <i>IfType</i> that is assigned to any Ethernet-like interface. For a list of interface types, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-interface-types">NDIS Interface Types</a>.

### -param pNetLuidIndex 
[out]
A pointer to a caller-supplied 
     <a href="https://docs.microsoft.com/windows/win32/api/ifdef/ns-ifdef-net_luid_lh">NET_LUID</a> index variable. If allocation is
     successful, 
     <b>NdisIfAllocateNetLuidIndex</b> sets this variable to the allocated 24-bit NET_LUID index value.


## -returns



<b>NdisIfAllocateNetLuidIndex</b> returns one of the following values:

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
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The operation failed because of insufficient resources.

</td>
</tr>
</table>
 




## -remarks



NDIS interface providers call the 
    <b>NdisIfAllocateNetLuidIndex</b> function to allocate a 
    <a href="https://docs.microsoft.com/windows/win32/api/ifdef/ns-ifdef-net_luid_lh">NET_LUID</a> index. An interface provider must allocate
    a NET_LUID index before the interface provider can register an interface.

<b>NdisIfAllocateNetLuidIndex</b> attempts to allocate a 24-bit NET_LUID index that is unique to the local
    computer and is associated with the interface type that the 
    <i>IfType</i> parameter specifies. NDIS records the NET_LUID index in persistent storage so that the index
    can remain associated with the same interface even after the computer restarts. NDIS will not allocate
    the same NET_LUID index to future callers of 
    <b>NdisIfAllocateNetLuidIndex</b> until after the interface provider calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisiffreenetluidindex">NdisIfFreeNetLuidIndex</a> function to
    free the index.

To build a 
    <a href="https://docs.microsoft.com/windows/win32/api/ifdef/ns-ifdef-net_luid_lh">NET_LUID</a> value from the NET_LUID index and the
    interface type, an interface provider calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-make-net-luid">NDIS_MAKE_NET_LUID</a> macro.

The interface provider must store the NET_LUID values that it allocates in persistent storage. For
    example, if there is a loss of computer power, the provider should have stored the NET_LUID values in
    persistent storage so it can call 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisiffreenetluidindex">NdisIfFreeNetLuidIndex</a> later to
    free any indexes that are no longer in use. Also, the provider should use the same NET_LUID value
    whenever it registers the same interface with the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisifregisterinterface">
    NdisIfRegisterInterface</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-make-net-luid">NDIS_MAKE_NET_LUID</a>



<a href="https://docs.microsoft.com/windows/win32/api/ifdef/ns-ifdef-net_luid_lh">NET_LUID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisiffreenetluidindex">NdisIfFreeNetLuidIndex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisifregisterinterface">NdisIfRegisterInterface</a>
 

 

