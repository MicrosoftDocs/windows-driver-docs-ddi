---
UID: NF:ndis.NdisMCmDispatchIncomingCall
title: NdisMCmDispatchIncomingCall macro (ndis.h)
description: NdisMCmDispatchIncomingCall informs the client of an incoming call on a SAP previously registered by that client with the MCM driver.
old-location: netvista\ndismcmdispatchincomingcall.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisMCmDispatchIncomingCall macro"]
ms.keywords: NdisMCmDispatchIncomingCall, NdisMCmDispatchIncomingCall macro [Network Drivers Starting with Windows Vista], condis_mcm_ref_1133faf8-d5a6-4800-8738-94b11bc1d51f.xml, ndis/NdisMCmDispatchIncomingCall, netvista.ndismcmdispatchincomingcall
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCmDispatchIncomingCall   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCmDispatchIncomingCall   (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_MCM_Function
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
 - NdisMCmDispatchIncomingCall
 - ndis/NdisMCmDispatchIncomingCall
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NdisMCmDispatchIncomingCall
---

# NdisMCmDispatchIncomingCall macro


## -description

<b>NdisMCmDispatchIncomingCall</b> informs the client of an incoming call on a SAP previously registered by
  that client with the MCM driver.

## -parameters

### -param _SH_

Specifies the handle identifying the SAP. NDIS set up this handle when the client originally
     called 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclregistersap">NdisClRegisterSap</a>, and the MCM driver
     obtained this handle as an input parameter to its 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_reg_sap">
     ProtocolCmRegisterSap</a> function.

### -param _VH_

Specifies the handle identifying the VC, created with 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmcreatevc">NdisMCmCreateVc</a> when the MCM driver
     processes the incoming call offer directed to this registered SAP.

### -param _CP_

Pointer to a structure of type 
     <a href="/previous-versions/windows/hardware/network/ff545384(v=vs.85)">CO_CALL_PARAMETERS</a> that specifies the call
     and media parameters for the VC.

## -remarks

Before calling 
    <b>NdisMCmDispatchIncomingCall</b>, an MCM driver has already done the following:

<ul>
<li>
Identified the target SAP, previously registered by a particular client, for the call (actually, a
      request to make a connection) that it received over the network

</li>
<li>
Created a VC for the incoming call with 
      <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmcreatevc">NdisMCmCreateVc</a>


</li>
<li>
Possibly negotiated about acceptable call parameters over the network, or accepted the call
      parameters sent from the remote node

</li>
<li>
Activated the VC with 
      <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmactivatevc">NdisMCmActivateVc</a> to notify NDIS that
      it is ready for transfers on the VC in accord with the negotiated or accepted call parameters

</li>
</ul>
The MCM driver's call to 
    <b>NdisMCmDispatchIncomingCall</b> causes NDIS to call the client's 
    <i>ProtocolClIncomingCall</i> function, within which the client either accepts or rejects the requested
    connection. After deciding whether to accept the connection, the client calls 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclincomingcallcomplete">NdisClIncomingCallComplete</a>,
    which, in turn, calls the MCM driver's 
    <i>ProtocolCmIncomingCallComplete</i> function. If the client accepted the call, the MCM driver next calls    
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmdispatchcallconnected">
    NdisMCmDispatchCallConnected</a>. Otherwise, it deactivates (and possibly deletes) the VC it created,
    after notifying the remote node that the offered call was rejected.

Only connection-oriented miniport drivers that provide integrated call-management support call 
    <b>NdisMCmDispatchIncomingCall</b>. Stand-alone call managers, which register themselves with NDIS as
    protocol drivers, call 
    <b>NdisCmDispatchIncomingCall</b> instead.

## -see-also

<a href="/previous-versions/windows/hardware/network/ff545384(v=vs.85)">CO_CALL_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_interrupt_dpc">MiniportInterruptDPC</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclincomingcallcomplete">NdisClIncomingCallComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclregistersap">NdisClRegisterSap</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmdispatchincomingcall">NdisCmDispatchIncomingCall</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmactivatevc">NdisMCmActivateVc</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmcreatevc">NdisMCmCreateVc</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmdeactivatevc">NdisMCmDeactivateVc</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmdeletevc">NdisMCmDeleteVc</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmdispatchcallconnected">NdisMCmDispatchCallConnected</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_call">ProtocolClIncomingCall</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_incoming_call_complete">
   ProtocolCmIncomingCallComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_reg_sap">ProtocolCmRegisterSap</a>
