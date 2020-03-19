---
UID: NS:61883._GET_UNIT_IDS
title: _GET_UNIT_IDS (61883.h)
description: The GET_UNIT_CAPABILITIES structure is used in conjunction with the Av61883_GetUnitInfo request to retrieve device identifiers.
old-location: ieee\get_unit_ids.htm
tech.root: IEEE
ms.assetid: 8ffa85ee-cad6-476e-91ab-1897a6b43ca1
ms.date: 02/15/2018
keywords: ["_GET_UNIT_IDS structure"]
ms.keywords: "*PGET_UNIT_IDS, 61883/GET_UNIT_IDS, 61883/PGET_UNIT_IDS, 61883_structures_5415ce51-9c17-481b-86bd-08b8ff1595ca.xml, GET_UNIT_IDS, GET_UNIT_IDS structure [Buses], IEEE.get_unit_ids, PGET_UNIT_IDS, PGET_UNIT_IDS structure pointer [Buses], _GET_UNIT_IDS"
f1_keywords:
 - "61883/GET_UNIT_IDS"
req.header: 61883.h
req.include-header: 61883.h
req.target-type: Windows
req.target-min-winverclnt: 
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
- 61883.h
api_name:
- GET_UNIT_IDS
product:
- Windows
targetos: Windows
req.typenames: GET_UNIT_IDS, *PGET_UNIT_IDS
---

# _GET_UNIT_IDS structure


## -description


The GET_UNIT_CAPABILITIES structure is used in conjunction with the <a href="https://docs.microsoft.com/previous-versions/ff536983(v=vs.85)">Av61883_GetUnitInfo</a> request to retrieve device identifiers. 


## -struct-fields




### -field UniqueID

The unique ID for the device from the bus information block within the configuration ROM of the unit. 


### -field VendorID

The vendor ID for the device.


### -field ModelID

The model ID for the device. This value is retrieved from the root directory within the device's Configuration ROM.


### -field ulVendorLength

The length, in bytes, of the vendor text string, including the terminating UNICODE_NULL. If <b>ulVendorLength</b> is not zero in the input GET_UNIT_IDS structure, <b>VendorText</b> must point to a buffer whose size is <b>sizeof(ulVendorLength)</b>.


### -field VendorText

Points to a buffer that receives the "friendly name" for the vendor as a Unicode string terminated with a UNICODE_NULL. If <b>ulVendorLength</b> is zero in the input GET_UNIT_IDS structure, <b>VendorText</b> is <b>NULL</b>. 


### -field ulModelLength

The length, in bytes, of the model text string, including the terminating UNICODE_NULL. If <b>ulModelLength</b> is not zero in the input GET_UNIT_IDS structure, <b>ModelText</b> must point to a buffer whose size is <b>sizeof(ulModelLength)</b>. 


### -field ModelText

Points to a buffer to receive the "friendly name" for the model as a Unicode string terminated with a UNICODE_NULL. If <b>ulModelLength</b> is zero in the input GET_UNIT_IDS structure, <b>ModelText</b> is <b>NULL</b>. This value is retrieved from the root directory within the device's Configuration ROM. 


### -field UnitModelID

The model ID for the device. This value is retrieved from the unit directory within the device's Configuration ROM. 


### -field ulUnitModelLength

The length, in bytes, of the model text string, including the terminating UNICODE_NULL. If <b>ulUnitModelLength</b> is not zero in the input GET_UNIT_IDS structure, <b>UnitModelText</b> must point to a buffer whose size is <b>sizeof(ulUnitModelLength)</b>. 


### -field UnitModelText

Points to a buffer that receives the "friendly name" for the model represented as a Unicode string terminated with a UNICODE_NULL. If <b>ulUnitModelLength</b> is zero in the input GET_UNIT_IDS structure, <b>UnitModelText</b> will be <b>NULL</b>. This value is retrieved from the unit directory within the device's Configuration ROM.


## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff536983(v=vs.85)">Av61883_GetUnitInfo</a>
 

 

