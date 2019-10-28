---
UID: NS:ndis._NDIS_MINIPORT_CO_CHARACTERISTICS
title: _NDIS_MINIPORT_CO_CHARACTERISTICS (ndis.h)
description: The NDIS_MINIPORT_CO_CHARACTERISTICS structure specifies the CoNDIS entry points for a CoNDIS miniport driver.
old-location: netvista\ndis_miniport_co_characteristics.htm
tech.root: netvista
ms.assetid: 9348c338-9fb4-4eee-a50f-f709748da56b
ms.date: 05/02/2018
ms.keywords: "*PNDIS_MINIPORT_CO_CHARACTERISTICS, NDIS_MINIPORT_CO_CHARACTERISTICS, NDIS_MINIPORT_CO_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_CO_CHARACTERISTICS, PNDIS_MINIPORT_CO_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_CO_CHARACTERISTICS, condis_structures_ref_148c0384-32c9-4d21-bab8-66b839ee75a6.xml, ndis/NDIS_MINIPORT_CO_CHARACTERISTICS, ndis/PNDIS_MINIPORT_CO_CHARACTERISTICS, netvista.ndis_miniport_co_characteristics"
ms.topic: struct
f1_keywords:
 - "ndis/NDIS_MINIPORT_CO_CHARACTERISTICS"
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
- NDIS_MINIPORT_CO_CHARACTERISTICS
product:
- Windows
targetos: Windows
req.typenames: NDIS_MINIPORT_CO_CHARACTERISTICS, *PNDIS_MINIPORT_CO_CHARACTERISTICS
---

# _NDIS_MINIPORT_CO_CHARACTERISTICS structure


## -description


The NDIS_MINIPORT_CO_CHARACTERISTICS structure specifies the CoNDIS entry points for a CoNDIS
  miniport driver.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     miniport driver CoNDIS characteristics structure (NDIS_MINIPORT_CO_CHARACTERISTICS). The driver sets the     
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_CO_MINIPORT_CHARACTERISTICS, the 
     <b>Revision</b> member to NDIS_MINIPORT_CO_CHARACTERISTICS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_MINIPORT_CO_CHARACTERISTICS_REVISION_1.


### -field Flags

Reserved for NDIS.


### -field CoCreateVcHandler

The entry point of the driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_create_vc">MiniportCoCreateVc</a> function. If
     this entry point is for an integrated miniport call manager (MCM) driver, this member should be <b>NULL</b>,
     because NDIS calls such a driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a> function
     instead. For more information about 
     <i>ProtocolCoCreateVc</i> in an MCM, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_co_call_manager_optional_handlers">
     NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS</a>.


### -field CoDeleteVcHandler

The entry point of the driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_delete_vc">MiniportCoDeleteVc</a> function. If
     this entry point is for an integrated miniport call manager (MCM) driver, this member should be <b>NULL</b>,
     because NDIS calls such a driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_delete_vc">ProtocolCoDeleteVc</a> function
     instead. For more information about 
     <i>ProtocolCoDeleteVc</i> in an MCM, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_co_call_manager_optional_handlers">
     NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS</a>.


### -field CoActivateVcHandler

The entry point of the driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_activate_vc">
     MiniportCoActivateVc</a> function.


### -field CoDeactivateVcHandler

The entry point of the driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_deactivate_vc">
     MiniportCoDeactivateVc</a> function.


### -field CoSendNetBufferListsHandler

The entry point of the driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_send_net_buffer_lists">
     MiniportCoSendNetBufferLists</a> function.


### -field CoOidRequestHandler

The entry point of the driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_oid_request">
     MiniportCoOidRequest</a> function.


## -remarks



To specify entry points for CoNDIS, a miniport driver initializes an NDIS_MINIPORT_CO_CHARACTERISTICS
    structure and passes it to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetoptionalhandlers">
    NdisSetOptionalHandlers</a> function.

The miniport driver calls 
    <b>NdisSetOptionalHandlers</b> from the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-set_options">MiniportSetOptions</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_activate_vc">MiniportCoActivateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_create_vc">MiniportCoCreateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_deactivate_vc">MiniportCoDeactivateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_delete_vc">MiniportCoDeleteVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_oid_request">MiniportCoOidRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_send_net_buffer_lists">
   MiniportCoSendNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-set_options">MiniportSetOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_co_call_manager_optional_handlers">
   NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetoptionalhandlers">NdisSetOptionalHandlers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_delete_vc">ProtocolCoDeleteVc</a>
 

 

