---
UID: NS:ndis._NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS
title: "_NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS"
author: windows-driver-content
description: The NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS structure specifies CoNDIS call manager ProtocolXxx functions for the driver that passes this structure to the NdisSetOptionalHandlers function.
old-location: netvista\ndis_co_call_manager_optional_handlers.htm
old-project: netvista
ms.assetid: 12d541e1-04dd-4512-827e-d27f16260fe3
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndis/NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS, PNDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS, *PNDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS, condis_structures_ref_82f5169a-d1fb-4555-a764-0d78dd48e8a4.xml, _NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS, NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS, NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS structure [Network Drivers Starting with Windows Vista], PNDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS structure pointer [Network Drivers Starting with Windows Vista], ndis/PNDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS, netvista.ndis_co_call_manager_optional_handlers
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
req.irql: See Remarks section
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS
product: Windows
targetos: Windows
req.typenames: "*PNDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS, NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS"
---

# _NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS structure


## -description


The NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS structure specifies CoNDIS call manager 
  <i>ProtocolXxx</i> functions for the driver that passes this structure to the 
  <a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">
  NdisSetOptionalHandlers</a> function.


## -syntax


````
typedef struct _NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS {
  NDIS_OBJECT_HEADER                  Header;
  ULONG                               Reserved;
  CO_CREATE_VC_HANDLER                CmCreateVcHandler;
  CO_DELETE_VC_HANDLER                CmDeleteVcHandler;
  CM_OPEN_AF_HANDLER                  CmOpenAfHandler;
  CM_CLOSE_AF_HANDLER                 CmCloseAfHandler;
  CM_REG_SAP_HANDLER                  CmRegisterSapHandler;
  CM_DEREG_SAP_HANDLER                CmDeregisterSapHandler;
  CM_MAKE_CALL_HANDLER                CmMakeCallHandler;
  CM_CLOSE_CALL_HANDLER               CmCloseCallHandler;
  CM_INCOMING_CALL_COMPLETE_HANDLER   CmIncomingCallCompleteHandler;
  CM_ADD_PARTY_HANDLER                CmAddPartyHandler;
  CM_DROP_PARTY_HANDLER               CmDropPartyHandler;
  CM_ACTIVATE_VC_COMPLETE_HANDLER     CmActivateVcCompleteHandler;
  CM_DEACTIVATE_VC_COMPLETE_HANDLER   CmDeactivateVcCompleteHandler;
  CM_MODIFY_CALL_QOS_HANDLER          CmModifyCallQoSHandler;
  CO_OID_REQUEST_HANDLER              CmOidRequestHandler;
  CO_OID_REQUEST_COMPLETE_HANDLER     CmOidRequestCompleteHandler;
  CM_NOTIFY_CLOSE_AF_COMPLETE_HANDLER CmNotifyCloseAfCompleteHandler;
} NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS, *PNDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     call manager CoNDIS characteristics structure (NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS). Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_CO_CALL_MANAGER_OPTIONAL_HANDLERS, the 
     <b>Revision</b> member to NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_CO_CALL_MANAGER_OPTIONAL_HANDLERS_REVISION_1.


### -field Reserved

Reserved for NDIS.


### -field CmCreateVcHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a> function.


### -field CmDeleteVcHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_co_delete_vc.md">ProtocolCoDeleteVc</a> function.


### -field CmOpenAfHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a> function.


### -field CmCloseAfHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_cm_close_af.md">ProtocolCmCloseAf</a> function.


### -field CmRegisterSapHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_cm_reg_sap.md">
     ProtocolCmRegisterSap</a> function.


### -field CmDeregisterSapHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_cm_deregister_sap.md">
     ProtocolCmDeregisterSap</a> function.


### -field CmMakeCallHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_cm_make_call.md">ProtocolCmMakeCall</a> function.


### -field CmCloseCallHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_cm_close_call.md">
     ProtocolCmCloseCall</a> function.


### -field CmIncomingCallCompleteHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_cm_incoming_call_complete.md">
     ProtocolCmIncomingCallComplete</a> function.


### -field CmAddPartyHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_cm_add_party.md">ProtocolCmAddParty</a> function.


### -field CmDropPartyHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_cm_drop_party.md">
     ProtocolCmDropParty</a> function.


### -field CmActivateVcCompleteHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_cm_activate_vc_complete.md">
     ProtocolCmActivateVcComplete</a> function.


### -field CmDeactivateVcCompleteHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_cm_deactivate_vc_complete.md">
     ProtocolCmDeactivateVcComplete</a> function.


### -field CmModifyCallQoSHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_cm_modify_qos_call.md">
     ProtocolCmModifyCallQoS</a> function.


### -field CmOidRequestHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_co_oid_request.md">
     ProtocolCoOidRequest</a> function.


### -field CmOidRequestCompleteHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_co_oid_request_complete.md">
     ProtocolCoOidRequestComplete</a> function.


### -field CmNotifyCloseAfCompleteHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_cm_notify_close_af_complete.md">
     ProtocolCmNotifyCloseAfComplete</a> function.


## -remarks



To specify entry points as a CoNDIS call manager, a protocol driver or miniport call manager (MCM)
    initializes an NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS structure and passes it to the 
    <a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">
    NdisSetOptionalHandlers</a> function.

<h3><a id="Stand-alone_Call_Manager_Constraints"></a><a id="stand-alone_call_manager_constraints"></a><a id="STAND-ALONE_CALL_MANAGER_CONSTRAINTS"></a>Stand-alone Call Manager Constraints</h3>
A stand-alone call manager calls 
     <b>NdisSetOptionalHandlers</b> from the 
     <a href="..\ndis\nc-ndis-set_options.md">ProtocolSetOptions</a> function. The
     call manager must set every entry point in the NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS structure to a
     driver-supplied 
     <i>ProtocolXxx</i> function when it calls 
     <a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a>, even if
     the call manager does not support incoming calls, outgoing calls, or point-to-multipoint connections.
     For whatever subset of connection-oriented functionality that such a call manager does not support, its
     placeholder 
     <i>ProtocolXxx</i> functions should simply return NDIS_STATUS_NOT_SUPPORTED.

