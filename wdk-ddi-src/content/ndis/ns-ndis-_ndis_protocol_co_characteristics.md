---
UID: NS:ndis._NDIS_PROTOCOL_CO_CHARACTERISTICS
title: "_NDIS_PROTOCOL_CO_CHARACTERISTICS"
author: windows-driver-content
description: The NDIS_PROTOCOL_CO_CHARACTERISTICS structure specifies CoNDIS entry points for CoNDIS protocol drivers.
old-location: netvista\ndis_protocol_co_characteristics.htm
tech.root: netvista
ms.assetid: 855e3231-502c-4c6f-99f9-7ad85354ccd5
ms.date: 05/02/2018
ms.keywords: "*PNDIS_PROTOCOL_CO_CHARACTERISTICS, NDIS_PROTOCOL_CO_CHARACTERISTICS, NDIS_PROTOCOL_CO_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_PROTOCOL_CO_CHARACTERISTICS, PNDIS_PROTOCOL_CO_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PROTOCOL_CO_CHARACTERISTICS, condis_structures_ref_a4228b74-0f76-4800-ad95-e7ef3d92df42.xml, ndis/NDIS_PROTOCOL_CO_CHARACTERISTICS, ndis/PNDIS_PROTOCOL_CO_CHARACTERISTICS, netvista.ndis_protocol_co_characteristics"
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
-	NDIS_PROTOCOL_CO_CHARACTERISTICS
product:
- Windows
targetos: Windows
req.typenames: NDIS_PROTOCOL_CO_CHARACTERISTICS, *PNDIS_PROTOCOL_CO_CHARACTERISTICS
---

# _NDIS_PROTOCOL_CO_CHARACTERISTICS structure


## -description


The NDIS_PROTOCOL_CO_CHARACTERISTICS structure specifies CoNDIS entry points for CoNDIS protocol
  drivers.


## -struct-fields




### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     protocol driver CoNDIS characteristics structure (NDIS_PROTOCOL_CO_CHARACTERISTICS). The driver sets the     
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_CO_PROTOCOL_CHARACTERISTICS, the 
     <b>Revision</b> member to NDIS_PROTOCOL_CO_CHARACTERISTICS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_PROTOCOL_CO_CHARACTERISTICS_REVISION_1.


### -field Flags

Reserved for NDIS.


### -field CoStatusHandlerEx

The entry point of the driver's 
     <a href="https://msdn.microsoft.com/1416ad56-548c-4f12-9922-9ab9a7e4fd3a">ProtocolCoStatusEx</a> function.


### -field CoAfRegisterNotifyHandler

The entry point of the driver's 
     <a href="https://msdn.microsoft.com/272d99da-ef08-4ebd-90e7-74e99410b3f5">
     ProtocolCoAfRegisterNotify</a> function.


### -field CoReceiveNetBufferListsHandler

The entry point of the driver's 
     <a href="https://msdn.microsoft.com/1755804c-d82f-465d-862f-8a2340516f8e">
     ProtocolCoReceiveNetBufferLists</a> function.


### -field CoSendNetBufferListsCompleteHandler

The entry point of the driver's 
     <a href="https://msdn.microsoft.com/fb4b00c0-0b14-48dd-a6f2-aae659c6bb28">
     ProtocolCoSendNetBufferListsComplete</a> function.


## -remarks



To specify entry points for CoNDIS, a protocol driver initializes an NDIS_PROTOCOL_CO_CHARACTERISTICS
    structure and passes it to the 
    <a href="https://msdn.microsoft.com/97649f4f-942a-47fc-a541-6f160c8b4eb4">
    NdisSetOptionalHandlers</a> function.

The protocol driver calls 
    <b>NdisSetOptionalHandlers</b> from the 
    <a href="https://msdn.microsoft.com/342e23ad-d38b-4100-949a-220b8fbdcf6e">ProtocolSetOptions</a> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a>



<a href="https://msdn.microsoft.com/272d99da-ef08-4ebd-90e7-74e99410b3f5">ProtocolCoAfRegisterNotify</a>



<a href="https://msdn.microsoft.com/1755804c-d82f-465d-862f-8a2340516f8e">
   ProtocolCoReceiveNetBufferLists</a>



<a href="https://msdn.microsoft.com/fb4b00c0-0b14-48dd-a6f2-aae659c6bb28">
   ProtocolCoSendNetBufferListsComplete</a>



<a href="https://msdn.microsoft.com/1416ad56-548c-4f12-9922-9ab9a7e4fd3a">ProtocolCoStatusEx</a>



<a href="https://msdn.microsoft.com/342e23ad-d38b-4100-949a-220b8fbdcf6e">ProtocolSetOptions</a>
 

 

