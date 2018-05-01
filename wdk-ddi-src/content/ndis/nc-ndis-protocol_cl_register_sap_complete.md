---
UID: NC:ndis.PROTOCOL_CL_REGISTER_SAP_COMPLETE
title: PROTOCOL_CL_REGISTER_SAP_COMPLETE
author: windows-driver-content
description: A connection-oriented NDIS client that accepts incoming calls must have a ProtocolClRegisterSapComplete function to complete the asynchronous operations that it initiates with NdisClRegisterSap.
old-location: netvista\protocolclregistersapcomplete.htm
old-project: netvista
ms.assetid: b0a2a224-3353-4f20-b14f-ed5d633a6ead
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: PROTOCOL_CL_REGISTER_SAP_COMPLETE, PROTOCOL_CL_REGISTER_SAP_COMPLETE callback, ProtocolClRegisterSapComplete, ProtocolClRegisterSapComplete callback function [Network Drivers Starting with Windows Vista], condis_client_ref_6f2cf710-53e9-43ce-8b9a-46ec76d1146d.xml, ndis/ProtocolClRegisterSapComplete, netvista.protocolclregistersapcomplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       ProtocolClRegisterSapComplete (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       ProtocolClRegisterSapComplete (NDIS 5.1)) in Windows XP.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	ProtocolClRegisterSapComplete
product: Windows
targetos: Windows
req.typenames: 
---

# PROTOCOL_CL_REGISTER_SAP_COMPLETE callback function


## -description


A connection-oriented NDIS client that accepts incoming calls must have 
  a <i>ProtocolClRegisterSapComplete</i> function to complete the asynchronous operations that it initiates
  with 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff561648">NdisClRegisterSap</a>. Otherwise, such a
  protocol driver's registered 
  <i>ProtocolClRegisterSapComplete</i> function can simply return control.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CL_REGISTER_SAP_COMPLETE</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters




### -param Status [in]

Specifies the final status of the client's call to 
     <b>NdisClRegisterSap</b>, which can be one of the following:
     





#### NDIS_STATUS_SUCCESS

The SAP has been registered both with NDIS and the call manager, which will subsequently call 
       <a href="https://msdn.microsoft.com/2172aeec-8502-414e-9d01-9292c0eb7ce8">
       NdisCmDispatchIncomingCall</a> whenever it receives an incoming call offer directed to the given
       SAP, thereby causing NDIS to call the client's 
       <a href="https://msdn.microsoft.com/8a5922ac-b22b-444e-9ea0-3bb56e71ef33">
       ProtocolClIncomingCall</a> function.



#### NDIS_STATUS_RESOURCES

NDIS or the call manager could not allocate and/or initialize necessary resources to register
       and maintain the SAP.



#### NDIS_STATUS_INVALID_DATA

The client supplied an invalid specification at 
       <i>Sap</i> to NDIS, which it forwarded to the call manager's 
       <a href="https://msdn.microsoft.com/3e3e7a0e-a8d2-40b2-895b-187d24867080">ProtocolCmRegisterSap</a> function
       for validation.



#### NDIS_STATUS_XXX

The call manager encountered an error in attempting to register the given SAP and NDIS
       propagated this CM-determined failure status to the client.


### -param ProtocolSapContext [in]

Specifies the handle to the client's per-SAP context area, which the client originally supplied to
     NDIS when it called 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff561648">NdisClRegisterSap</a>. If the registration
     is successful, NDIS retains this context handle and uses it subsequently in calls to the client's 
     <i>ProtocolClIncomingCall</i> function pertaining to this SAP.


### -param Sap [in]

Pointer to the client-allocated buffer containing the specification for the SAP to be opened. The
     client originally passed this pointer to 
     <b>NdisClRegisterSap</b>.


### -param NdisSapHandle [in]

If 
     <i>Status</i> is NDIS_STATUS_SUCCESS, specifies an NDIS-supplied valid handle to this registered SAP,
     effectively an association established with NDIS between the client and a particular call manager for
     the client-specified SAP. Otherwise, this parameter is <b>NULL</b>. The client must save a valid handle,
     preferably in its 
     <i>ProtocolSapContext</i> area, for an eventual call to 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff561628">NdisClDeregisterSap</a>.


