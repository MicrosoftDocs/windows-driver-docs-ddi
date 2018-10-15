---
UID: NS:ndis._NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS
title: "_NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS"
author: windows-driver-content
description: The NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS structure specifies CoNDIS call manager ProtocolXxx functions for the driver that passes this structure to the NdisSetOptionalHandlers function.
old-location: netvista\ndis_co_call_manager_optional_handlers.htm
tech.root: netvista
ms.assetid: 12d541e1-04dd-4512-827e-d27f16260fe3
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: "*PNDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS, NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS, NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS structure [Network Drivers Starting with Windows Vista], PNDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS, PNDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS, condis_structures_ref_82f5169a-d1fb-4555-a764-0d78dd48e8a4.xml, ndis/NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS, ndis/PNDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS, netvista.ndis_co_call_manager_optional_handlers"
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
-	NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS, *PNDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS
---

# _NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS structure


## -description


The NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS structure specifies CoNDIS call manager 
  <i>ProtocolXxx</i> functions for the driver that passes this structure to the 
  <a href="https://msdn.microsoft.com/97649f4f-942a-47fc-a541-6f160c8b4eb4">
  NdisSetOptionalHandlers</a> function.


## -struct-fields




### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     call manager CoNDIS characteristics structure (NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS). Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_CO_CALL_MANAGER_OPTIONAL_HANDLERS, the 
     <b>Revision</b> member to NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_CO_CALL_MANAGER_OPTIONAL_HANDLERS_REVISION_1.


### -field Reserved

Reserved for NDIS.


### -field CmCreateVcHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/b086dd24-74f5-474a-8684-09bf92ac731b">ProtocolCoCreateVc</a> function.


### -field CmDeleteVcHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/d761270f-bf77-441e-834c-9ac7fb3d350f">ProtocolCoDeleteVc</a> function.


### -field CmOpenAfHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/7422c205-bc41-4121-b430-ff9e6b49dc2e">ProtocolCmOpenAf</a> function.


### -field CmCloseAfHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/a7a02813-62e4-49c5-abb6-a90f4e092b9f">ProtocolCmCloseAf</a> function.


### -field CmRegisterSapHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/3e3e7a0e-a8d2-40b2-895b-187d24867080">
     ProtocolCmRegisterSap</a> function.


### -field CmDeregisterSapHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/738c426e-aa4f-4f59-b955-fbf67071303f">
     ProtocolCmDeregisterSap</a> function.


### -field CmMakeCallHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/ede0a18a-cd3b-4fbb-a16b-e7493940d633">ProtocolCmMakeCall</a> function.


### -field CmCloseCallHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/b5307e1b-3905-4e43-a0b0-0068ba18ef0d">
     ProtocolCmCloseCall</a> function.


### -field CmIncomingCallCompleteHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/353e929b-17c8-47e8-82fd-b646e93a5b9a">
     ProtocolCmIncomingCallComplete</a> function.


### -field CmAddPartyHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/06aa5ff6-974c-43dd-8395-bc1a1a8421d5">ProtocolCmAddParty</a> function.


### -field CmDropPartyHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/be0fce3e-7308-42fa-b63a-4d5cfec7ea6c">
     ProtocolCmDropParty</a> function.


### -field CmActivateVcCompleteHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/6ec9e73e-8abd-4d27-b598-6176f2125348">
     ProtocolCmActivateVcComplete</a> function.


### -field CmDeactivateVcCompleteHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/44ee0e3c-aee9-4e24-9e54-c57248b568b6">
     ProtocolCmDeactivateVcComplete</a> function.


### -field CmModifyCallQoSHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/24523677-9f5a-4109-8484-95883a4d1bbf">
     ProtocolCmModifyCallQoS</a> function.


### -field CmOidRequestHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/8247396f-8781-45da-aba1-a31a2a26a46f">
     ProtocolCoOidRequest</a> function.


### -field CmOidRequestCompleteHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/16883c64-3cc6-4f50-8be7-7c58c422a717">
     ProtocolCoOidRequestComplete</a> function.


### -field CmNotifyCloseAfCompleteHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/c5bdedee-dacd-4f4d-a3d1-f1cb71a68001">
     ProtocolCmNotifyCloseAfComplete</a> function.


## -remarks



To specify entry points as a CoNDIS call manager, a protocol driver or miniport call manager (MCM)
    initializes an NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS structure and passes it to the 
    <a href="https://msdn.microsoft.com/97649f4f-942a-47fc-a541-6f160c8b4eb4">
    NdisSetOptionalHandlers</a> function.

<h3><a id="Stand-alone_Call_Manager_Constraints"></a><a id="stand-alone_call_manager_constraints"></a><a id="STAND-ALONE_CALL_MANAGER_CONSTRAINTS"></a>Stand-alone Call Manager Constraints</h3>
A stand-alone call manager calls 
     <b>NdisSetOptionalHandlers</b> from the 
     <a href="https://msdn.microsoft.com/342e23ad-d38b-4100-949a-220b8fbdcf6e">ProtocolSetOptions</a> function. The
     call manager must set every entry point in the NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS structure to a
     driver-supplied 
     <i>ProtocolXxx</i> function when it calls 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a>, even if
     the call manager does not support incoming calls, outgoing calls, or point-to-multipoint connections.
     For whatever subset of connection-oriented functionality that such a call manager does not support, its
     placeholder 
     <i>ProtocolXxx</i> functions should simply return NDIS_STATUS_NOT_SUPPORTED.

After a stand-alone call manager calls the 
     <a href="https://msdn.microsoft.com/8890bf31-f2c7-48b0-926d-8931893ede86">
     NdisCmRegisterAddressFamilyEx</a> function successfully, NDIS ignores any entry point that the call
     manager previously specified for the 
     <a href="https://msdn.microsoft.com/2706577e-ba03-4347-9672-7303752ec0fe">
     ProtocolOidRequestComplete</a> function of the 
     <a href="https://msdn.microsoft.com/db64c160-9db6-4b23-af14-e64acdb9ef57">
     NDIS_PROTOCOL_DRIVER_CHARACTERISTICS</a> structure that it passed to the 
     <a href="https://msdn.microsoft.com/b48571eb-13a2-4541-80ac-c8d31f378d37">
     NdisRegisterProtocolDriver</a> function.

<h3><a id="MCM_Constraints"></a><a id="mcm_constraints"></a><a id="MCM_CONSTRAINTS"></a>MCM Constraints</h3>
An MCM calls the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a> function
     from the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff570269">MiniportSetOptions</a> function. The
     MCM must set every 
     <b>Cm</b><i>Xxx</i> member in the NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS structure to a MCM-supplied 
     <i>ProtocolXxx</i> function even if the MCM does not support incoming calls, outgoing calls, or
     point-to-multipoint connections. For whatever subset of connection-oriented functionality that such an
     MCM driver does not support, its 
     <i>ProtocolXxx</i> functions should simply return NDIS_STATUS_NOT_SUPPORTED. For example, NDIS never
     calls an MCM driver's registered 
     <a href="https://msdn.microsoft.com/6ec9e73e-8abd-4d27-b598-6176f2125348">
     ProtocolCmActivateVcComplete</a> or 
     <a href="https://msdn.microsoft.com/44ee0e3c-aee9-4e24-9e54-c57248b568b6">
     ProtocolCmDeactivateVcComplete</a> function, so these functions can return NDIS_STATUS_NOT_SUPPORTED
     but must have entry points in the NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS structure.

