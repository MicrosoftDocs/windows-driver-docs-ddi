---
UID: NS:ksmedia.__unnamed_struct_114
title: KSPROPERTY_CAMERACONTROL_S (ksmedia.h)
description: The KSPROPERTY_CAMERACONTROL_S structure describes filter-based properties in the PROPSETID_VIDCAP_CAMERACONTROL property set.
old-location: stream\ksproperty_cameracontrol_s.htm
tech.root: stream
ms.assetid: 203c6452-26d4-4dbf-89d4-c7e6d47e7c16
ms.date: 04/23/2018
ms.keywords: "*PKSPROPERTY_CAMERACONTROL_S, KSPROPERTY_CAMERACONTROL_S, KSPROPERTY_CAMERACONTROL_S structure [Streaming Media Devices], PKSPROPERTY_CAMERACONTROL_S, PKSPROPERTY_CAMERACONTROL_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_CAMERACONTROL_S, ksmedia/PKSPROPERTY_CAMERACONTROL_S, stream.ksproperty_cameracontrol_s, vidcapstruct_bfabf468-24f0-4acb-b064-229b3eea7df3.xml"
ms.topic: struct
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
- KSPROPERTY_CAMERACONTROL_S
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_CAMERACONTROL_S, *PKSPROPERTY_CAMERACONTROL_S
---

# KSPROPERTY_CAMERACONTROL_S structure


## -description


The KSPROPERTY_CAMERACONTROL_S structure describes filter-based properties in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567802">PROPSETID_VIDCAP_CAMERACONTROL</a> property set.


## -struct-fields




### -field Property

Specifies an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that describes the property set, property ID, and request type. 


### -field Value

Specifies the value of the property. This member is read/write.


### -field Flags

Indicates, for Get requests, the current setting for the specified property from the values listed below. Indicates, for Set requests, the desired setting for the specified property from the values listed below. This member can be set to one of the following values that are defined in <i>ksmedia.h</i>:

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
Indicates that the setting is controlled manually.

</td>
</tr>
<tr>
<td>
KSPROPERTY_CAMERACONTROL_FLAGS_AUTO

</td>
<td>
Indicates that the setting is controlled automatically.

</td>
</tr>
<tr>
<td>
KSPROPERTY_CAMERACONTROL_FLAGS_ABSOLUTE

</td>
<td>
Indicates that the setting is in absolute values.

</td>
</tr>
<tr>
<td>
KSPROPERTY_CAMERACONTROL_FLAGS_RELATIVE

</td>
<td>
Indicates that the setting is in relative values.

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
Indicates that the device can be controlled manually.

</td>
</tr>
<tr>
<td>
KSPROPERTY_CAMERACONTROL_FLAGS_AUTO

</td>
<td>
Indicates that the device can be controlled automatically.

</td>
</tr>
<tr>
<td>
KSPROPERTY_CAMERACONTROL_FLAGS_ABSOLUTE

</td>
<td>
Indicates that the device settings are in absolute values.

</td>
</tr>
<tr>
<td>
KSPROPERTY_CAMERACONTROL_FLAGS_RELATIVE

</td>
<td>
Indicates that the device settings are in relative values.

</td>
</tr>
</table>
 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564420">KSPROPERTY_CAMERACONTROL_NODE_S</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567802">PROPSETID_VIDCAP_CAMERACONTROL</a>
 

 

