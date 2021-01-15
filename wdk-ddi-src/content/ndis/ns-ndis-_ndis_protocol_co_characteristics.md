---
UID: NS:ndis._NDIS_PROTOCOL_CO_CHARACTERISTICS
title: _NDIS_PROTOCOL_CO_CHARACTERISTICS (ndis.h)
description: The NDIS_PROTOCOL_CO_CHARACTERISTICS structure specifies CoNDIS entry points for CoNDIS protocol drivers.
old-location: netvista\ndis_protocol_co_characteristics.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_PROTOCOL_CO_CHARACTERISTICS structure"]
ms.keywords: "*PNDIS_PROTOCOL_CO_CHARACTERISTICS, NDIS_PROTOCOL_CO_CHARACTERISTICS, NDIS_PROTOCOL_CO_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_PROTOCOL_CO_CHARACTERISTICS, PNDIS_PROTOCOL_CO_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PROTOCOL_CO_CHARACTERISTICS, condis_structures_ref_a4228b74-0f76-4800-ad95-e7ef3d92df42.xml, ndis/NDIS_PROTOCOL_CO_CHARACTERISTICS, ndis/PNDIS_PROTOCOL_CO_CHARACTERISTICS, netvista.ndis_protocol_co_characteristics"
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
req.typenames: NDIS_PROTOCOL_CO_CHARACTERISTICS, *PNDIS_PROTOCOL_CO_CHARACTERISTICS
f1_keywords:
 - _NDIS_PROTOCOL_CO_CHARACTERISTICS
 - ndis/_NDIS_PROTOCOL_CO_CHARACTERISTICS
 - PNDIS_PROTOCOL_CO_CHARACTERISTICS
 - ndis/PNDIS_PROTOCOL_CO_CHARACTERISTICS
 - NDIS_PROTOCOL_CO_CHARACTERISTICS
 - ndis/NDIS_PROTOCOL_CO_CHARACTERISTICS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - _NDIS_PROTOCOL_CO_CHARACTERISTICS
 - PNDIS_PROTOCOL_CO_CHARACTERISTICS
 - NDIS_PROTOCOL_CO_CHARACTERISTICS
---

# _NDIS_PROTOCOL_CO_CHARACTERISTICS structure


## -description

The NDIS_PROTOCOL_CO_CHARACTERISTICS structure specifies CoNDIS entry points for CoNDIS protocol
  drivers.

## -struct-fields

### -field Header

The 
     <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     protocol driver CoNDIS characteristics structure (NDIS_PROTOCOL_CO_CHARACTERISTICS). The driver sets the     
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_CO_PROTOCOL_CHARACTERISTICS, the 
     <b>Revision</b> member to NDIS_PROTOCOL_CO_CHARACTERISTICS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_PROTOCOL_CO_CHARACTERISTICS_REVISION_1.

### -field Flags

Reserved for NDIS.

### -field CoStatusHandlerEx

The entry point of the driver's 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_status_ex">ProtocolCoStatusEx</a> function.

### -field CoAfRegisterNotifyHandler

The entry point of the driver's 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_af_register_notify">
     ProtocolCoAfRegisterNotify</a> function.

### -field CoReceiveNetBufferListsHandler

The entry point of the driver's 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_receive_net_buffer_lists">
     ProtocolCoReceiveNetBufferLists</a> function.

### -field CoSendNetBufferListsCompleteHandler

The entry point of the driver's 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_send_net_buffer_lists_complete">
     ProtocolCoSendNetBufferListsComplete</a> function.

## -remarks

To specify entry points for CoNDIS, a protocol driver initializes an NDIS_PROTOCOL_CO_CHARACTERISTICS
    structure and passes it to the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetoptionalhandlers">
    NdisSetOptionalHandlers</a> function.

The protocol driver calls 
    <b>NdisSetOptionalHandlers</b> from the 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-set_options">ProtocolSetOptions</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetoptionalhandlers">NdisSetOptionalHandlers</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_af_register_notify">ProtocolCoAfRegisterNotify</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_receive_net_buffer_lists">
   ProtocolCoReceiveNetBufferLists</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_send_net_buffer_lists_complete">
   ProtocolCoSendNetBufferListsComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_status_ex">ProtocolCoStatusEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-set_options">ProtocolSetOptions</a>

