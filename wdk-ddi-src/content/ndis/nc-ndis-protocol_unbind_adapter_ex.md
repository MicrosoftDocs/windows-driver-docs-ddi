---
UID: NC:ndis.PROTOCOL_UNBIND_ADAPTER_EX
title: PROTOCOL_UNBIND_ADAPTER_EX (ndis.h)
description: NDIS calls a protocol driver's ProtocolUnbindAdapterEx function to request the driver to unbind from an underlying miniport adapter.Note  You must declare the function by using the PROTOCOL_UNBIND_ADAPTER_EX type.
old-location: netvista\protocolunbindadapterex.htm
tech.root: netvista
ms.assetid: 19fa7be2-acb9-42f6-bd9f-5be3e3c8b5fa
ms.date: 05/02/2018
keywords: ["PROTOCOL_UNBIND_ADAPTER_EX callback function"]
ms.keywords: PROTOCOL_UNBIND_ADAPTER_EX, PROTOCOL_UNBIND_ADAPTER_EX callback, ProtocolUnbindAdapterEx, ProtocolUnbindAdapterEx callback function [Network Drivers Starting with Windows Vista], ndis/ProtocolUnbindAdapterEx, netvista.protocolunbindadapterex, protocol_functions_ref_e8d6b640-35e1-4824-9d7b-a7ebd6273764.xml
f1_keywords:
 - "ndis/ProtocolUnbindAdapterEx"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and later.
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndis.h
api_name:
- ProtocolUnbindAdapterEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# PROTOCOL_UNBIND_ADAPTER_EX callback function


## -description


NDIS calls a protocol driver's 
  <i>ProtocolUnbindAdapterEx</i> function to request the driver to unbind from an underlying miniport
  adapter.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_UNBIND_ADAPTER_EX</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param UnbindContext [in]

The handle that identifies the NDIS context area for this unbind operation.


### -param ProtocolBindingContext [in]

A handle to a context area allocated by the protocol driver. The protocol driver maintains the
     per-binding context information in this context area. The driver supplied this handle to NDIS when the
     driver called the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a> function.


## -returns



<i>ProtocolUnbindAdapterEx</i> returns one of the following status values:

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
<i>ProtocolUnbindAdapterEx</i> successfully unbound from an underlying miniport adapter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
<i>ProtocolUnbindAdapterEx</i> did not complete the unbind operation and the operation will be
       completed asynchronously. The protocol driver must call the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscompleteunbindadapterex">
       NdisCompleteUnbindAdapterEx</a> function after the unbind operation is complete.

</td>
</tr>
</table>
 




## -remarks



<i>ProtocolUnbindAdapterEx</i> is a required function. As the reciprocal of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a> function,
    NDIS calls 
    <i>ProtocolUnbindAdapterEx</i> to release the resources that the driver allocated for network I/O
    operations that are specific to a binding. A protocol driver cannot fail an unbind operation.

Before calling 
    <i>ProtocolUnbindAdapterEx</i>, NDIS pauses the protocol binding. To pause the binding, NDIS calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_net_pnp_event">ProtocolNetPnPEvent</a> function and
    specifics a 
    <b>NetEventPause</b> event.

<i>ProtocolUnbindAdapterEx</i> must call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscloseadapterex">NdisCloseAdapterEx</a> function to close
    the binding to the underlying miniport adapter. If 
    <b>NdisCloseAdapterEx</b> returns NDIS_STATUS_SUCCESS, the close operation is complete. If 
    <b>NdisCloseAdapterEx</b> returns NDIS_STATUS_PENDING, NDIS calls the protocol driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_close_adapter_complete_ex">
    ProtocolCloseAdapterCompleteEx</a> function after the close operation is complete.

Before calling 
    <b>NdisCloseAdapterEx</b>, the protocol driver should clear the multicast address list and packet filters
    for the binding. The protocol driver sets the binding multicast address list to <b>NULL</b>, and the packet
    filter to zero. For more information, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-802-3-multicast-list">OID_802_3_MULTICAST_LIST</a> and 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-current-packet-filter">
    OID_GEN_CURRENT_PACKET_FILTER</a>.

If a wake-up pattern has been specified, the protocol driver should remove it with the   <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-pnp-remove-wake-up-pattern">OID_PNP_REMOVE_WAKE_UP_PATTERN</a> OID and clear the receive side scaling parameters with the <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-receive-scale-parameters">OID_GEN_RECEIVE_SCALE_PARAMETERS</a> OID. An NDIS 6.20 and later protocol driver should remove a wake-on-LAN pattern with the <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-pm-remove-wol-pattern">OID_PM_REMOVE_WOL_PATTERN</a> OID and remove a low-power protocol offload with the <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-pm-remove-protocol-offload">OID_PM_REMOVE_PROTOCOL_OFFLOAD</a> OID.

