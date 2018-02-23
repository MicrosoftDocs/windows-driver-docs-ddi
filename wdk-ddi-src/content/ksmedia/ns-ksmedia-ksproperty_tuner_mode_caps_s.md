---
UID: NS:ksmedia.KSPROPERTY_TUNER_MODE_CAPS_S
title: KSPROPERTY_TUNER_MODE_CAPS_S
author: windows-driver-content
description: The KS_PROPERTY_TUNER_MODE_CAPS_S structure describes the capabilities of TV and radio tuner devices.
old-location: stream\ksproperty_tuner_mode_caps_s.htm
old-project: stream
ms.assetid: e2376cde-7e13-475d-a118-0cf48ba8a742
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: vidcapstruct_d80882b8-2962-48c3-b2e9-393deec31ccc.xml, ksmedia/KSPROPERTY_TUNER_MODE_CAPS_S, KSPROPERTY_TUNER_MODE_CAPS_S structure [Streaming Media Devices], *PKSPROPERTY_TUNER_MODE_CAPS_S, ksmedia/PKSPROPERTY_TUNER_MODE_CAPS_S, PKSPROPERTY_TUNER_MODE_CAPS_S, KSPROPERTY_TUNER_MODE_CAPS_S, stream.ksproperty_tuner_mode_caps_s, PKSPROPERTY_TUNER_MODE_CAPS_S structure pointer [Streaming Media Devices]
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
-	KSPROPERTY_TUNER_MODE_CAPS_S
product: Windows
targetos: Windows
req.typenames: "*PKSPROPERTY_TUNER_MODE_CAPS_S, KSPROPERTY_TUNER_MODE_CAPS_S"
---

# KSPROPERTY_TUNER_MODE_CAPS_S structure


## -description


The KS_PROPERTY_TUNER_MODE_CAPS_S structure describes the capabilities of TV and radio tuner devices.


## -syntax


````
typedef struct {
  KSPROPERTY Property;
  ULONG      Mode;
  ULONG      StandardsSupported;
  ULONG      MinFrequency;
  ULONG      MaxFrequency;
  ULONG      TuningGranularity;
  ULONG      NumberOfInputs;
  ULONG      SettlingTime;
  ULONG      Strategy;
} KSPROPERTY_TUNER_MODE_CAPS_S, *PKSPROPERTY_TUNER_MODE_CAPS_S;
````


## -struct-fields




### -field Property

Specifies an initialized <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field Mode

Specifies the tuner mode that the caller is requesting capability information about. It can be one of the following tuner modes from the KSPROPERTY_TUNER_MODES enumeration that is defined in <i>ksmedia.h</i>:

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
Indicates that the tuner is capable of tuning analog broadcast or cable television channels.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TUNER_MODE_FM_RADIO

</td>
<td>
Indicates that the tuner is capable of tuning FM radio channels.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TUNER_MODE_AM_RADIO

</td>
<td>
Indicates that the tuner is capable of tuning AM radio channels.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TUNER_MODE_DSS

</td>
<td>
Indicates that the tuner is capable of tuning DSS channels.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TUNER_MODE_ATSC

</td>
<td>
Indicates that the tuner is capable of tuning Advanced Television Systems Committee broadcasts (Digital TV for the United States) or other digital television standard.

</td>
</tr>
</table>
 


### -field StandardsSupported

Describes the analog video standards supported. If <b>Mode</b> is set to KSPROPERTY_TUNER_MODE_TV, this member may be set to one or more (logically ORed) values from the <a href="..\ksmedia\ne-ksmedia-ks_analogvideostandard.md">KS_AnalogVideoStandard</a> enumeration.


### -field MinFrequency

Specifies the lowest frequency supported by the tuner. This value is in hertz (Hz).


### -field MaxFrequency

Specifies the highest frequency supported by the tuner. This value is in hertz (Hz).


### -field TuningGranularity

Specifies the smallest possible step size between two settings of the tuning frequency. This value is in hertz (Hz).


### -field NumberOfInputs

Specifies the number of inputs on the tuner.


### -field SettlingTime

Specifies the time, in milliseconds, for a new frequency setting to become stable.


### -field Strategy

Specifies the tuning method. This member must be set to only one of the values from the <a href="..\ksmedia\ne-ksmedia-ks_tuner_strategy.md">KS_TUNER_STRATEGY</a> enumeration.


## -remarks



The minidriver fills in the mode capabilities for the requested tuner mode.




## -see-also

<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>



<a href="..\ksmedia\ne-ksmedia-ks_analogvideostandard.md">KS_AnalogVideoStandard</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567800">PROPSETID_TUNER</a>



<a href="..\ksmedia\ne-ksmedia-ks_tuner_strategy.md">KS_TUNER_STRATEGY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565865">KSPROPERTY_TUNER_MODE_CAPS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_TUNER_MODE_CAPS_S structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

