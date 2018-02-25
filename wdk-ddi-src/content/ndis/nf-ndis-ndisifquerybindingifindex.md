---
UID: NF:ndis.NdisIfQueryBindingIfIndex
title: NdisIfQueryBindingIfIndex function
author: windows-driver-content
description: The NdisIfQueryBindingIfIndex function retrieves the network interface indexes and NET_LUID values for the highest and lowest layered network interfaces that are associated with a specified protocol binding.
old-location: netvista\ndisifquerybindingifindex.htm
old-project: netvista
ms.assetid: 08f31584-b3ea-4e6e-b8ce-17813ca7c06b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , B, I, N, NdisIfQueryBindingIfIndex, NdisIfQueryBindingIfIndex function [Network Drivers Starting with Windows Vista], Q, d, e, f, g, i, n, ndis/NdisIfQueryBindingIfIndex, net_if_functions_ref_eacdb959-2a12-4688-9e83-7454c579e2d3.xml, netvista.ndisifquerybindingifindex, r, s, u, x, y"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisIfQueryBindingIfIndex
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisIfQueryBindingIfIndex function


## -description


The 
  <b>NdisIfQueryBindingIfIndex</b> function retrieves the network interface indexes and 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568747">NET_LUID</a> values for the highest and lowest layered
  network interfaces that are associated with a specified protocol binding.


## -syntax


````
NDIS_STATUS NdisIfQueryBindingIfIndex(
  _In_  NDIS_HANDLE  NdisBindingHandle,
  _Out_ PNET_IFINDEX pBoundIfIndex,
  _Out_ PNET_LUID    pBoundIfNetLuid,
  _Out_ PNET_IFINDEX pLowestIfIndex,
  _Out_ PNET_LUID    pLowestIfNetLuid
);
````


## -parameters




### -param NdisBindingHandle [in]

A handle that identifies the binding for which NDIS should obtain the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568747">NET_LUID</a> values and network interface indexes.
     NDIS provided this handle at the 
     <i>NdisBindingHandle</i> parameter of the 
     <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function.


### -param pBoundIfIndex [out]

A pointer to a caller-supplied interface index variable. If 
     <b>NdisIfQueryBindingIfIndex</b> succeeds, NDIS writes to this variable the network interface index of
     the network interface that is associated with the specified binding and is highest in the driver
     stack.


### -param pBoundIfNetLuid [out]

A pointer to a caller-supplied NET_LUID variable. If 
     <b>NdisIfQueryBindingIfIndex</b> succeeds, NDIS writes to this variable the NET_LUID value of the network
     interface that is associated with the specified binding and is highest in the driver stack.


### -param pLowestIfIndex [out]

A pointer to a caller-supplied interface index variable. If 
     <b>NdisIfQueryBindingIfIndex</b> succeeds, NDIS writes to this variable the network interface index of
     the network interface that is associated with the specified binding and is lowest in the driver
     stack.


### -param pLowestIfNetLuid [out]

A pointer to a caller-supplied NET_LUID variable. If 
     <b>NdisIfQueryBindingIfIndex</b> succeeds, NDIS writes to this variable the NET_LUID value of the network
     interface that is associated with the specified binding and is lowest in the driver stack.


## -returns



<b>NdisIfQueryBindingIfIndex</b> returns one of the following status values:

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
<b>NdisIfQueryBindingIfIndex</b> failed because the specified binding is not
       associated with a registered interface.

</td>
</tr>
</table>
 




## -remarks



NDIS protocol drivers can call the 
    <b>NdisIfQueryBindingIfIndex</b> function to retrieve the network interface indexes and 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568747">NET_LUID</a> values that are associated with a
    binding.

<b>NdisIfQueryBindingIfIndex</b> provides the NET_LUID value and the interface index for the highest
    interface and lowest interface that are associated with the binding. These values are different, for
    example, if the miniport adapter that is directly associated with the specified binding is the virtual
    miniport of a filter intermediate driver or if there is a filter module that is configured over the
    miniport adapter.

Protocol drivers can also obtain the interface index and NET_LUID of the highest and the lowest
    interfaces in a driver stack in the 
    <a href="..\ndis\ns-ndis-_ndis_bind_parameters.md">NDIS_BIND_PARAMETERS</a> structure.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568747">NET_LUID</a>



<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>



<a href="..\ndis\ns-ndis-_ndis_bind_parameters.md">NDIS_BIND_PARAMETERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisIfQueryBindingIfIndex function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

