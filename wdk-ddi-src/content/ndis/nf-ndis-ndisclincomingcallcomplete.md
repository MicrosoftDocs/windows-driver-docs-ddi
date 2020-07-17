---
UID: NF:ndis.NdisClIncomingCallComplete
title: NdisClIncomingCallComplete function (ndis.h)
description: NdisClIncomingCallComplete returns a client's acceptance or rejection of an offered incoming call, for which the client's ProtocolClIncomingCall function previously returned NDIS_STATUS_PENDING.
old-location: netvista\ndisclincomingcallcomplete.htm
tech.root: netvista
ms.assetid: b3931dd7-319e-4ef8-9812-6dc3f2e41b2c
ms.date: 05/02/2018
keywords: ["NdisClIncomingCallComplete function"]
ms.keywords: NdisClIncomingCallComplete, NdisClIncomingCallComplete function [Network Drivers Starting with Windows Vista], condis_client_ref_93263dd6-f55a-4923-8173-b3617f40353a.xml, ndis/NdisClIncomingCallComplete, netvista.ndisclincomingcallcomplete
f1_keywords:
 - "ndis/NdisClIncomingCallComplete"
 - "NdisClIncomingCallComplete"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisClIncomingCallComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisClIncomingCallComplete function


## -description


<b>NdisClIncomingCallComplete</b> returns a client's acceptance or rejection of an offered incoming call,
  for which the client's 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_call">ProtocolClIncomingCall</a> function
  previously returned NDIS_STATUS_PENDING.


## -parameters




### -param Status [in]

Is set to NDIS_STATUS_SUCCESS if the client accepts the offered call. Otherwise, this parameter
     can be set to any NDIS_STATUS_<i>XXX</i> except NDIS_STATUS_PENDING to indicate the client-determined reason for rejecting the
     call.


### -param NdisVcHandle [in]

Specifies the handle to the VC that was created by the call manager to represent the incoming
     call. The client obtained this handle from it per-VC state designated by the 
     <i>ProtocolVcContext</i> passed as an input parameter to its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_call">
     ProtocolClIncomingCall</a> function.


### -param CallParameters [in]

Pointer to a structure of type 
     <a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff545384(v=vs.85)">CO_CALL_PARAMETERS</a>, specifying the call
     parameters for the incoming call.


## -remarks



If a client's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_call">ProtocolClIncomingCall</a> function
    returns NDIS_STATUS_PENDING for an offered call incoming on a particular SAP, previously registered by
    the client with 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclregistersap">NdisClRegisterSap</a>, the client
    subsequently must call 
    <b>NdisClIncomingCallComplete</b> to indicate whether it is accepting or rejecting the offered call.

Before it calls 
    <b>NdisClIncomingCallComplete</b>, such a client can negotiate with the call manager by calling 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclmodifycallqos">NdisClModifyCallQoS</a> one or more times
    until both drivers reach an agreement on an acceptable quality of service for the incoming call or the
    client determines it should reject the offered call because its attempts to modify the QoS reach some
    client-determined limit without resulting in an agreement.

If the client has changed the call parameters passed in to its 
    <a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff545384(v=vs.85)">ProtocolClIncomingCall</a> function, it must set
    the 
    <b>Flags</b> member in the 
    <b>CO_CALL_PARAMETERS</b> structure with
    CALL_PARAMETERS_CHANGED when it passes these changes to 
    <b>NdisClIncomingCallComplete</b>. Depending on whether the call manager accepts or rejects the client's
    proposed changes to the call parameters, NDIS subsequently calls either the client's
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_call_connected">
    ProtocolClCallConnected</a> function or its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_close_call">
    ProtocolClIncomingCloseCall</a> function, respectively.

A call to 
    <b>NdisClIncomingCallComplete</b> causes NDIS to call the CM's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_incoming_call_complete">
    ProtocolCmIncomingCallComplete</a> function. NDIS passes the client-supplied parameters of 
    <b>NdisClIncomingCallComplete</b> as input parameters to 
    <i>ProtocolCmIncomingCallComplete</i>.

If a client rejects an offered call by setting 
    <i>Status</i> to something other than NDIS_STATUS_SUCCESS, the client must consider the 
    <i>CallParameters</i> pointer invalid as soon as its call to 
    <b>NdisClIncomingCallComplete</b> occurs.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff545384(v=vs.85)">CO_CALL_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclmodifycallqos">NdisClModifyCallQoS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclregistersap">NdisClRegisterSap</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmdispatchincomingcall">NdisCmDispatchIncomingCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_call_connected">ProtocolClCallConnected</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_call">ProtocolClIncomingCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_close_call">ProtocolClIncomingCloseCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_incoming_call_complete">
   ProtocolCmIncomingCallComplete</a>
 

 

