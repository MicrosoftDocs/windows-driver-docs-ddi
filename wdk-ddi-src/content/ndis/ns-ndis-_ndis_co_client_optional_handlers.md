---
UID: NS:ndis._NDIS_CO_CLIENT_OPTIONAL_HANDLERS
title: _NDIS_CO_CLIENT_OPTIONAL_HANDLERS (ndis.h)
description: The NDIS_CO_CLIENT_OPTIONAL_HANDLERS structure specifies entry points for CoNDIS client ProtocolXxx functions for the protocol driver that passes this structure to the NdisSetOptionalHandlers function.
old-location: netvista\ndis_co_client_optional_handlers.htm
tech.root: netvista
ms.assetid: 1f2285bb-be70-4496-905d-89106bf3712a
ms.date: 05/02/2018
keywords: ["_NDIS_CO_CLIENT_OPTIONAL_HANDLERS structure"]
ms.keywords: "*PNDIS_CO_CLIENT_OPTIONAL_HANDLERS, NDIS_CO_CLIENT_OPTIONAL_HANDLERS, NDIS_CO_CLIENT_OPTIONAL_HANDLERS structure [Network Drivers Starting with Windows Vista], PNDIS_CO_CLIENT_OPTIONAL_HANDLERS, PNDIS_CO_CLIENT_OPTIONAL_HANDLERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_CO_CLIENT_OPTIONAL_HANDLERS, condis_structures_ref_63c453a1-6ad8-4d31-93ff-340dba8433db.xml, ndis/NDIS_CO_CLIENT_OPTIONAL_HANDLERS, ndis/PNDIS_CO_CLIENT_OPTIONAL_HANDLERS, netvista.ndis_co_client_optional_handlers"
f1_keywords:
 - "ndis/NDIS_CO_CLIENT_OPTIONAL_HANDLERS"
 - "NDIS_CO_CLIENT_OPTIONAL_HANDLERS"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndis.h
api_name:
- NDIS_CO_CLIENT_OPTIONAL_HANDLERS
targetos: Windows
req.typenames: NDIS_CO_CLIENT_OPTIONAL_HANDLERS, *PNDIS_CO_CLIENT_OPTIONAL_HANDLERS
---

# _NDIS_CO_CLIENT_OPTIONAL_HANDLERS structure


## -description


The NDIS_CO_CLIENT_OPTIONAL_HANDLERS structure specifies entry points for CoNDIS client 
  <i>ProtocolXxx</i> functions for the protocol driver that passes this structure to the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetoptionalhandlers">
  NdisSetOptionalHandlers</a> function.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     protocol driver CoNDIS characteristics structure (NDIS_CO_CLIENT_OPTIONAL_HANDLERS). The driver sets the    
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_CO_CLIENT_OPTIONAL_HANDLERS, the 
     <b>Revision</b> member to NDIS_CO_CLIENT_OPTIONAL_HANDLERS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_CO_CLIENT_OPTIONAL_HANDLERS_REVISION_1.


### -field Reserved

Reserved for NDIS.


### -field ClCreateVcHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a> function.


### -field ClDeleteVcHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_delete_vc">ProtocolCoDeleteVc</a> function.


### -field ClOidRequestHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_oid_request">
     ProtocolCoOidRequest</a> function.


### -field ClOidRequestCompleteHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_oid_request_complete">
     ProtocolCoOidRequestComplete</a> function.


### -field ClOpenAfCompleteHandlerEx

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_open_af_complete_ex">
     ProtocolClOpenAfCompleteEx</a> function.


### -field ClCloseAfCompleteHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_close_af_complete">
     ProtocolClCloseAfComplete</a> function.


### -field ClRegisterSapCompleteHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_register_sap_complete">
     ProtocolClRegisterSapComplete</a> function. A client uses this function to accept incoming calls from
     remote machines.


### -field ClDeregisterSapCompleteHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_deregister_sap_complete">
     ProtocolClDeregisterSapComplete</a> function.


