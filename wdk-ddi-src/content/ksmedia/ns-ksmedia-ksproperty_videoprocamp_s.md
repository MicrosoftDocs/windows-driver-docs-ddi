---
UID: NS:ksmedia.KSPROPERTY_VIDEOPROCAMP_S
title: KSPROPERTY_VIDEOPROCAMP_S
author: windows-driver-content
description: The KSPROPERTY_VIDEOPROCAMP_S structure describes filter-based property settings in the PROPSETID_VIDCAP_VIDEOPROCAMP property set.
old-location: stream\ksproperty_videoprocamp_s.htm
old-project: stream
ms.assetid: e8b9c381-2159-4cb2-92e2-11c1d3698f2d
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: "*PKSPROPERTY_VIDEOPROCAMP_S, vidcapstruct_4ec1fd8e-6ea5-4560-a528-e6cd2023ec87.xml, ksmedia/KSPROPERTY_VIDEOPROCAMP_S, KSPROPERTY_VIDEOPROCAMP_S, ksmedia/PKSPROPERTY_VIDEOPROCAMP_S, stream.ksproperty_videoprocamp_s, PKSPROPERTY_VIDEOPROCAMP_S, KSPROPERTY_VIDEOPROCAMP_S structure [Streaming Media Devices], PKSPROPERTY_VIDEOPROCAMP_S structure pointer [Streaming Media Devices]"
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
-	KSPROPERTY_VIDEOPROCAMP_S
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_VIDEOPROCAMP_S, *PKSPROPERTY_VIDEOPROCAMP_S
---

# KSPROPERTY_VIDEOPROCAMP_S structure


## -description


The KSPROPERTY_VIDEOPROCAMP_S structure describes filter-based property settings in the PROPSETID_VIDCAP_VIDEOPROCAMP property set.


## -syntax


````
typedef struct {
  KSPROPERTY Property;
  LONG       Value;
  ULONG      Flags;
  ULONG      Capabilities;
} KSPROPERTY_VIDEOPROCAMP_S, *PKSPROPERTY_VIDEOPROCAMP_S;
````


## -struct-fields




### -field Property

Specifies an initialized <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566070">KSPROPERTY_VIDEOPROCAMP_CONTRAST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566066">KSPROPERTY_VIDEOPROCAMP_COLORENABLE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566095">KSPROPERTY_VIDEOPROCAMP_WHITEBALANCE</a>



<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566065">KSPROPERTY_VIDEOPROCAMP_BRIGHTNESS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566093">KSPROPERTY_VIDEOPROCAMP_SHARPNESS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566063">KSPROPERTY_VIDEOPROCAMP_BACKLIGHT_COMPENSATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566076">KSPROPERTY_VIDEOPROCAMP_GAMMA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566092">KSPROPERTY_VIDEOPROCAMP_SATURATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566078">KSPROPERTY_VIDEOPROCAMP_HUE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568122">PROPSETID_VIDCAP_VIDEOPROCAMP</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_VIDEOPROCAMP_S structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

