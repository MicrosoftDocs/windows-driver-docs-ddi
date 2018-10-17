---
UID: NS:ksmedia.KSPROPERTY_CAMERACONTROL_NODE_S
title: KSPROPERTY_CAMERACONTROL_NODE_S
author: windows-driver-content
description: The KSPROPERTY_CAMERACONTROL_NODE_S structure describes node-based properties in the PROPSETID_VIDCAP_CAMERACONTROL property set. This structure specifies property values in requests to the USB Video Class driver.
old-location: stream\ksproperty_cameracontrol_node_s.htm
tech.root: stream
ms.assetid: ced1d848-fb6e-4207-bdb0-29ca82249d06
ms.date: 4/23/2018
ms.keywords: KSPROPERTY_CAMERACONTROL_NODE_S, KSPROPERTY_CAMERACONTROL_NODE_S structure [Streaming Media Devices], PKSPROPERTY_CAMERACONTROL_NODE_S, PKSPROPERTY_CAMERACONTROL_NODE_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_CAMERACONTROL_NODE_S, ksmedia/PKSPROPERTY_CAMERACONTROL_NODE_S, stream.ksproperty_cameracontrol_node_s, vidcapstruct_fbe0c251-5c32-49b7-978c-67b52c920613.xml
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KSPROPERTY_CAMERACONTROL_NODE_S
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_CAMERACONTROL_NODE_S, PKSPROPERTY_CAMERACONTROL_NODE_S
---

# KSPROPERTY_CAMERACONTROL_NODE_S structure


## -description


The KSPROPERTY_CAMERACONTROL_NODE_S structure describes node-based properties in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567802">PROPSETID_VIDCAP_CAMERACONTROL</a> property set. This structure specifies property values in requests to the USB Video Class driver.


## -struct-fields




### -field NodeProperty

Specifies an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff566720">KSP_NODE</a> structure that describes the property set, property ID, request type, and node ID. 


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
 


## -remarks



See related information about the <a href="https://msdn.microsoft.com/84b5302d-c4c1-4519-bb94-66e80879ce26">USB Video Class Driver</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564439">KSPROPERTY_CAMERACONTROL_S</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567802">PROPSETID_VIDCAP_CAMERACONTROL</a>
 

 

