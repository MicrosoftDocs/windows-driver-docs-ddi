---
UID: NC:ndis.PROTOCOL_CM_REG_SAP
title: PROTOCOL_CM_REG_SAP (ndis.h)
description: The ProtocolCmRegisterSap function is a required function that is called by NDIS to request that a call manager register a SAP (service access point) on behalf of a connection-oriented client.Note  You must declare the function by using the PROTOCOL_CM_REG_SAP type. For more information, see the following Examples section.
old-location: netvista\protocolcmregistersap.htm
tech.root: netvista
ms.assetid: 3e3e7a0e-a8d2-40b2-895b-187d24867080
ms.date: 05/02/2018
keywords: ["PROTOCOL_CM_REG_SAP callback function"]
ms.keywords: PROTOCOL_CM_REG_SAP, PROTOCOL_CM_REG_SAP callback, ProtocolCmRegisterSap, ProtocolCmRegisterSap callback function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_aaaefdc1-4954-4911-84a4-1f82141ccca6.xml, ndis/ProtocolCmRegisterSap, netvista.protocolcmregistersap
f1_keywords:
 - "ndis/ProtocolCmRegisterSap"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    ProtocolCmRegisterSap (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    ProtocolCmRegisterSap (NDIS   5.1)) in Windows XP.
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
- ProtocolCmRegisterSap
product:
- Windows
targetos: Windows
req.typenames: 
---

# PROTOCOL_CM_REG_SAP callback function


## -description


The 
  <i>ProtocolCmRegisterSap</i> function is a required function that is called by NDIS to request that a call
  manager register a SAP (service access point) on behalf of a connection-oriented client.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CM_REG_SAP</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters




### -param CallMgrAfContext [in]

Specifies the handle to a call manager-allocated context area in which the call manager maintains
     its per-open AF state. The call manager supplied this handle to NDIS from its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_open_af">ProtocolCmOpenAf</a> function.


### -param Sap [in]

Pointer to a media-specific CO_SAP structure that contains the specific SAP that a
     connection-oriented client is registering.


### -param NdisSapHandle [in]

Specifies a handle, supplied by NDIS, that uniquely identifies this SAP. This handle is opaque to
     the call manager and reserved for NDIS library use.


### -param CallMgrSapContext [out]

On return, specifies the handle to a call manager-supplied context area in which the call manager
     maintains state about this SAP.


## -returns



<i>ProtocolCmRegisterSap</i> returns the status of its operation(s) as one of the following:

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
Indicates that the call manager successfully allocated and/or initialized any necessary
       resources to register and maintain the SAP. In addition, it also indicates that the SAP was registered
       successfully as required by the network media that the call manager supports.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the call manager will complete the processing of this request asynchronously.
       Call managers must call 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmregistersapcomplete">
       NdisCmRegisterSapComplete</a> when all processing has been completed to signal NDIS that the
       registration is finished.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the call manager was unable to allocated and/or initialize its resources required
       to register the SAP on behalf of the connection-oriented client.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_DATA</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the specification provided at 
       <i>Sap</i> is invalid or cannot be supported.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_<i>XXX</i></b></dt>
</dl>
</td>
<td width="60%">
Indicates that the call manager encountered an error in attempting to register the SAP for the
       connection-oriented client. The return code is appropriate to the error and could be a return code
       propagated from another NDIS library function.

</td>
</tr>
</table>
 




## -remarks



<i>ProtocolCmMakeCall</i> communicates with network control devices or other media-specific agents, as
    necessary, to register the SAP, as specified at 
    <i>Sap</i>, on the network for a connection-oriented client. Such actions could include, but are not
    limited to communicating with switching hardware, communicating with a network control station, or other
    actions that are appropriate to the network medium.

If a call manager is required to communicate with networking control agents (in other words, a network
    switch) it should use a virtual connection to the network control agent that it established in its 
    <i>ProtocolBindAdapterEx</i> function. Stand-alone call managers communicate through the underlying
    miniport driver by calling 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscosendnetbufferlists">NdisCoSendNetBufferLists</a>.
    Miniport drivers with integrated call-management support never call 
    <b>NdisCoSendNetBufferLists</b>. Instead, they transmit the data directly across the network.

In addition, 
    <i>ProtocolCmRegisterSap</i> should perform any necessary allocations of dynamic resources and structures
    that the call manager needs to maintain state information about the SAP on behalf of the
    connection-oriented client. Such resources include, but are not limited to, memory buffers, data
    structures, events, and other such similar resources. A call manager must also initialize any resources
    it allocates before returning control to NDIS. Call managers must store the NDIS-supplied handle
    identifying the SAP, provided at 
    <i>NdisSapHandle</i>, in their context area for future use.

If 
    <i>ProtocolCmRegisterSap</i> will return NDIS_STATUS_SUCCESS, it should, after allocating the per-SAP
    state area, set the address of this state area in 
    <i>CallMgrSapContext</i> before returning control to NDIS. To do this, dereference 
    <i>CallMgrSapContext</i> and store a pointer to the data area as the value of the handle. For example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>*CallMgrSapContext = SomeBuffer ;</pre>
</td>
</tr>
</table></span></div>
If the given SAP that is already registered by another connection-oriented client, the call manager
    must fail the request and return NDIS_STATUS_INVALID_DATA.

After a call manager has registered a SAP on behalf of a connection-oriented client, it notifies that
    client of an incoming call offer directed to that SAP by calling 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmdispatchincomingcall">
    NdisCmDispatchIncomingCall</a>.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolCmRegisterSap</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCmRegisterSap</i> function that is named "MyCmRegisterSap", use the <b>PROTOCOL_CM_REG_SAP</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CM_REG_SAP MyCmRegisterSap;</pre>
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
 MyCmRegisterSap(
    NDIS_HANDLE  CallMgrAfContext,
    PCO_SAP  Sap,
    NDIS_HANDLE  NdisSapHandle,
    PNDIS_HANDLE  CallMgrSapContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CM_REG_SAP</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CM_REG_SAP</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmdispatchincomingcall">NdisCmDispatchIncomingCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmregistersapcomplete">NdisCmRegisterSapComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscosendnetbufferlists">NdisCoSendNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_deregister_sap">ProtocolCmDeregisterSap</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_open_af">ProtocolCmOpenAf</a>
 

 