<i>ProtocolUnbindAdapterEx</i> must not free the memory at 
    <i>ProtocolBindingContext</i> until the close operation is complete. NDIS passes the handle at 
    <i>ProtocolBindingContext</i> to 
    <i>ProtocolCloseAdapterCompleteEx</i>.

If the protocol driver has completed the unbind operation, 
    <i>ProtocolUnbindAdapterEx</i> can return NDIS_STATUS_SUCCESS. If 
    <b>NdisCloseAdapterEx</b> returns NDIS_STATUS_PENDING, 
    <i>ProtocolUnbindAdapterEx</i> must wait for NDIS to call 
    <i>ProtocolCloseAdapterCompleteEx</i> before it can return NDIS_STATUS_SUCCESS.

<i>ProtocolUnbindAdapterEx</i> can return NDIS_STATUS_PENDING to defer the completion of the unbind
    operation to a later time. If 
    <i>ProtocolUnbindAdapterEx</i> returns NDIS_STATUS_PENDING, the driver must eventually call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscompleteunbindadapterex">
    NdisCompleteUnbindAdapterEx</a> function to complete the unbind operation. If the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscloseadapterex">NdisCloseAdapterEx</a> function returned
    NDIS_STATUS_PENDING, the driver can complete the unbind operation in 
    <i>ProtocolCloseAdapterCompleteEx</i>. 
    <i>ProtocolUnbindAdapterEx</i> can store the handle at 
    <i>UnbindContext</i> in the context area at 
    <i>ProtocolBindingContext</i> before it calls 
    <b>NdisCloseAdapterEx</b>. If 
    <i>ProtocolUnbindAdapterEx</i> stored the handle,
    <i>ProtocolCloseAdapterCompleteEx</i> can pass the handle to 
    <b>NdisCompleteUnbindAdapterEx</b> to complete the unbind operation.

As soon as 
    <i>ProtocolUnbindAdapterEx</i> calls 
    <b>NdisCloseAdapterEx</b>, the handle obtained from the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a> function at the 
    <i>NdisBindingHandle</i> parameter becomes invalid. 
    <i>ProtocolUnbindAdapterEx</i> cannot make any subsequent calls to 
    <b>Ndis<i>Xxx</i></b> functions with this handle. The driver can get receive and status indications from the
    underlying miniport adapter until the close operation is complete.

NDIS calls 
    <i>ProtocolUnbindAdapterEx</i> at IRQL = PASSIVE_LEVEL.

<h3><a id="Updating_Power_Management_and_RSS_Settings"></a><a id="updating_power_management_and_rss_settings"></a><a id="UPDATING_POWER_MANAGEMENT_AND_RSS_SETTINGS"></a>Updating Power Management and RSS Settings</h3>
NDIS 6.0 and 6.1 protocol drivers should perform the following operations where applicable:

<ol>
<li>
Remove power management wake on LAN (WOL) patterns from the miniport adapter with the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-pnp-remove-wake-up-pattern">
       OID_PNP_REMOVE_WAKE_UP_PATTERN</a> OID.

</li>
<li>
Clear the receive side scaling parameters with the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-receive-scale-parameters">
       OID_GEN_RECEIVE_SCALE_PARAMETERS</a> OID.

</li>
</ol>
NDIS 6.20 and later protocol drivers should perform the following operations:

<ol>
<li>
Remove power management WOL patterns from the miniport adapter with the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-pm-remove-wol-pattern">OID_PM_REMOVE_WOL_PATTERN</a> OID.

</li>
<li>
Remove power management protocol offloads from the miniport adapter with the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-pm-remove-protocol-offload">
       OID_PM_REMOVE_PROTOCOL_OFFLOAD</a> OID.

</li>
</ol>
<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolUnbindAdapterEx</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolUnbindAdapterEx</i> function that is named "MyUnbindAdapterEx", use the <b>PROTOCOL_UNBIND_ADAPTER_EX</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_UNBIND_ADAPTER_EX MyUnbindAdapterEx;</pre>
</td>
</tr>
</table></span></div>
Then, implement your function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
NDIS_STATUS
 MyUnbindAdapterEx(
    NDIS_HANDLE  UnbindContext,
    NDIS_HANDLE  ProtocolBindingContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_UNBIND_ADAPTER_EX</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_UNBIND_ADAPTER_EX</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscloseadapterex">NdisCloseAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscompleteunbindadapterex">NdisCompleteUnbindAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-802-3-multicast-list">OID_802_3_MULTICAST_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-current-packet-filter">OID_GEN_CURRENT_PACKET_FILTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-receive-scale-parameters">
   OID_GEN_RECEIVE_SCALE_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-pnp-remove-wake-up-pattern">OID_PNP_REMOVE_WAKE_UP_PATTERN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_close_adapter_complete_ex">
   ProtocolCloseAdapterCompleteEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_net_pnp_event">ProtocolNetPnPEvent</a>
 

 

