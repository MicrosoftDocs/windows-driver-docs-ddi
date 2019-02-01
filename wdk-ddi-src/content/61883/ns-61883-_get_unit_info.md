---
UID: NS:61883._GET_UNIT_INFO
title: _GET_UNIT_INFO (61883.h)
description: This structure is used to get unit information.
old-location: ieee\get_unit_info.htm
tech.root: IEEE
ms.assetid: 2FE13A53-5B88-40B8-B129-8DD141F1B160
ms.date: 02/15/2018
ms.keywords: "*PGET_UNIT_INFO, 61883/GET_UNIT_INFO, 61883/PGET_UNIT_INFO, GET_UNIT_INFO, GET_UNIT_INFO structure [Buses], IEEE.get_unit_info, PGET_UNIT_INFO, PGET_UNIT_INFO structure pointer [Buses], _GET_UNIT_INFO"
ms.topic: struct
req.header: 61883.h
req.include-header: 
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	61883.h
api_name:
-	GET_UNIT_INFO
product:
- Windows
targetos: Windows
req.typenames: GET_UNIT_INFO, *PGET_UNIT_INFO
---

# _GET_UNIT_INFO structure


## -description


This structure is used to get unit information.The  request retrieves unit information about the device. The Plug and Play ID for a 61883 device is based on its VendorID, ModelID, and Character/Transaction Set. 


## -struct-fields




### -field nLevel

On input, the level of information to retrieve. Can be one of the following:

GET_UNIT_INFO_IDS

GET_UNIT_INFO_CAPABILITIES

GET_UNIT_INFO_ISOCH_PARAMS

GET_UNIT_BUS_GENERATION_NODE

GET_UNIT_DDI_VERSION

GET_UNIT_DIAG_LEVEL


### -field Information

In input, a pointer to information supplied by the protocol driver about the device. 

<table>
<tr>
<th>Value of nLevel</th>
<th>Action of the Protocol Driver</th>
</tr>
<tr>
<td>
GET_UNIT_INFO_IDS

</td>
<td>
The protocol driver writes device ID information to the caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff537168">GET_UNIT_IDS</a> structure at <b>Information</b>.

</td>
</tr>
<tr>
<td>
GET_UNIT_INFO_CAPABILITIES

</td>
<td>
The protocol driver writes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537166">GET_UNIT_CAPABILITIES</a> structure containing device capability information.

</td>
</tr>
<tr>
<td>
GET_UNIT_ISOCH_PARAMS

</td>
<td>
The protocol driver writes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff538921">UNIT_ISOCH_PARAMS</a> structure containing device parameters used by the device to capture and transmit isochronous packets.

</td>
</tr>
<tr>
<td>
GET_UNIT_BUS_GENERATION_NODE

</td>
<td>
The protocol driver writes current bus characteristics to the caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff537020">BUS_GENERATION_NODE</a> structure at <b>Information</b>.

</td>
</tr>
<tr>
<td>
GET_UNIT_DDI_VERSION

</td>
<td>
The protocol driver writes current 61883 DDI version to the caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff538898">UNIT_DDI_VERSION</a> structure at <b>Information</b>. 

</td>
</tr>
<tr>
<td>
GET_UNIT_DIAG_LEVEL

</td>
<td>
The protocol driver writes current diag level to the caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff538914">UNIT_DIAG_LEVEL</a> structure at <b>Information</b>.

</td>
</tr>
</table>
 


## -remarks



<b>Flags</b> in the request specifies either RETRIEVE_DEVICE_UNIT_INFO or RETRIEVE_LOCAL_UNIT_INFO. Only used when <b>nLevel</b> is set to GET_UNIT_INFO_CAPABILITIES.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>
 

 

