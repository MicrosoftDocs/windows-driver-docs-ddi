---
UID: NS:ndis._NDIS_CO_CLIENT_OPTIONAL_HANDLERS
title: "_NDIS_CO_CLIENT_OPTIONAL_HANDLERS"
author: windows-driver-content
description: The NDIS_CO_CLIENT_OPTIONAL_HANDLERS structure specifies entry points for CoNDIS client ProtocolXxx functions for the protocol driver that passes this structure to the NdisSetOptionalHandlers function.
old-location: netvista\ndis_co_client_optional_handlers.htm
old-project: netvista
ms.assetid: 1f2285bb-be70-4496-905d-89106bf3712a
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PNDIS_CO_CLIENT_OPTIONAL_HANDLERS, NDIS_CO_CLIENT_OPTIONAL_HANDLERS, NDIS_CO_CLIENT_OPTIONAL_HANDLERS structure [Network Drivers Starting with Windows Vista], PNDIS_CO_CLIENT_OPTIONAL_HANDLERS, PNDIS_CO_CLIENT_OPTIONAL_HANDLERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_CO_CLIENT_OPTIONAL_HANDLERS, condis_structures_ref_63c453a1-6ad8-4d31-93ff-340dba8433db.xml, ndis/NDIS_CO_CLIENT_OPTIONAL_HANDLERS, ndis/PNDIS_CO_CLIENT_OPTIONAL_HANDLERS, netvista.ndis_co_client_optional_handlers"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NDIS_CO_CLIENT_OPTIONAL_HANDLERS
product: Windows
targetos: Windows
req.typenames: NDIS_CO_CLIENT_OPTIONAL_HANDLERS, *PNDIS_CO_CLIENT_OPTIONAL_HANDLERS
---

# _NDIS_CO_CLIENT_OPTIONAL_HANDLERS structure


## -description


The NDIS_CO_CLIENT_OPTIONAL_HANDLERS structure specifies entry points for CoNDIS client 
  <i>ProtocolXxx</i> functions for the protocol driver that passes this structure to the 
  <a href="https://msdn.microsoft.com/97649f4f-942a-47fc-a541-6f160c8b4eb4">
  NdisSetOptionalHandlers</a> function.


## -struct-fields




### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     protocol driver CoNDIS characteristics structure (NDIS_CO_CLIENT_OPTIONAL_HANDLERS). The driver sets the
     
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_CO_CLIENT_OPTIONAL_HANDLERS, the 
     <b>Revision</b> member to NDIS_CO_CLIENT_OPTIONAL_HANDLERS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_CO_CLIENT_OPTIONAL_HANDLERS_REVISION_1.


### -field Reserved

Reserved for NDIS.


### -field ClCreateVcHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/b086dd24-74f5-474a-8684-09bf92ac731b">ProtocolCoCreateVc</a> function.


### -field ClDeleteVcHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/d761270f-bf77-441e-834c-9ac7fb3d350f">ProtocolCoDeleteVc</a> function.


### -field ClOidRequestHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/8247396f-8781-45da-aba1-a31a2a26a46f">
     ProtocolCoOidRequest</a> function.


### -field ClOidRequestCompleteHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/16883c64-3cc6-4f50-8be7-7c58c422a717">
     ProtocolCoOidRequestComplete</a> function.


### -field ClOpenAfCompleteHandlerEx

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/03ddbbfd-8fe8-44b6-8d3e-12a7bf6f8f6b">
     ProtocolClOpenAfCompleteEx</a> function.


### -field ClCloseAfCompleteHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/7597e124-34e4-4326-98b3-c65dbe90ae6f">
     ProtocolClCloseAfComplete</a> function.


### -field ClRegisterSapCompleteHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/b0a2a224-3353-4f20-b14f-ed5d633a6ead">
     ProtocolClRegisterSapComplete</a> function. A client uses this function to accept incoming calls from
     remote machines.


### -field ClDeregisterSapCompleteHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/93f8f74a-8ad4-42ea-83cf-ddfcd7f55ce6">
     ProtocolClDeregisterSapComplete</a> function.


### -field ClMakeCallCompleteHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/6bb69f78-8dab-46a7-84fb-7bc17e894535">
     ProtocolClMakeCallComplete</a> function. A client uses this function to make outgoing calls to remote
     machines.


### -field ClModifyCallQoSCompleteHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/0d925862-49af-4579-b877-c9a033e73be0">
     ProtocolClModifyCallQoSComplete</a> function. A client uses this function to dynamically make changes
     in the quality of service (QoS) on an established virtual connection (VC) or to negotiate with the call
     manager to establish the QoS when the client sets up an incoming call.


### -field ClCloseCallCompleteHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/a7ba1ab2-04c9-45b5-a184-e1ad1448561a">
     ProtocolClCloseCallComplete</a> function.


### -field ClAddPartyCompleteHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/ea3ebbe9-fd94-44b8-8801-639d099c5158">
     ProtocolClAddPartyComplete</a> function. A client uses this function to establish point-to-multipoint
     VCs for outgoing calls to remote machines.


### -field ClDropPartyCompleteHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/c916f379-393c-41d7-ab30-2f3181c3ada6">
     ProtocolClDropPartyComplete</a> function.


### -field ClIncomingCallHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/8a5922ac-b22b-444e-9ea0-3bb56e71ef33">
     ProtocolClIncomingCall</a> function. A client uses this function to accept incoming calls from remote
     machines.


### -field ClIncomingCallQoSChangeHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/ca9953f4-35db-4acb-b0ea-887156b4f6ee">
     ProtocolClIncomingCallQoSChange</a> function. A client uses this function to accept incoming calls
     from remote machines on which the sending client can dynamically change the QoS.


### -field ClIncomingCloseCallHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/01c7d887-eb54-47c3-98f0-bc567b60fb4b">
     ProtocolClIncomingCloseCall</a> function.


### -field ClIncomingDropPartyHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/3815ca4b-f4bc-4de9-a28a-5d3ee20bcdd8">
     ProtocolClIncomingDropParty</a> function.


### -field ClCallConnectedHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/675b2066-6a65-47cf-bde7-3c843f97c960">
     ProtocolClCallConnected</a> function. A client uses this function to accept incoming calls from remote
     machines.


### -field ClNotifyCloseAfHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/0f595daa-9822-4ca6-8f25-e6f82030d4ea">
     ProtocolClNotifyCloseAf</a> function.


## -remarks



To specify entry points as a CoNDIS client, a protocol driver initializes an
    NDIS_CO_CLIENT_OPTIONAL_HANDLERS structure and passes it to the 
    <a href="https://msdn.microsoft.com/97649f4f-942a-47fc-a541-6f160c8b4eb4">
    NdisSetOptionalHandlers</a> function.

The client calls 
    <b>NdisSetOptionalHandlers</b> from the 
    <a href="https://msdn.microsoft.com/342e23ad-d38b-4100-949a-220b8fbdcf6e">ProtocolSetOptions</a> function. The
    client must set every 
    <b>Cl</b><i>Xxx</i> member in the NDIS_CO_CLIENT_OPTIONAL_HANDLERS structure to a caller-supplied 
    <i>ProtocolXxx</i> function, even if the call manager does not support incoming calls, outgoing calls, or
    point-to-multipoint connections. For whatever subset of connection-oriented functionality that a client
    does not support, its placeholder 
    <i>ProtocolXxx</i> functions should return NDIS_STATUS_NOT_SUPPORTED.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a>



<a href="https://msdn.microsoft.com/ea3ebbe9-fd94-44b8-8801-639d099c5158">ProtocolClAddPartyComplete</a>



<a href="https://msdn.microsoft.com/675b2066-6a65-47cf-bde7-3c843f97c960">ProtocolClCallConnected</a>



<a href="https://msdn.microsoft.com/7597e124-34e4-4326-98b3-c65dbe90ae6f">ProtocolClCloseAfComplete</a>



<a href="https://msdn.microsoft.com/a7ba1ab2-04c9-45b5-a184-e1ad1448561a">ProtocolClCloseCallComplete</a>



<a href="https://msdn.microsoft.com/93f8f74a-8ad4-42ea-83cf-ddfcd7f55ce6">
   ProtocolClDeregisterSapComplete</a>



<a href="https://msdn.microsoft.com/c916f379-393c-41d7-ab30-2f3181c3ada6">ProtocolClDropPartyComplete</a>



<a href="https://msdn.microsoft.com/8a5922ac-b22b-444e-9ea0-3bb56e71ef33">ProtocolClIncomingCall</a>



<a href="https://msdn.microsoft.com/ca9953f4-35db-4acb-b0ea-887156b4f6ee">
   ProtocolClIncomingCallQoSChange</a>



<a href="https://msdn.microsoft.com/01c7d887-eb54-47c3-98f0-bc567b60fb4b">ProtocolClIncomingCloseCall</a>



<a href="https://msdn.microsoft.com/3815ca4b-f4bc-4de9-a28a-5d3ee20bcdd8">ProtocolClIncomingDropParty</a>



<a href="https://msdn.microsoft.com/6bb69f78-8dab-46a7-84fb-7bc17e894535">ProtocolClMakeCallComplete</a>



<a href="https://msdn.microsoft.com/0d925862-49af-4579-b877-c9a033e73be0">
   ProtocolClModifyCallQoSComplete</a>



<a href="https://msdn.microsoft.com/03ddbbfd-8fe8-44b6-8d3e-12a7bf6f8f6b">ProtocolClOpenAfCompleteEx</a>



<a href="https://msdn.microsoft.com/b0a2a224-3353-4f20-b14f-ed5d633a6ead">
   ProtocolClRegisterSapComplete</a>



<a href="https://msdn.microsoft.com/272d99da-ef08-4ebd-90e7-74e99410b3f5">ProtocolCoAfRegisterNotify</a>



<a href="https://msdn.microsoft.com/b086dd24-74f5-474a-8684-09bf92ac731b">ProtocolCoCreateVc</a>



<a href="https://msdn.microsoft.com/d761270f-bf77-441e-834c-9ac7fb3d350f">ProtocolCoDeleteVc</a>



<a href="https://msdn.microsoft.com/8247396f-8781-45da-aba1-a31a2a26a46f">ProtocolCoOidRequest</a>



<a href="https://msdn.microsoft.com/16883c64-3cc6-4f50-8be7-7c58c422a717">
   ProtocolCoOidRequestComplete</a>



<a href="https://msdn.microsoft.com/342e23ad-d38b-4100-949a-220b8fbdcf6e">ProtocolSetOptions</a>
 

 