## -returns



None




## -remarks



NDIS calls 
    <i>ProtocolClRegisterSapComplete</i> to indicate that the client's previous call to 
    <b>NdisClRegisterSap</b> has been processed by NDIS and, if NDIS did not fail the call, by the call
    manager with which the client shares the 
    <i>NdisAfHandle</i> that it passed to 
    <b>NdisClRegisterSap</b>.

To receive incoming calls through a connection-oriented NIC, a client's 
    <a href="https://msdn.microsoft.com/272d99da-ef08-4ebd-90e7-74e99410b3f5">
    ProtocolCoAfRegisterNotify</a> or 
    <a href="https://msdn.microsoft.com/03ddbbfd-8fe8-44b6-8d3e-12a7bf6f8f6b">
    ProtocolClOpenAfCompleteEx</a> function usually registers one or more SAPs with the call manager.

To register each SAP, the client calls 
    <b>NdisClRegisterSap</b>, passing in the 
    <i>NdisAfHandle</i> that identifies the call manager from which the client wants to receive notifications
    of incoming calls, and NDIS returns the client an 
    <i>NdisSapHandle</i> to the registered SAP if the client's call to 
    <b>NdisClRegisterSap</b> succeeds. 
    <i>ProtocolClRegisterSapComplete</i> must save each valid 
    <i>NdisSapHandle</i>, usually in the client's per-SAP 
    <i>ProtocolSapContext</i> area so it can release the SAP later with 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561628">NdisClDeregisterSap</a>.

The format of a SAP is specific to the call manager. If the call manager does not recognize the SAP
    that the client is attempting to register or if the specified SAP is already in use, the call manager can
    fail the SAP registration. 
    <i>ProtocolClRegisterSapComplete</i> should check the input 
    <i>Status</i> for NDIS_STATUS_SUCCESS before proceding further. If the attempt to register the SAP failed,
    
    <i>ProtocolClRegisterSapComplete</i> can either release the per-SAP context area and buffer at 
    <i>Sap</i> that the client allocated or prepare them for reuse in another call to 
    <b>NdisClRegisterSap</b>.

A client can receive incoming calls on a SAP even while SAP registration is still pending, that is,
    before its 
    <i>ProtocolClRegisterSapComplete</i> function is called.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolClRegisterSapComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolClRegisterSapComplete</i> function that is named "MyClRegisterSapComplete", use the <b>PROTOCOL_CL_REGISTER_SAP_COMPLETE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CL_REGISTER_SAP_COMPLETE MyClRegisterSapComplete;</pre>
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
VOID
 MyClRegisterSapComplete(
    NDIS_STATUS  Status,
    NDIS_HANDLE  ProtocolSapContext,
    PCO_SAP  Sap,
    NDIS_HANDLE  NdisSapHandle
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CL_REGISTER_SAP_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CL_REGISTER_SAP_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561628">NdisClDeregisterSap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561648">NdisClRegisterSap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561664">NdisCmDispatchIncomingCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561689">NdisCmRegisterSapComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562577">NdisFreeMemory</a>



<a href="https://msdn.microsoft.com/2405a405-177a-420a-9628-a340e0d0acb3">
   NdisFreeToNPagedLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562830">NdisMCmDispatchIncomingCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563557">NdisMCmRegisterSapComplete</a>



<a href="https://msdn.microsoft.com/8a5922ac-b22b-444e-9ea0-3bb56e71ef33">ProtocolClIncomingCall</a>



<a href="https://msdn.microsoft.com/03ddbbfd-8fe8-44b6-8d3e-12a7bf6f8f6b">ProtocolClOpenAfCompleteEx</a>



<a href="https://msdn.microsoft.com/3e3e7a0e-a8d2-40b2-895b-187d24867080">ProtocolCmRegisterSap</a>



<a href="https://msdn.microsoft.com/272d99da-ef08-4ebd-90e7-74e99410b3f5">ProtocolCoAfRegisterNotify</a>
 

 