### -field ClMakeCallCompleteHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_make_call_complete">
     ProtocolClMakeCallComplete</a> function. A client uses this function to make outgoing calls to remote
     machines.


### -field ClModifyCallQoSCompleteHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_modify_call_qos_complete">
     ProtocolClModifyCallQoSComplete</a> function. A client uses this function to dynamically make changes
     in the quality of service (QoS) on an established virtual connection (VC) or to negotiate with the call
     manager to establish the QoS when the client sets up an incoming call.


### -field ClCloseCallCompleteHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_close_call_complete">
     ProtocolClCloseCallComplete</a> function.


### -field ClAddPartyCompleteHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_add_party_complete">
     ProtocolClAddPartyComplete</a> function. A client uses this function to establish point-to-multipoint
     VCs for outgoing calls to remote machines.


### -field ClDropPartyCompleteHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_drop_party_complete">
     ProtocolClDropPartyComplete</a> function.


### -field ClIncomingCallHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_call">
     ProtocolClIncomingCall</a> function. A client uses this function to accept incoming calls from remote
     machines.


### -field ClIncomingCallQoSChangeHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_call_qos_change">
     ProtocolClIncomingCallQoSChange</a> function. A client uses this function to accept incoming calls
     from remote machines on which the sending client can dynamically change the QoS.


### -field ClIncomingCloseCallHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_close_call">
     ProtocolClIncomingCloseCall</a> function.


### -field ClIncomingDropPartyHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_drop_party">
     ProtocolClIncomingDropParty</a> function.


### -field ClCallConnectedHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_call_connected">
     ProtocolClCallConnected</a> function. A client uses this function to accept incoming calls from remote
     machines.


### -field ClNotifyCloseAfHandler

The entry point of the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_notify_close_af">
     ProtocolClNotifyCloseAf</a> function.


## -remarks



To specify entry points as a CoNDIS client, a protocol driver initializes an
    NDIS_CO_CLIENT_OPTIONAL_HANDLERS structure and passes it to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetoptionalhandlers">
    NdisSetOptionalHandlers</a> function.

The client calls 
    <b>NdisSetOptionalHandlers</b> from the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-set_options">ProtocolSetOptions</a> function. The
    client must set every 
    <b>Cl</b><i>Xxx</i> member in the NDIS_CO_CLIENT_OPTIONAL_HANDLERS structure to a caller-supplied 
    <i>ProtocolXxx</i> function, even if the call manager does not support incoming calls, outgoing calls, or
    point-to-multipoint connections. For whatever subset of connection-oriented functionality that a client
    does not support, its placeholder 
    <i>ProtocolXxx</i> functions should return NDIS_STATUS_NOT_SUPPORTED.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetoptionalhandlers">NdisSetOptionalHandlers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_add_party_complete">ProtocolClAddPartyComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_call_connected">ProtocolClCallConnected</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_close_af_complete">ProtocolClCloseAfComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_close_call_complete">ProtocolClCloseCallComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_deregister_sap_complete">
   ProtocolClDeregisterSapComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_drop_party_complete">ProtocolClDropPartyComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_call">ProtocolClIncomingCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_call_qos_change">
   ProtocolClIncomingCallQoSChange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_close_call">ProtocolClIncomingCloseCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_drop_party">ProtocolClIncomingDropParty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_make_call_complete">ProtocolClMakeCallComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_modify_call_qos_complete">
   ProtocolClModifyCallQoSComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_open_af_complete_ex">ProtocolClOpenAfCompleteEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_register_sap_complete">
   ProtocolClRegisterSapComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_af_register_notify">ProtocolCoAfRegisterNotify</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_delete_vc">ProtocolCoDeleteVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_oid_request">ProtocolCoOidRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_oid_request_complete">
   ProtocolCoOidRequestComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-set_options">ProtocolSetOptions</a>
 

 

