---
UID: NS:ksmedia.KSPROPERTY_CAMERACONTROL_S
title: KSPROPERTY_CAMERACONTROL_S
author: windows-driver-content
description: The KSPROPERTY_CAMERACONTROL_S structure describes filter-based properties in the PROPSETID_VIDCAP_CAMERACONTROL property set.
old-location: stream\ksproperty_cameracontrol_s.htm
old-project: stream
ms.assetid: 203c6452-26d4-4dbf-89d4-c7e6d47e7c16
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.ksproperty_cameracontrol_s, PKSPROPERTY_CAMERACONTROL_S, KSPROPERTY_CAMERACONTROL_S structure [Streaming Media Devices], ksmedia/KSPROPERTY_CAMERACONTROL_S, vidcapstruct_bfabf468-24f0-4acb-b064-229b3eea7df3.xml, ksmedia/PKSPROPERTY_CAMERACONTROL_S, KSPROPERTY_CAMERACONTROL_S, *PKSPROPERTY_CAMERACONTROL_S, PKSPROPERTY_CAMERACONTROL_S structure pointer [Streaming Media Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	KSPROPERTY_CAMERACONTROL_S
product: Windows
targetos: Windows
req.typenames: "*PKSPROPERTY_CAMERACONTROL_S, KSPROPERTY_CAMERACONTROL_S"
---

# KSPROPERTY_CAMERACONTROL_S structure


## -description


The KSPROPERTY_CAMERACONTROL_S structure describes filter-based properties in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567802">PROPSETID_VIDCAP_CAMERACONTROL</a> property set.


## -syntax


````
typedef struct {
  KSPROPERTY Property;
  LONG       Value;
  ULONG      Flags;
  ULONG      Capabilities;
} KSPROPERTY_CAMERACONTROL_S, *PKSPROPERTY_CAMERACONTROL_S;
````


## -struct-fields




### -field Property

Specifies an initialized <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure that describes the property set, property ID, and request type. 


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

<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>

<a href="..\ksmedia\ns-ksmedia-ksproperty_cameracontrol_node_s.md">KSPROPERTY_CAMERACONTROL_NODE_S</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567802">PROPSETID_VIDCAP_CAMERACONTROL</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_CAMERACONTROL_S structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

