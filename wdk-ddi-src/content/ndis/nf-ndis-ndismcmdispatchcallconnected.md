---
UID: NF:ndis.NdisMCmDispatchCallConnected
title: NdisMCmDispatchCallConnected macro (ndis.h)
description: NdisMCmDispatchCallConnected notifies NDIS and the client that data transfers can begin on a VC that the MCM driver created for an incoming call initiated on a remote node.
old-location: netvista\ndismcmdispatchcallconnected.htm
tech.root: netvista
ms.assetid: b47976ad-fdde-48cb-bb30-4eaf25489143
ms.date: 05/02/2018
ms.keywords: NdisMCmDispatchCallConnected, NdisMCmDispatchCallConnected macro [Network Drivers Starting with Windows Vista], condis_mcm_ref_3d3199be-36e5-445e-986d-984a4f778da0.xml, ndis/NdisMCmDispatchCallConnected, netvista.ndismcmdispatchcallconnected
ms.topic: macro
f1_keywords:
 - "ndis/NdisMCmDispatchCallConnected"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCmDispatchCallConnected   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCmDispatchCallConnected   (NDIS 5.1)) in Windows XP.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndis.h
api_name:
- NdisMCmDispatchCallConnected
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMCmDispatchCallConnected macro


## -description


<b>NdisMCmDispatchCallConnected</b> notifies NDIS and the client that data transfers can begin on a VC that
  the MCM driver created for an 
  <i>incoming</i> call initiated on a remote node.


## -parameters




### -param _H_

Specifies the handle to the VC that represents the connection, created with 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismcmcreatevc">NdisMCmCreateVc</a> when the MCM driver set
     up the VC for the incoming call.

## -remarks



An MCM driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cm_incoming_call_complete">
    ProtocolCmIncomingCallComplete</a> function calls 
    <b>NdisMCmDispatchCallConnected</b> to complete the final handshake for an incoming call from a remote
    node, which the local client has already accepted.

A call to 
    <b>NdisMCmDispatchCallConnected</b> causes NDIS to call the client's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cl_call_connected">
    ProtocolClCallConnected</a> function.

Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmDispatchCallConnected</b>. Stand-alone call managers, which register themselves with NDIS as
    protocol drivers, call 
    <b>NdisCmDispatchCallConnected</b> instead.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndiscmdispatchcallconnected">NdisCmDispatchCallConnected</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismcmcreatevc">NdisMCmCreateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismcmdispatchincomingcall">NdisMCmDispatchIncomingCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cl_call_connected">ProtocolClCallConnected</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cm_incoming_call_complete">
   ProtocolCmIncomingCallComplete</a>
 

 

