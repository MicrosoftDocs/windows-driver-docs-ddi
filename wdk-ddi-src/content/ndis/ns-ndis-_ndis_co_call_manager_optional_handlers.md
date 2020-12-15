---
UID: NS:ndis._NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS
title: _NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS (ndis.h)
description: The NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS structure specifies CoNDIS call manager ProtocolXxx functions for the driver that passes this structure to the NdisSetOptionalHandlers function.
old-location: netvista\ndis_co_call_manager_optional_handlers.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS structure"]
ms.keywords: "*PNDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS, NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS, NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS structure [Network Drivers Starting with Windows Vista], PNDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS, PNDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS, condis_structures_ref_82f5169a-d1fb-4555-a764-0d78dd48e8a4.xml, ndis/NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS, ndis/PNDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS, netvista.ndis_co_call_manager_optional_handlers"
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
targetos: Windows
req.typenames: NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS, *PNDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS
f1_keywords:
 - _NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS
 - ndis/_NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS
 - PNDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS
 - ndis/PNDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS
 - NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS
 - ndis/NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS
---

# _NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS structure


## -description

The NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS structure specifies CoNDIS call manager 
  <i>ProtocolXxx</i> functions for the driver that passes this structure to the 
  <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetoptionalhandlers">
  NdisSetOptionalHandlers</a> function.

## -struct-fields

### -field Header

The 
     <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     call manager CoNDIS characteristics structure (NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS). Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_CO_CALL_MANAGER_OPTIONAL_HANDLERS, the 
     <b>Revision</b> member to NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_CO_CALL_MANAGER_OPTIONAL_HANDLERS_REVISION_1.

### -field Reserved

Reserved for NDIS.

### -field CmCreateVcHandler

The entry point of the caller's 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a> function.

### -field CmDeleteVcHandler

The entry point of the caller's 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_delete_vc">ProtocolCoDeleteVc</a> function.

### -field CmOpenAfHandler

The entry point of the caller's 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_open_af">ProtocolCmOpenAf</a> function.

### -field CmCloseAfHandler

The entry point of the caller's 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_close_af">ProtocolCmCloseAf</a> function.

### -field CmRegisterSapHandler

The entry point of the caller's 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_reg_sap">
     ProtocolCmRegisterSap</a> function.

### -field CmDeregisterSapHandler

The entry point of the caller's 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_deregister_sap">
     ProtocolCmDeregisterSap</a> function.

### -field CmMakeCallHandler

The entry point of the caller's 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_make_call">ProtocolCmMakeCall</a> function.

### -field CmCloseCallHandler

The entry point of the caller's 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_close_call">
     ProtocolCmCloseCall</a> function.

### -field CmIncomingCallCompleteHandler

The entry point of the caller's 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_incoming_call_complete">
     ProtocolCmIncomingCallComplete</a> function.

### -field CmAddPartyHandler

The entry point of the caller's 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_add_party">ProtocolCmAddParty</a> function.

### -field CmDropPartyHandler

The entry point of the caller's 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_drop_party">
     ProtocolCmDropParty</a> function.

### -field CmActivateVcCompleteHandler

The entry point of the caller's 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_activate_vc_complete">
     ProtocolCmActivateVcComplete</a> function.

### -field CmDeactivateVcCompleteHandler

The entry point of the caller's 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_deactivate_vc_complete">
     ProtocolCmDeactivateVcComplete</a> function.

### -field CmModifyCallQoSHandler

The entry point of the caller's 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_modify_qos_call">
     ProtocolCmModifyCallQoS</a> function.

### -field CmOidRequestHandler

The entry point of the caller's 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_oid_request">
     ProtocolCoOidRequest</a> function.

### -field CmOidRequestCompleteHandler

The entry point of the caller's 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_oid_request_complete">
     ProtocolCoOidRequestComplete</a> function.

### -field CmNotifyCloseAfCompleteHandler

The entry point of the caller's 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_notify_close_af_complete">
     ProtocolCmNotifyCloseAfComplete</a> function.

## -remarks

To specify entry points as a CoNDIS call manager, a protocol driver or miniport call manager (MCM)
    initializes an NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS structure and passes it to the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetoptionalhandlers">
    NdisSetOptionalHandlers</a> function.

<h3><a id="Stand-alone_Call_Manager_Constraints"></a><a id="stand-alone_call_manager_constraints"></a><a id="STAND-ALONE_CALL_MANAGER_CONSTRAINTS"></a>Stand-alone Call Manager Constraints</h3>
A stand-alone call manager calls 
     <b>NdisSetOptionalHandlers</b> from the 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-set_options">ProtocolSetOptions</a> function. The
     call manager must set every entry point in the NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS structure to a
     driver-supplied 
     <i>ProtocolXxx</i> function when it calls 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetoptionalhandlers">NdisSetOptionalHandlers</a>, even if
     the call manager does not support incoming calls, outgoing calls, or point-to-multipoint connections.
     For whatever subset of connection-oriented functionality that such a call manager does not support, its
     placeholder 
     <i>ProtocolXxx</i> functions should simply return NDIS_STATUS_NOT_SUPPORTED.

