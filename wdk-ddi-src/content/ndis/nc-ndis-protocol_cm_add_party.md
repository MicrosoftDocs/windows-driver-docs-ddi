---
UID: NC:ndis.PROTOCOL_CM_ADD_PARTY
title: PROTOCOL_CM_ADD_PARTY (ndis.h)
description: The ProtocolCmAddParty function is a required function.
old-location: netvista\protocolcmaddparty.htm
tech.root: netvista
ms.assetid: 06aa5ff6-974c-43dd-8395-bc1a1a8421d5
ms.date: 05/02/2018
keywords: ["PROTOCOL_CM_ADD_PARTY callback function"]
ms.keywords: PROTOCOL_CM_ADD_PARTY, PROTOCOL_CM_ADD_PARTY callback, ProtocolCmAddParty, ProtocolCmAddParty callback function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_06efc681-bd3d-4bcc-938e-5ba45ce97279.xml, ndis/ProtocolCmAddParty, netvista.protocolcmaddparty
f1_keywords:
 - "ndis/ProtocolCmAddParty"
 - "ProtocolCmAddParty"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    ProtocolCmAddParty (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    ProtocolCmAddParty (NDIS   5.1)) in Windows XP.
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndis.h
api_name:
- ProtocolCmAddParty
targetos: Windows
req.typenames: 
---

# PROTOCOL_CM_ADD_PARTY callback function


## -description


The 
  <i>ProtocolCmAddParty</i> function is a required function. 
  <i>ProtocolCmAddParty</i> sets up the media-specific parameters to add a party to an existing multipoint
  call, stores state data for the new party, and causes the party to be added to the call.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CM_ADD_PARTY</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters




### -param CallMgrVcContext 
[in]
Specifies the handle to a call manager-allocated context area in which the call manager maintains
     its per-VC state. The call manager supplied this handle to NDIS from its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a> function.


### -param CallParameters 
[in, out]
Pointer to a 
     <a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff545384(v=vs.85)">CO_CALL_PARAMETERS</a> structure that contains
     the parameters, specified by a connection-oriented client, for the party that is being added to an
     existing call.


### -param NdisPartyHandle 
[in]
Specifies a handle, supplied by NDIS, that uniquely identifies a multipoint party that is to be
     added to an existing virtual connection. This handle is opaque to the call manager and reserved for NDIS
     library use.


### -param CallMgrPartyContext 
[out]
Specifies, on return, a handle to a call manager-supplied context area in which the call manager
     maintains state about this party for the multipoint call.


## -returns



<i>ProtocolCmAddParty</i> returns the status of its operation(s) as one of the following:

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
Indicates that the call manager successfully allocated the necessary resources to maintain state
       about the party and successfully added the party to the call.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the call manager will complete the request to add a party asynchronously. When
       the call manager has completed all operations for adding the party, it must call 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmaddpartycomplete">NdisCmAddPartyComplete</a> to signal
       NDIS that this operation has been completed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the call manager was unable to allocate and/or initialize its resources for
       adding a party to the connection.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the call manager was unable to add the party to the multipoint call because the
       caller requested invalid or unavailable features in the call parameters at 
       <i>CallParameters</i> or else that the media type supported by this call manager does not support
       multipoint calls.

</td>
</tr>
</table>
 




## -remarks



<i>ProtocolCmAddParty</i> performs any necessary allocations of dynamic resources and structures that the
    call manager requires to maintain state information about the party, specified by 
    <i>NdisPartyHandle</i>, to be added to a multipoint call. Such resources could include, but are not
    limited to, memory buffers, data structures, events, and other similar resources. Call managers should
    also initialize relevant per-party structures in this function.

In the per-party state area that the call manager allocates, the call manager 
    <u>must</u> store the handle specified by 
    <i>NdisPartyHandle</i> for reference in future calls. After the call manager has allocated and finish
    initializing its per-party state area, the address of the state buffer should be set as the 
    <i>CallMgrPartyContext</i> handle before returning control to NDIS. To do this, dereference the handle and
    store a pointer to the state buffer as the value of the handle. For example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>*CallMgrPartyContext = SomeBuffer;</pre>
</td>
</tr>
</table></span></div>
Call managers perform any necessary communication with their network hardware or other media-specific
    actors, as necessary, to add the party specified by the call parameters at 
    <i>CallParameters</i> to an existing multipoint call.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolCmAddParty</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCmAddParty</i> function that is named "MyCmAddParty", use the <b>PROTOCOL_CM_ADD_PARTY</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_ADD_DEVICE MyCmAddParty;</pre>
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
 MyCmAddParty(
    NDIS_HANDLE  CallMgrVcContext,
    PCO_CALL_PARAMETERS  CallParameters,
    NDIS_HANDLE  NdisPartyHandle,
    PNDIS_HANDLE  CallMgrPartyContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CM_ADD_PARTY</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CM_ADD_PARTY</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscladdparty">NdisClAddParty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_add_party_complete">ProtocolClAddPartyComplete</a>
 

 

