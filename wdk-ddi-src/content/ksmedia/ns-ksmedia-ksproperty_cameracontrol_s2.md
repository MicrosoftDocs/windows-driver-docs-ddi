---
UID: NS:ksmedia.__unnamed_struct_116
title: KSPROPERTY_CAMERACONTROL_S2 (ksmedia.h)
description: The KSPROPERTY_CAMERACONTROL_S2 structure describes filter-based properties in the PROPSETID_VIDCAP_CAMERACONTROL property set that use two values at the same time.
old-location: stream\ksproperty_cameracontrol_s2.htm
tech.root: stream
ms.assetid: b0ea25c0-5b10-403f-8c61-7840fe062596
ms.date: 04/23/2018
ms.keywords: "*PKSPROPERTY_CAMERACONTROL_S2, KSPROPERTY_CAMERACONTROL_S2, KSPROPERTY_CAMERACONTROL_S2 structure [Streaming Media Devices], PKSPROPERTY_CAMERACONTROL_S2, PKSPROPERTY_CAMERACONTROL_S2 structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_CAMERACONTROL_S2, ksmedia/PKSPROPERTY_CAMERACONTROL_S2, stream.ksproperty_cameracontrol_s2, vidcapstruct_8ffb951a-dfed-4871-b8f8-36e975884c1e.xml"
f1_keywords:
 - "ksmedia/KSPROPERTY_CAMERACONTROL_S2"
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
- ksmedia.h
api_name:
- KSPROPERTY_CAMERACONTROL_S2
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_CAMERACONTROL_S2, *PKSPROPERTY_CAMERACONTROL_S2
---

# KSPROPERTY_CAMERACONTROL_S2 structure


## -description


The KSPROPERTY_CAMERACONTROL_S2 structure describes filter-based properties in the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/propsetid-vidcap-cameracontrol">PROPSETID_VIDCAP_CAMERACONTROL</a> property set that use two values at the same time.


## -struct-fields




### -field Property

Specifies an initialized <a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a> structure that describes the property set, property ID, and request type. 


### -field Value1

Specifies the first value of the property. This member is read/write.


### -field Flags

Indicates, for get requests, the current setting for the specified property from the values listed below. Indicates, for set requests, the desired setting for the specified property from the values listed below. This member can be set to one of the following values that are defined in <i>ksmedia.h</i>:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KSPROPERTY_CAMERACONTROL_FLAGS_MANUAL

</td>
<td>
Indicates that the setting is controlled manually

</td>
</tr>
<tr>
<td>
KSPROPERTY_CAMERACONTROL_FLAGS_AUTO

</td>
<td>
Indicates that the setting is controlled automatically

</td>
</tr>
<tr>
<td>
KSPROPERTY_CAMERACONTROL_FLAGS_ABSOLUTE

</td>
<td>
Indicates that the setting is in absolute values

</td>
</tr>
<tr>
<td>
KSPROPERTY_CAMERACONTROL_FLAGS_RELATIVE

</td>
<td>
Indicates that the setting is in relative values

</td>
</tr>
</table>
 


### -field Capabilities

Indicates the minidriver's camera control capabilities for the specified property. This member is read-only. This member can be set to one of the following values that are defined in <i>ksmedia.h</i>:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KSPROPERTY_CAMERACONTROL_FLAGS_MANUAL

</td>
<td>
Indicates that the device can be controlled manually

</td>
</tr>
<tr>
<td>
KSPROPERTY_CAMERACONTROL_FLAGS_AUTO

</td>
<td>
Indicates that the device can be controlled automatically

</td>
</tr>
<tr>
<td>
KSPROPERTY_CAMERACONTROL_FLAGS_ABSOLUTE

</td>
<td>
Indicates that the device settings are in absolute values

</td>
</tr>
<tr>
<td>
KSPROPERTY_CAMERACONTROL_FLAGS_RELATIVE

</td>
<td>
Indicates that the device settings are in relative values

</td>
</tr>
</table>
 


### -field Value2

Specifies the second value of the property. This member is read/write.


## -remarks



This structure is used by <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-cameracontrol-pantilt">KSPROPERTY_CAMERACONTROL_PANTILT</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-cameracontrol-pantilt-relative">KSPROPERTY_CAMERACONTROL_PANTILT_RELATIVE</a> for filter-based get/set property requests.



