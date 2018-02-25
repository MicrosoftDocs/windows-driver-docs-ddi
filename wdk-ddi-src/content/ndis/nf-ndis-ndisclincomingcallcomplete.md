---
UID: NF:ndis.NdisClIncomingCallComplete
title: NdisClIncomingCallComplete function
author: windows-driver-content
description: NdisClIncomingCallComplete returns a client's acceptance or rejection of an offered incoming call, for which the client's ProtocolClIncomingCall function previously returned NDIS_STATUS_PENDING.
old-location: netvista\ndisclincomingcallcomplete.htm
old-project: netvista
ms.assetid: b3931dd7-319e-4ef8-9812-6dc3f2e41b2c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , C, I, N, NdisClIncomingCallComplete, NdisClIncomingCallComplete function [Network Drivers Starting with Windows Vista], a, c, condis_client_ref_93263dd6-f55a-4923-8173-b3617f40353a.xml, d, e, g, i, l, m, n, ndis/NdisClIncomingCallComplete, netvista.ndisclincomingcallcomplete, o, p, s, t"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisClIncomingCallComplete   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisClIncomingCallComplete   (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Protocol_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisClIncomingCallComplete
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisClIncomingCallComplete function


## -description


<b>NdisClIncomingCallComplete</b> returns a client's acceptance or rejection of an offered incoming call,
  for which the client's 
  <a href="..\ndis\nc-ndis-protocol_cl_incoming_call.md">ProtocolClIncomingCall</a> function
  previously returned NDIS_STATUS_PENDING.


## -syntax


````
VOID NdisClIncomingCallComplete(
  _In_ NDIS_STATUS         Status,
  _In_ NDIS_HANDLE         NdisVcHandle,
  _In_ PCO_CALL_PARAMETERS CallParameters
);
````


## -parameters




### -param Status [in]

Is set to NDIS_STATUS_SUCCESS if the client accepts the offered call. Otherwise, this parameter
     can be set to any NDIS_STATUS_<i>XXX</i> except NDIS_STATUS_PENDING to indicate the client-determined reason for rejecting the
     call.


### -param NdisVcHandle [in]

Specifies the handle to the VC that was created by the call manager to represent the incoming
     call. The client obtained this handle from it per-VC state designated by the 
     <i>ProtocolVcContext</i> passed as an input parameter to its 
     <a href="..\ndis\nc-ndis-protocol_cl_incoming_call.md">
     ProtocolClIncomingCall</a> function.


### -param CallParameters [in]

Pointer to a structure of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>, specifying the call
     parameters for the incoming call.


## -returns



None




## -remarks



If a client's 
    <a href="..\ndis\nc-ndis-protocol_cl_incoming_call.md">ProtocolClIncomingCall</a> function
    returns NDIS_STATUS_PENDING for an offered call incoming on a particular SAP, previously registered by
    the client with 
    <a href="..\ndis\nf-ndis-ndisclregistersap.md">NdisClRegisterSap</a>, the client
    subsequently must call 
    <b>NdisClIncomingCallComplete</b> to indicate whether it is accepting or rejecting the offered call.

Before it calls 
    <b>NdisClIncomingCallComplete</b>, such a client can negotiate with the call manager by calling 
    <a href="..\ndis\nf-ndis-ndisclmodifycallqos.md">NdisClModifyCallQoS</a> one or more times
    until both drivers reach an agreement on an acceptable quality of service for the incoming call or the
    client determines it should reject the offered call because its attempts to modify the QoS reach some
    client-determined limit without resulting in an agreement.

If the client has changed the call parameters passed in to its 
    <a href="https://msdn.microsoft.com/9143a8aa-56e0-40ad-aecb-19a10de64269">ProtocolClIncomingCall</a> function, it must set
    the 
    <b>Flags</b> member in the 
    <b>CO_CALL_PARAMETERS</b> structure with
    CALL_PARAMETERS_CHANGED when it passes these changes to 
    <b>NdisClIncomingCallComplete</b>. Depending on whether the call manager accepts or rejects the client's
    proposed changes to the call parameters, NDIS subsequently calls either the client's
    <a href="..\ndis\nc-ndis-protocol_cl_call_connected.md">
    ProtocolClCallConnected</a> function or its 
    <a href="..\ndis\nc-ndis-protocol_cl_incoming_close_call.md">
    ProtocolClIncomingCloseCall</a> function, respectively.

A call to 
    <b>NdisClIncomingCallComplete</b> causes NDIS to call the CM's 
    <a href="..\ndis\nc-ndis-protocol_cm_incoming_call_complete.md">
    ProtocolCmIncomingCallComplete</a> function. NDIS passes the client-supplied parameters of 
    <b>NdisClIncomingCallComplete</b> as input parameters to 
    <i>ProtocolCmIncomingCallComplete</i>.

If a client rejects an offered call by setting 
    <i>Status</i> to something other than NDIS_STATUS_SUCCESS, the client must consider the 
    <i>CallParameters</i> pointer invalid as soon as its call to 
    <b>NdisClIncomingCallComplete</b> occurs.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>



<a href="..\ndis\nf-ndis-ndiscmdispatchincomingcall.md">NdisCmDispatchIncomingCall</a>



<a href="..\ndis\nc-ndis-protocol_cm_incoming_call_complete.md">
   ProtocolCmIncomingCallComplete</a>



<a href="..\ndis\nf-ndis-ndisclregistersap.md">NdisClRegisterSap</a>



<a href="..\ndis\nc-ndis-protocol_cl_incoming_close_call.md">ProtocolClIncomingCloseCall</a>



<a href="..\ndis\nf-ndis-ndisclmodifycallqos.md">NdisClModifyCallQoS</a>



<a href="..\ndis\nc-ndis-protocol_cl_incoming_call.md">ProtocolClIncomingCall</a>



<a href="..\ndis\nc-ndis-protocol_cl_call_connected.md">ProtocolClCallConnected</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisClIncomingCallComplete function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