After a stand-alone call manager calls the 
     <a href="..\ndis\nf-ndis-ndiscmregisteraddressfamilyex.md">
     NdisCmRegisterAddressFamilyEx</a> function successfully, NDIS ignores any entry point that the call
     manager previously specified for the 
     <a href="..\ndis\nc-ndis-protocol_oid_request_complete.md">
     ProtocolOidRequestComplete</a> function of the 
     <a href="..\ndis\ns-ndis-_ndis_protocol_driver_characteristics.md">
     NDIS_PROTOCOL_DRIVER_CHARACTERISTICS</a> structure that it passed to the 
     <a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">
     NdisRegisterProtocolDriver</a> function.

<h3><a id="MCM_Constraints"></a><a id="mcm_constraints"></a><a id="MCM_CONSTRAINTS"></a>MCM Constraints</h3>
An MCM calls the 
     <a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a> function
     from the 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">MiniportSetOptions</a> function. The
     MCM must set every 
     <b>Cm</b><i>Xxx</i> member in the NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS structure to a MCM-supplied 
     <i>ProtocolXxx</i> function even if the MCM does not support incoming calls, outgoing calls, or
     point-to-multipoint connections. For whatever subset of connection-oriented functionality that such an
     MCM driver does not support, its 
     <i>ProtocolXxx</i> functions should simply return NDIS_STATUS_NOT_SUPPORTED. For example, NDIS never
     calls an MCM driver's registered 
     <a href="..\ndis\nc-ndis-protocol_cm_activate_vc_complete.md">
     ProtocolCmActivateVcComplete</a> or 
     <a href="..\ndis\nc-ndis-protocol_cm_deactivate_vc_complete.md">
     ProtocolCmDeactivateVcComplete</a> function, so these functions can return NDIS_STATUS_NOT_SUPPORTED
     but must have entry points in the NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS structure.

An MCM driver must specify entry points for the 
     <a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a> and 
     <a href="..\ndis\nc-ndis-protocol_co_delete_vc.md">ProtocolCoDeleteVc</a> functions. If
     the MCM previously registered a 
     <a href="..\ndis\nc-ndis-miniport_co_create_vc.md">MiniportCoCreateVc</a> or 
     <a href="..\ndis\nc-ndis-miniport_co_delete_vc.md">MiniportCoDeleteVc</a> function. NDIS
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
     <a href="..\ndis\nc-ndis-miniport_co_oid_request.md">MiniportCoOidRequest</a> function.
     The driver must provide a separate entry point for a 
     <a href="..\ndis\nc-ndis-protocol_co_oid_request.md">ProtocolCoOidRequest</a> function. An
     MCM driver must have a 
     <i>ProtocolCoOidRequest</i> function to handle call manager requests from CoNDIS clients and must have a 
     <a href="..\ndis\nc-ndis-protocol_co_oid_request_complete.md">
     ProtocolCoOidRequestComplete</a> function.




## -see-also

<a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a>



<a href="..\ndis\nc-ndis-protocol_cm_deregister_sap.md">ProtocolCmDeregisterSap</a>



<a href="..\ndis\nc-ndis-protocol_cm_add_party.md">ProtocolCmAddParty</a>



<a href="..\ndis\nc-ndis-protocol_cm_make_call.md">ProtocolCmMakeCall</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">MiniportSetOptions</a>



<a href="..\ndis\nc-ndis-protocol_oid_request_complete.md">ProtocolOidRequestComplete</a>



<a href="..\ndis\nc-ndis-protocol_cm_close_af.md">ProtocolCmCloseAf</a>



<a href="..\ndis\nc-ndis-miniport_co_create_vc.md">MiniportCoCreateVc</a>



<a href="..\ndis\nc-ndis-protocol_cm_drop_party.md">ProtocolCmDropParty</a>



<a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">NdisRegisterProtocolDriver</a>



<a href="..\ndis\nc-ndis-protocol_cm_deactivate_vc_complete.md">
   ProtocolCmDeactivateVcComplete</a>



<a href="..\ndis\nc-ndis-miniport_co_oid_request.md">MiniportCoOidRequest</a>



<a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a>



<a href="..\ndis\nc-ndis-protocol_cm_modify_qos_call.md">ProtocolCmModifyCallQoS</a>



<a href="..\ndis\ns-ndis-_ndis_protocol_driver_characteristics.md">
   NDIS_PROTOCOL_DRIVER_CHARACTERISTICS</a>



<a href="..\ndis\nc-ndis-protocol_cm_reg_sap.md">ProtocolCmRegisterSap</a>



<a href="..\ndis\nc-ndis-protocol_cm_incoming_call_complete.md">
   ProtocolCmIncomingCallComplete</a>



<a href="..\ndis\nf-ndis-ndiscmregisteraddressfamilyex.md">
   NdisCmRegisterAddressFamilyEx</a>



<a href="..\ndis\nc-ndis-protocol_cm_activate_vc_complete.md">
   ProtocolCmActivateVcComplete</a>



<a href="..\ndis\nc-ndis-miniport_co_delete_vc.md">MiniportCoDeleteVc</a>



<a href="..\ndis\nc-ndis-protocol_cm_close_call.md">ProtocolCmCloseCall</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ndis\nc-ndis-set_options.md">ProtocolSetOptions</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

