---
UID: NS:ksmedia.KSPROPERTY_VIDEOPROCAMP_NODE_S
title: KSPROPERTY_VIDEOPROCAMP_NODE_S
author: windows-driver-content
description: The KSPROPERTY_VIDEOPROCAMP_NODE_S structure describes node-based property settings in the PROPSETID_VIDCAP_VIDEOPROCAMP property set.
old-location: stream\ksproperty_videoprocamp_node_s.htm
old-project: stream
ms.assetid: 7350ffec-2993-4f05-b031-3d633a6f17ad
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSPROPERTY_VIDEOPROCAMP_NODE_S, KSPROPERTY_VIDEOPROCAMP_NODE_S, KSPROPERTY_VIDEOPROCAMP_NODE_S structure [Streaming Media Devices], PKSPROPERTY_VIDEOPROCAMP_NODE_S, PKSPROPERTY_VIDEOPROCAMP_NODE_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_VIDEOPROCAMP_NODE_S, ksmedia/PKSPROPERTY_VIDEOPROCAMP_NODE_S, stream.ksproperty_videoprocamp_node_s, vidcapstruct_d7d544d4-dd33-4498-9104-c63fa5a48079.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	KSPROPERTY_VIDEOPROCAMP_NODE_S
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_VIDEOPROCAMP_NODE_S, *PKSPROPERTY_VIDEOPROCAMP_NODE_S
---

# KSPROPERTY_VIDEOPROCAMP_NODE_S structure


## -description


The KSPROPERTY_VIDEOPROCAMP_NODE_S structure describes node-based property settings in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568122">PROPSETID_VIDCAP_VIDEOPROCAMP</a> property set.


## -struct-fields




### -field NodeProperty

Specifies an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff566720">KSP_NODE</a> structure that describes the node, property set, property ID, and request type.


### -field Value

Specifies the value of a request. For Set requests, the minidriver should set the property specified in <b>Property</b> to this value. For Get requests, the minidriver should return the value of the property specified in <b>Property</b>.


### -field Flags

Specifies the flags of a request. For Set requests, this value indicates the desired setting. For Get requests, this value contains the current setting. This member can be set to one of the values that are defined in <i>ksmedia.h</i>:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KSPROPERTY_VIDEOPROCAMP_FLAGS_MANUAL

</td>
<td>
Indicates that the property is to be adjusted manually.

</td>
</tr>
<tr>
<td>
KSPROPERTY_VIDEOPROCAMP_FLAGS_AUTO

</td>
<td>
Indicates that the property is to be adjusted automatically.

</td>
</tr>
</table>
 


### -field Capabilities

Specifies the capabilities of a property. This member has meaning only for Get requests. The minidriver should return the capabilities of the VideoProcAmp with respect to the property specified in <b>Property</b>. This member should be set to one of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KSPROPERTY_VIDEOPROCAMP_FLAGS_MANUAL

</td>
<td>
The device supports manual setting of the specified property.

</td>
</tr>
<tr>
<td>
KSPROPERTY_VIDEOPROCAMP_FLAGS_AUTO

</td>
<td>
The device supports automatic setting of the specified property.

</td>
</tr>
</table>
 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566089">KSPROPERTY_VIDEOPROCAMP_S</a>
 

 