An MCM driver must specify entry points for the 
     <a href="https://msdn.microsoft.com/b086dd24-74f5-474a-8684-09bf92ac731b">ProtocolCoCreateVc</a> and 
     <a href="https://msdn.microsoft.com/d761270f-bf77-441e-834c-9ac7fb3d350f">ProtocolCoDeleteVc</a> functions. If
     the MCM previously registered a 
     <a href="https://msdn.microsoft.com/99eaba29-ce17-4e79-878e-5fdf7411e56c">MiniportCoCreateVc</a> or 
     <a href="https://msdn.microsoft.com/ed9b6ad1-059b-47d9-b1f7-10d498c5d2d4">MiniportCoDeleteVc</a> function. NDIS
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
     <a href="https://msdn.microsoft.com/903bcdc5-9d42-4067-a054-057edc95ccf7">MiniportCoOidRequest</a> function.
     The driver must provide a separate entry point for a 
     <a href="https://msdn.microsoft.com/8247396f-8781-45da-aba1-a31a2a26a46f">ProtocolCoOidRequest</a> function. An
     MCM driver must have a 
     <i>ProtocolCoOidRequest</i> function to handle call manager requests from CoNDIS clients and must have a 
     <a href="https://msdn.microsoft.com/16883c64-3cc6-4f50-8be7-7c58c422a717">
     ProtocolCoOidRequestComplete</a> function.




## -see-also




<a href="https://msdn.microsoft.com/99eaba29-ce17-4e79-878e-5fdf7411e56c">MiniportCoCreateVc</a>



<a href="https://msdn.microsoft.com/ed9b6ad1-059b-47d9-b1f7-10d498c5d2d4">MiniportCoDeleteVc</a>



<a href="https://msdn.microsoft.com/903bcdc5-9d42-4067-a054-057edc95ccf7">MiniportCoOidRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570269">MiniportSetOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/db64c160-9db6-4b23-af14-e64acdb9ef57">
   NDIS_PROTOCOL_DRIVER_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/8890bf31-f2c7-48b0-926d-8931893ede86">
   NdisCmRegisterAddressFamilyEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564520">NdisRegisterProtocolDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a>



<a href="https://msdn.microsoft.com/6ec9e73e-8abd-4d27-b598-6176f2125348">
   ProtocolCmActivateVcComplete</a>



<a href="https://msdn.microsoft.com/06aa5ff6-974c-43dd-8395-bc1a1a8421d5">ProtocolCmAddParty</a>



<a href="https://msdn.microsoft.com/a7a02813-62e4-49c5-abb6-a90f4e092b9f">ProtocolCmCloseAf</a>



<a href="https://msdn.microsoft.com/b5307e1b-3905-4e43-a0b0-0068ba18ef0d">ProtocolCmCloseCall</a>



<a href="https://msdn.microsoft.com/44ee0e3c-aee9-4e24-9e54-c57248b568b6">
   ProtocolCmDeactivateVcComplete</a>



<a href="https://msdn.microsoft.com/738c426e-aa4f-4f59-b955-fbf67071303f">ProtocolCmDeregisterSap</a>



<a href="https://msdn.microsoft.com/be0fce3e-7308-42fa-b63a-4d5cfec7ea6c">ProtocolCmDropParty</a>



<a href="https://msdn.microsoft.com/353e929b-17c8-47e8-82fd-b646e93a5b9a">
   ProtocolCmIncomingCallComplete</a>



<a href="https://msdn.microsoft.com/ede0a18a-cd3b-4fbb-a16b-e7493940d633">ProtocolCmMakeCall</a>



<a href="https://msdn.microsoft.com/24523677-9f5a-4109-8484-95883a4d1bbf">ProtocolCmModifyCallQoS</a>



<a href="https://msdn.microsoft.com/7422c205-bc41-4121-b430-ff9e6b49dc2e">ProtocolCmOpenAf</a>



<a href="https://msdn.microsoft.com/3e3e7a0e-a8d2-40b2-895b-187d24867080">ProtocolCmRegisterSap</a>



<a href="https://msdn.microsoft.com/2706577e-ba03-4347-9672-7303752ec0fe">ProtocolOidRequestComplete</a>



<a href="https://msdn.microsoft.com/342e23ad-d38b-4100-949a-220b8fbdcf6e">ProtocolSetOptions</a>
 

 

