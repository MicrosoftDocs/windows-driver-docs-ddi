---
UID: NC:ndis.PROTOCOL_CM_OPEN_AF
title: PROTOCOL_CM_OPEN_AF
description: The ProtocolCmOpenAf function is required.
old-location: netvista\protocolcmopenaf.htm
tech.root: netvista
ms.assetid: 7422c205-bc41-4121-b430-ff9e6b49dc2e
ms.date: 05/02/2018
ms.keywords: PROTOCOL_CM_OPEN_AF, PROTOCOL_CM_OPEN_AF callback, ProtocolCmOpenAf, ProtocolCmOpenAf callback function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_2dbd2a83-f6e5-4324-9419-6a39a8e81f41.xml, ndis/ProtocolCmOpenAf, netvista.protocolcmopenaf
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    ProtocolCmOpenAf (NDIS 5.1))   in Windows Vista. Supported for NDIS 5.1 drivers (see    ProtocolCmOpenAf (NDIS 5.1))   in Windows XP.
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
-	ProtocolCmOpenAf
product:
- Windows
targetos: Windows
req.typenames: 
---

# PROTOCOL_CM_OPEN_AF callback function


## -description


The 
  <i>ProtocolCmOpenAf</i> function is required. This function allocates per-open resources for a call manager
  to interact with a connection-oriented NDIS client that is opening the address family.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CM_OPEN_AF</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters




### -param CallMgrBindingContext [in]

For a non-integrated call manager, <i>CallMgrBindingContext</i> specifies the handle to a call manager-allocated context area in which the call managers maintains
     its per-binding state information. The call manager supplied this handle when it called 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>.

For an integrated call manager (MCM), <i>CallMgrBindingContext</i> specifies the handle to a miniport-allocated context area in which the miniport maintains its per-adapter state information.  The miniport supplied this handle in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff553623">NdisMSetAttributesEx</a> call (for 5.x drivers) or its <a href="https://msdn.microsoft.com/library/windows/hardware/ff563672">NdisMSetMiniportAttributes</a> call (for 6.x drivers).


### -param AddressFamily [in]

Specifies the address family that a client is opening. This address family was registered by the
     call manager when it called 
     <a href="https://msdn.microsoft.com/8890bf31-f2c7-48b0-926d-8931893ede86">
     NdisCmRegisterAddressFamilyEx</a>.


### -param NdisAfHandle [in]

Specifies a handle, supplied by NDIS, that uniquely identifies this address family instance. This
     handle is opaque to the call manager and reserved for system use.


### -param CallMgrAfContext [out]

Specifies the handle to a call manager-supplied context area in which the call manager maintains
     state about this open of an address family it provides.


## -returns



<i>ProtocolCmOpenAf</i> returns the status of its operation(s) as one of the following:

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
Indicates that the call manager has successfully allocated and initialized any resources
       necessary to accept requests from the client to this address family.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the requested operation is being handled asynchronously. The call manager must
       call 
       <a href="https://msdn.microsoft.com/eed57341-0b1a-4697-b05d-680bc17da796">
       NdisCmOpenAddressFamilyComplete</a> when it has completed all its open-AF operations to indicate to
       NDIS (and the client) that the operation(s) has been completed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the call manager could not complete its necessary operation(s) because of a lack
       of available system resources, such as memory.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_<i>XXX</i></b></dt>
</dl>
</td>
<td width="60%">
Indicates that the call manager could not set itself into a state where it can accept requests
       from the client to operate on this address family. This could be an error status propagated from
       another NDIS library function or any error status determined appropriate by the driver writer.

</td>
</tr>
</table>
 




## -remarks



<i>ProtocolCmOpenAf</i> performs any required allocations of dynamic resources and structures that the
    call manager writer deems necessary to perform operations on behalf of the client that is opening an
    instance of this address family. Such resources include, but are not limited to, memory buffers, data
    structures, events, and other such similar resources. A call manager should also initialize any relevant
    per-open data before returning control to NDIS.

When a call manager has allocated its per-open state area, the address of the state area should be set
    in the 
    <i>CallMgrAfContext</i> handle before returning control to NDIS. To do this, dereference 
    <i>CallMgrAfContext</i> and store a pointer to the data area as the value of the handle. For example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>*CallMgrAfContext = SomeBuffer;</pre>
</td>
</tr>
</table></span></div>
If 
    <i>ProtocolCmOpenAf</i> cannot allocate the per-open resources it needs to carry out subsequent requests
    on behalf of the client opening this address family, it should free all resources that it allocated for
    the open and return control to the NDIS with NDIS_STATUS_RESOURCES.

If 
    <i>ProtocolCmOpenAf</i> has completed its required operations and the CM is ready to accept requests from
    the client, 
    <i>ProtocolCmOpenAf</i> should return control as quickly as possible with a status of
    NDIS_STATUS_SUCCESS.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolCmOpenAf</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCmOpenAf</i> function that is named "MyCmOpenAf", use the <b>PROTOCOL_CM_OPEN_AF</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CM_OPEN_AF MyCmOpenAf;</pre>
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
 MyCmOpenAf(
    NDIS_HANDLE  CallMgrBindingContext,
    PCO_ADDRESS_FAMILY  AddressFamily,
    NDIS_HANDLE  NdisAfHandle,
    PNDIS_HANDLE  CallMgrAfContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CM_OPEN_AF</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CM_OPEN_AF</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561639">NdisClOpenAddressFamilyEx</a>



<a href="https://msdn.microsoft.com/eed57341-0b1a-4697-b05d-680bc17da796">
   NdisCmOpenAddressFamilyComplete</a>



<a href="https://msdn.microsoft.com/8890bf31-f2c7-48b0-926d-8931893ede86">
   NdisCmRegisterAddressFamilyEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>
 

 