After a stand-alone call manager calls the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmregisteraddressfamilyex">
     NdisCmRegisterAddressFamilyEx</a> function successfully, NDIS ignores any entry point that the call
     manager previously specified for the 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_oid_request_complete">
     ProtocolOidRequestComplete</a> function of the 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_protocol_driver_characteristics">
     NDIS_PROTOCOL_DRIVER_CHARACTERISTICS</a> structure that it passed to the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterprotocoldriver">
     NdisRegisterProtocolDriver</a> function.

<h3><a id="MCM_Constraints"></a><a id="mcm_constraints"></a><a id="MCM_CONSTRAINTS"></a>MCM Constraints</h3>
An MCM calls the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetoptionalhandlers">NdisSetOptionalHandlers</a> function
     from the 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-set_options">MiniportSetOptions</a> function. The
     MCM must set every 
     <b>Cm</b><i>Xxx</i> member in the NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS structure to a MCM-supplied 
     <i>ProtocolXxx</i> function even if the MCM does not support incoming calls, outgoing calls, or
     point-to-multipoint connections. For whatever subset of connection-oriented functionality that such an
     MCM driver does not support, its 
     <i>ProtocolXxx</i> functions should simply return NDIS_STATUS_NOT_SUPPORTED. For example, NDIS never
     calls an MCM driver's registered 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_activate_vc_complete">
     ProtocolCmActivateVcComplete</a> or 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_deactivate_vc_complete">
     ProtocolCmDeactivateVcComplete</a> function, so these functions can return NDIS_STATUS_NOT_SUPPORTED
     but must have entry points in the NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS structure.

An MCM driver must specify entry points for the 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a> and 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_delete_vc">ProtocolCoDeleteVc</a> functions. If
     the MCM previously registered a 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_create_vc">MiniportCoCreateVc</a> or 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_delete_vc">MiniportCoDeleteVc</a> function. NDIS
     ignores the entry points for these functions, whenever NDIS calls the MCM driver to create or delete a
     virtual connection (VC). Therefore, NDIS passes in an 
     <i>NdisAfHandle</i> value for the initial parameter to the MCM-supplied 
     <i>ProtocolCoCreateVc</i> or 
     <i>ProtocolCoDeleteVc</i> function, rather than the 
     <i>MiniportAdapterContext</i> value that it would pass to the 
     <i>MiniportCoCreateVc</i> or 
     <i>MiniportCoDeleteVc</i> function of a non-MCM miniport driver.

An MCM driver cannot set the 
     <b>CmOidRequestHandler</b> member of NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS to its 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_oid_request">MiniportCoOidRequest</a> function.
     The driver must provide a separate entry point for a 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_oid_request">ProtocolCoOidRequest</a> function. An
     MCM driver must have a 
     <i>ProtocolCoOidRequest</i> function to handle call manager requests from CoNDIS clients and must have a 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_oid_request_complete">
     ProtocolCoOidRequestComplete</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_create_vc">MiniportCoCreateVc</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_delete_vc">MiniportCoDeleteVc</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_oid_request">MiniportCoOidRequest</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-set_options">MiniportSetOptions</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_protocol_driver_characteristics">
   NDIS_PROTOCOL_DRIVER_CHARACTERISTICS</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmregisteraddressfamilyex">
   NdisCmRegisterAddressFamilyEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterprotocoldriver">NdisRegisterProtocolDriver</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetoptionalhandlers">NdisSetOptionalHandlers</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_activate_vc_complete">
   ProtocolCmActivateVcComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_add_party">ProtocolCmAddParty</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_close_af">ProtocolCmCloseAf</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_close_call">ProtocolCmCloseCall</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_deactivate_vc_complete">
   ProtocolCmDeactivateVcComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_deregister_sap">ProtocolCmDeregisterSap</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_drop_party">ProtocolCmDropParty</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_incoming_call_complete">
   ProtocolCmIncomingCallComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_make_call">ProtocolCmMakeCall</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_modify_qos_call">ProtocolCmModifyCallQoS</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_open_af">ProtocolCmOpenAf</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_reg_sap">ProtocolCmRegisterSap</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_oid_request_complete">ProtocolOidRequestComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-set_options">ProtocolSetOptions</a>
