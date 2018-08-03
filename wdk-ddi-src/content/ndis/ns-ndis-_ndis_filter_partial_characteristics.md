---
UID: NS:ndis._NDIS_FILTER_PARTIAL_CHARACTERISTICS
title: "_NDIS_FILTER_PARTIAL_CHARACTERISTICS"
author: windows-driver-content
description: To specify optional entry points for a filter module, a filter driver initializes an NDIS_FILTER_PARTIAL_CHARACTERISTICS structure and passes it to the NdisSetOptionalHandlers function.
old-location: netvista\ndis_filter_partial_characteristics.htm
tech.root: netvista
ms.assetid: 4a7f365c-a252-4d8e-bddf-684b3298db5c
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: "*PNDIS_FILTER_PARTIAL_CHARACTERISTICS, NDIS_FILTER_PARTIAL_CHARACTERISTICS, NDIS_FILTER_PARTIAL_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_FILTER_PARTIAL_CHARACTERISTICS, PNDIS_FILTER_PARTIAL_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_FILTER_PARTIAL_CHARACTERISTICS, filter_structures_ref_34b4c497-9a4c-4d15-9d25-672a7580456b.xml, ndis/NDIS_FILTER_PARTIAL_CHARACTERISTICS, ndis/PNDIS_FILTER_PARTIAL_CHARACTERISTICS, netvista.ndis_filter_partial_characteristics"
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
-	NDIS_FILTER_PARTIAL_CHARACTERISTICS
product:
- Windows
targetos: Windows
req.typenames: NDIS_FILTER_PARTIAL_CHARACTERISTICS, *PNDIS_FILTER_PARTIAL_CHARACTERISTICS
---

# _NDIS_FILTER_PARTIAL_CHARACTERISTICS structure


## -description


To specify optional entry points for a filter module, a filter driver initializes an
  NDIS_FILTER_PARTIAL_CHARACTERISTICS structure and passes it to the 
  <a href="https://msdn.microsoft.com/97649f4f-942a-47fc-a541-6f160c8b4eb4">
  NdisSetOptionalHandlers</a> function.


## -struct-fields




### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     filter driver partial characteristics structure (NDIS_FILTER_PARTIAL_CHARACTERISTICS). Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_FILTER_PARTIAL_CHARACTERISTICS, the 
     <b>Revision</b> member to NDIS_FILTER_PARTIAL_CHARACTERISTICS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_FILTER_PARTIAL_CHARACTERISTICS_REVISION_1.


### -field Flags

Reserved for NDIS.


### -field SendNetBufferListsHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/1b3fc0c8-95da-47e5-8ff1-b7967f5148e7">
     FilterSendNetBufferLists</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field SendNetBufferListsCompleteHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/1a3a1e80-29f1-4f19-b3c7-9a8b189f18c4">
     FilterSendNetBufferListsComplete</a> function. To bypass this function, set this member to
     <b>NULL</b>.


### -field CancelSendNetBufferListsHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/55979b0d-61a6-43da-8fa5-11159b1a48d1">
     FilterCancelSendNetBufferLists</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field ReceiveNetBufferListsHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/6359c2a7-1208-41ea-bbf9-015c91b6e8f6">
     FilterReceiveNetBufferLists</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field ReturnNetBufferListsHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/8d7e362f-62da-4ce7-9497-1cfaff2b678e">
     FilterReturnNetBufferLists</a> function. To bypass this function, set this member to <b>NULL</b>.


## -remarks



This structure specifies optional 
    <i>FilterXxx</i> functions and other characteristics for a filter module. These characteristics override
    the default values that the driver set in the 
    <a href="https://msdn.microsoft.com/1eb2bae0-70b9-4bc0-9d93-4fc9467f9532">
    NDIS_FILTER_DRIVER_CHARACTERISTICS</a> structure that the driver passed to the 
    <a href="https://msdn.microsoft.com/14381de2-36d9-4ec8-9d4e-7af3e6d8ecf3">
    NdisFRegisterFilterDriver</a> function.




## -see-also




<a href="https://msdn.microsoft.com/55979b0d-61a6-43da-8fa5-11159b1a48d1">
   FilterCancelSendNetBufferLists</a>



<a href="https://msdn.microsoft.com/6359c2a7-1208-41ea-bbf9-015c91b6e8f6">FilterReceiveNetBufferLists</a>



<a href="https://msdn.microsoft.com/8d7e362f-62da-4ce7-9497-1cfaff2b678e">FilterReturnNetBufferLists</a>



<a href="https://msdn.microsoft.com/1b3fc0c8-95da-47e5-8ff1-b7967f5148e7">FilterSendNetBufferLists</a>



<a href="https://msdn.microsoft.com/1a3a1e80-29f1-4f19-b3c7-9a8b189f18c4">
   FilterSendNetBufferListsComplete</a>



<a href="https://msdn.microsoft.com/1eb2bae0-70b9-4bc0-9d93-4fc9467f9532">
   NDIS_FILTER_DRIVER_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562608">NdisFRegisterFilterDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a>
 

 

