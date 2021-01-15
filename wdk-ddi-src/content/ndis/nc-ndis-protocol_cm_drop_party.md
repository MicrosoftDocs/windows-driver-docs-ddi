---
UID: NC:ndis.PROTOCOL_CM_DROP_PARTY
title: PROTOCOL_CM_DROP_PARTY (ndis.h)
description: The ProtocolCmDropParty function is required.
old-location: netvista\protocolcmdropparty.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["PROTOCOL_CM_DROP_PARTY callback function"]
ms.keywords: PROTOCOL_CM_DROP_PARTY, PROTOCOL_CM_DROP_PARTY callback, ProtocolCmDropParty, ProtocolCmDropParty callback function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_cda3b3ab-baf4-43a7-b560-7a717687508e.xml, ndis/ProtocolCmDropParty, netvista.protocolcmdropparty
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    ProtocolCmDropParty (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    ProtocolCmDropParty (NDIS   5.1)) in Windows XP.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PROTOCOL_CM_DROP_PARTY
 - ndis/PROTOCOL_CM_DROP_PARTY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - PROTOCOL_CM_DROP_PARTY
---

# PROTOCOL_CM_DROP_PARTY callback function


## -description

The 
  <i>ProtocolCmDropParty</i> function is required. NDIS calls 
  <i>ProtocolCmDropParty</i> to request that the call manager remove a party from an existing multipoint
  call.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CM_DROP_PARTY</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters

### -param CallMgrPartyContext 

[in]
Specifies the handle to a call manager-allocated context area in which the call manager maintains
     its per-party state. This handle was provided to NDIS in the call managers 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_add_party">ProtocolCmAddParty</a> function.

### -param CloseData 

[in, optional]
Pointer to a buffer containing connection-oriented client-specific data that should be sent across
     the connection before the party is dropped. This parameter is <b>NULL</b> if the underlying network medium does
     not support transfers of data when closing a connection.

### -param Size 

[in, optional]
Specifies the length, in bytes, of the buffer at 
     <i>CloseData</i>, zero if 
     <i>CloseData</i> is <b>NULL</b>.

## -returns

<i>ProtocolCmDropParty</i> returns the status of its operation(s) as one of the following values:

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
Indicates that the call manager has successfully dropped the party, sent any close data, and
       free the resources that were allocated for its context area.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the call manager will complete the request to drop the party asynchronously. The
       call manager must call 
       <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmdroppartycomplete">NdisCmDropPartyComplete</a> when
       all processing has been finished to notify NDIS and the requesting actor that the party has been
       dropped.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_DATA</b></dt>
</dl>
</td>
<td width="60%">
Indicates that 
       <i>CloseData</i> was specified to the call manager, but the media type does not support sending data
       concurrent with connection termination.

</td>
</tr>
</table>

## -remarks

<i>ProtocolCmDropParty</i> communicates with network control devices or other media-specific agents, as
    necessary for its media, to drop a party from an existing multipoint call. If the call manager is
    required to communicated with network control agents (such as, a networking switch) it should use a
    virtual connection to the network control agents that it established in its 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">
    ProtocolBindAdapterEx</a> function.

If 
    <i>CloseData</i> is non-<b>NULL</b> and sending data at connection termination is supported by its media type,
    the call manager should transmit the data specified at 
    <i>CloseData</i> before completing termination. If sending data concurrent with connection termination is
    not supported by the media type, the call manager should return control with
    NDIS_STATUS_INVALID_DATA.

Call managers must also free any per-party resources that it allocated and stored at 
    <i>CallMgrPartyContext</i> . In addition, the call manager must free the buffer stored 
    <i>CallMgrPartyContext</i> itself. Failure to do so will result in a memory leak condition.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolCmDropParty</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCmDropParty</i> function that is named "MyCmDropParty", use the <b>PROTOCOL_CM_DROP_PARTY</b> type as shown in this code example:


```
PROTOCOL_CM_DROP_PARTY MyCmDropParty;
```

Then, implement your function as follows:


```
_Use_decl_annotations_
NDIS_STATUS
 MyCmDropParty(
    NDIS_HANDLE  CallMgrPartyContext,
    PVOID  CloseData,
    UINT  Size
    )
  {...}
```

The <b>PROTOCOL_CM_DROP_PARTY</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CM_DROP_PARTY</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmdroppartycomplete">NdisCmDropPartyComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_add_party">ProtocolCmAddParty</a>

