---
UID: NS:ksmedia.KSPROPERTY_TUNER_MODE_S
title: KSPROPERTY_TUNER_MODE_S
author: windows-driver-content
description: The KSPROPERTY_TUNER_MODE_S structure describes the mode of a TV or radio tuner device.
old-location: stream\ksproperty_tuner_mode_s.htm
old-project: stream
ms.assetid: a3e443e5-1766-4292-a25a-ad673734bac1
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: vidcapstruct_fe1fe8d4-8abd-4db3-8438-ef7dddadfa5c.xml, ksmedia/KSPROPERTY_TUNER_MODE_S, PKSPROPERTY_TUNER_MODE_S structure pointer [Streaming Media Devices], stream.ksproperty_tuner_mode_s, *PKSPROPERTY_TUNER_MODE_S, KSPROPERTY_TUNER_MODE_S, KSPROPERTY_TUNER_MODE_S structure [Streaming Media Devices], PKSPROPERTY_TUNER_MODE_S, ksmedia/PKSPROPERTY_TUNER_MODE_S
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
-	KSPROPERTY_TUNER_MODE_S
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_TUNER_MODE_S, *PKSPROPERTY_TUNER_MODE_S
---

# KSPROPERTY_TUNER_MODE_S structure


## -description


The KSPROPERTY_TUNER_MODE_S structure describes the mode of a TV or radio tuner device.


## -syntax


````
typedef struct {
  KSPROPERTY Property;
  ULONG      Mode;
} KSPROPERTY_TUNER_MODE_S, *PKSPROPERTY_TUNER_MODE_S;
````


## -struct-fields




### -field Property

Specifies an initialized <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field Mode

Specifies the current tuner mode. If the request is a Get request, the minidriver should return the current tuner mode. If the request is a Set request, the minidriver should switch the current tuner mode to the specified value. This member can be one of the following tuner modes from the KSPROPERTY_TUNER_MODES enumeration that is defined in <i>K</i><i>smedia.h</i>:
<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KSPROPERTY_TUNER_MODE_TV

</td>
<td>
Indicates that the tuner is currently tuning (get) or should switch to tuning broadcast or cable television channels (set).

</td>
</tr>
<tr>
<td>
KSPROPERTY_TUNER_MODE_FM_RADIO

</td>
<td>
Indicates that the tuner is currently tuning (get) or should switch to tuning (set) FM radio channels.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TUNER_MODE_AM_RADIO

</td>
<td>
Indicates that the tuner is currently tuning (get) or should switch to tuning (set) AM radio channels.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TUNER_MODE_DSS

</td>
<td>
Indicates that the tuner is currently tuning (get) or should switch to tuning (set) tuning DSS channels.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TUNER_MODE_ATSC

</td>
<td>
Indicates that the tuner is capable of tuning (get) or should switch to tuning (set) Advanced Television Systems Committee broadcasts (Digital TV for the United States). This setting can also be used by DVB-T and DVB-C systems.

</td>
</tr>
</table> 


## -see-also

<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565862">KSPROPERTY_TUNER_MODE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567800">PROPSETID_TUNER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_TUNER_MODE_S structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

