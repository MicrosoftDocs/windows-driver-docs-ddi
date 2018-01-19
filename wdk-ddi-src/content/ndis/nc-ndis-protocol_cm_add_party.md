---
UID: NC:ndis.PROTOCOL_CM_ADD_PARTY
title: PROTOCOL_CM_ADD_PARTY
author: windows-driver-content
description: The ProtocolCmAddParty function is a required function.
old-location: netvista\protocolcmaddparty.htm
old-project: netvista
ms.assetid: 06aa5ff6-974c-43dd-8395-bc1a1a8421d5
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    ProtocolCmAddParty (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    ProtocolCmAddParty (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ProtocolCmAddParty
req.alt-loc: Ndis.h
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
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# PROTOCOL_CM_ADD_PARTY callback



## -description
The 
  <i>ProtocolCmAddParty</i> function is a required function. 
  <i>ProtocolCmAddParty</i> sets up the media-specific parameters to add a party to an existing multipoint
  call, stores state data for the new party, and causes the party to be added to the call.



## -prototype

````
PROTOCOL_CM_ADD_PARTY ProtocolCmAddParty;

NDIS_STATUS ProtocolCmAddParty(
  _In_    NDIS_HANDLE         CallMgrVcContext,
  _Inout_ PCO_CALL_PARAMETERS CallParameters,
  _In_    NDIS_HANDLE         NdisPartyHandle,
  _Out_   PNDIS_HANDLE        CallMgrPartyContext
)
{ ... }
````


## -parameters

### -param CallMgrVcContext [in]

Specifies the handle to a call manager-allocated context area in which the call manager maintains
     its per-VC state. The call manager supplied this handle to NDIS from its 
     <a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a> function.


### -param CallParameters [in, out]

Pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a> structure that contains
     the parameters, specified by a connection-oriented client, for the party that is being added to an
     existing call.


### -param NdisPartyHandle [in]

Specifies a handle, supplied by NDIS, that uniquely identifies a multipoint party that is to be
     added to an existing virtual connection. This handle is opaque to the call manager and reserved for NDIS
     library use.


### -param CallMgrPartyContext [out]

Specifies, on return, a handle to a call manager-supplied context area in which the call manager
     maintains state about this party for the multipoint call.


## -returns
<i>ProtocolCmAddParty</i> returns the status of its operation(s) as one of the following:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>Indicates that the call manager successfully allocated the necessary resources to maintain state
       about the party and successfully added the party to the call.
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>Indicates that the call manager will complete the request to add a party asynchronously. When
       the call manager has completed all operations for adding the party, it must call 
       <a href="..\ndis\nf-ndis-ndiscmaddpartycomplete.md">NdisCmAddPartyComplete</a> to signal
       NDIS that this operation has been completed.
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>Indicates that the call manager was unable to allocate and/or initialize its resources for
       adding a party to the connection.
<dl>
<dt><b>NDIS_STATUS_NOT_SUPPORTED</b></dt>
</dl>Indicates that the call manager was unable to add the party to the multipoint call because the
       caller requested invalid or unavailable features in the call parameters at 
       <i>CallParameters</i> or else that the media type supported by this call manager does not support
       multipoint calls.

 


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

Call managers perform any necessary communication with their network hardware or other media-specific
    actors, as necessary, to add the party specified by the call parameters at 
    <i>CallParameters</i> to an existing multipoint call.

To define a <i>ProtocolCmAddParty</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCmAddParty</i> function that is named "MyCmAddParty", use the <b>PROTOCOL_CM_ADD_PARTY</b> type as shown in this code example:

Then, implement your function as follows:

The <b>PROTOCOL_CM_ADD_PARTY</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CM_ADD_PARTY</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


## -see-also
<dl>
<dt>
<a href="..\ndis\nf-ndis-ndiscladdparty.md">NdisClAddParty</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cl_add_party_complete.md">ProtocolClAddPartyComplete</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_CM_ADD_PARTY callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

