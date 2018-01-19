---
UID: NC:ndis.PROTOCOL_CM_DROP_PARTY
title: PROTOCOL_CM_DROP_PARTY
author: windows-driver-content
description: The ProtocolCmDropParty function is required.
old-location: netvista\protocolcmdropparty.htm
old-project: netvista
ms.assetid: be0fce3e-7308-42fa-b63a-4d5cfec7ea6c
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    ProtocolCmDropParty (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    ProtocolCmDropParty (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ProtocolCmDropParty
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

# PROTOCOL_CM_DROP_PARTY callback



## -description
The 
  <i>ProtocolCmDropParty</i> function is required. NDIS calls 
  <i>ProtocolCmDropParty</i> to request that the call manager remove a party from an existing multipoint
  call.



## -prototype

````
PROTOCOL_CM_DROP_PARTY ProtocolCmDropParty;

NDIS_STATUS ProtocolCmDropParty(
  _In_     NDIS_HANDLE CallMgrPartyContext,
  _In_opt_ PVOID       CloseData,
  _In_opt_ UINT        Size
)
{ ... }
````


## -parameters

### -param CallMgrPartyContext [in]

Specifies the handle to a call manager-allocated context area in which the call manager maintains
     its per-party state. This handle was provided to NDIS in the call managers 
     <a href="..\ndis\nc-ndis-protocol_cm_add_party.md">ProtocolCmAddParty</a> function.


### -param CloseData [in, optional]

Pointer to a buffer containing connection-oriented client-specific data that should be sent across
     the connection before the party is dropped. This parameter is <b>NULL</b> if the underlying network medium does
     not support transfers of data when closing a connection.


### -param Size [in, optional]

Specifies the length, in bytes, of the buffer at 
     <i>CloseData</i>, zero if 
     <i>CloseData</i> is <b>NULL</b>.


## -returns
<i>ProtocolCmDropParty</i> returns the status of its operation(s) as one of the following values:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>Indicates that the call manager has successfully dropped the party, sent any close data, and
       free the resources that were allocated for its context area.
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>Indicates that the call manager will complete the request to drop the party asynchronously. The
       call manager must call 
       <a href="..\ndis\nf-ndis-ndiscmdroppartycomplete.md">NdisCmDropPartyComplete</a> when
       all processing has been finished to notify NDIS and the requesting actor that the party has been
       dropped.
<dl>
<dt><b>NDIS_STATUS_INVALID_DATA</b></dt>
</dl>Indicates that 
       <i>CloseData</i> was specified to the call manager, but the media type does not support sending data
       concurrent with connection termination.

 


## -remarks
<i>ProtocolCmDropParty</i> communicates with network control devices or other media-specific agents, as
    necessary for its media, to drop a party from an existing multipoint call. If the call manager is
    required to communicated with network control agents (such as, a networking switch) it should use a
    virtual connection to the network control agents that it established in its 
    <a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">
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

To define a <i>ProtocolCmDropParty</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCmDropParty</i> function that is named "MyCmDropParty", use the <b>PROTOCOL_CM_DROP_PARTY</b> type as shown in this code example:

Then, implement your function as follows:

The <b>PROTOCOL_CM_DROP_PARTY</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CM_DROP_PARTY</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


## -see-also
<dl>
<dt>
<a href="..\ndis\nf-ndis-ndiscmdroppartycomplete.md">NdisCmDropPartyComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cm_add_party.md">ProtocolCmAddParty</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_CM_DROP_PARTY callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

