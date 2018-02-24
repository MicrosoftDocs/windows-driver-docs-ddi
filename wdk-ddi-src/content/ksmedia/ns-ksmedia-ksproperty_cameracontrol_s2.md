---
UID: NS:ksmedia.KSPROPERTY_CAMERACONTROL_S2
title: KSPROPERTY_CAMERACONTROL_S2
author: windows-driver-content
description: The KSPROPERTY_CAMERACONTROL_S2 structure describes filter-based properties in the PROPSETID_VIDCAP_CAMERACONTROL property set that use two values at the same time.
old-location: stream\ksproperty_cameracontrol_s2.htm
old-project: stream
ms.assetid: b0ea25c0-5b10-403f-8c61-7840fe062596
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: PKSPROPERTY_CAMERACONTROL_S2, KSPROPERTY_CAMERACONTROL_S2 structure [Streaming Media Devices], stream.ksproperty_cameracontrol_s2, ksmedia/PKSPROPERTY_CAMERACONTROL_S2, ksmedia/KSPROPERTY_CAMERACONTROL_S2, PKSPROPERTY_CAMERACONTROL_S2 structure pointer [Streaming Media Devices], vidcapstruct_8ffb951a-dfed-4871-b8f8-36e975884c1e.xml, KSPROPERTY_CAMERACONTROL_S2, *PKSPROPERTY_CAMERACONTROL_S2
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
-	KSPROPERTY_CAMERACONTROL_S2
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_CAMERACONTROL_S2, *PKSPROPERTY_CAMERACONTROL_S2
---

# KSPROPERTY_CAMERACONTROL_S2 structure


## -description


The KSPROPERTY_CAMERACONTROL_S2 structure describes filter-based properties in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567802">PROPSETID_VIDCAP_CAMERACONTROL</a> property set that use two values at the same time.


## -syntax


````
typedef struct {
  KSPROPERTY Property;
  LONG       Value1;
  ULONG      Flags;
  ULONG      Capabilities;
  LONG       Value2;
} KSPROPERTY_CAMERACONTROL_S2, *PKSPROPERTY_CAMERACONTROL_S2;
````


## -struct-fields




### -field Property

Specifies an initialized <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure that describes the property set, property ID, and request type. 


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



This structure is used by <a href="https://msdn.microsoft.com/library/windows/hardware/ff564425">KSPROPERTY_CAMERACONTROL_PANTILT</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff564427">KSPROPERTY_CAMERACONTROL_PANTILT_RELATIVE</a> for filter-based get/set property requests.



