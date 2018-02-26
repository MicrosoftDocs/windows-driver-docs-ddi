---
UID: NS:ksmedia.KSPROPERTY_TUNER_STATUS_S
title: KSPROPERTY_TUNER_STATUS_S
author: windows-driver-content
description: The KSPROPERTY_TUNER_STATUS_S structure describes the progress of a tuning operation for TV and radio tuner devices, including present tuning frequency.
old-location: stream\ksproperty_tuner_status_s.htm
old-project: stream
ms.assetid: 5e1b37f2-f567-4c03-b0f4-cc1dbd568907
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , *, *PKSPROPERTY_TUNER_STATUS_S, ,, A, E, K, KSPROPERTY_TUNER_STATUS_S, KSPROPERTY_TUNER_STATUS_S structure [Streaming Media Devices], N, O, P, PKSPROPERTY_TUNER_STATUS_S, PKSPROPERTY_TUNER_STATUS_S structure pointer [Streaming Media Devices], R, S, T, U, Y, _, ksmedia/KSPROPERTY_TUNER_STATUS_S, ksmedia/PKSPROPERTY_TUNER_STATUS_S, stream.ksproperty_tuner_status_s, vidcapstruct_a36247d8-99d7-4dad-8632-5feb685616d6.xml"
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
-	KSPROPERTY_TUNER_STATUS_S
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_TUNER_STATUS_S, *PKSPROPERTY_TUNER_STATUS_S
---

# KSPROPERTY_TUNER_STATUS_S structure


## -description


The KSPROPERTY_TUNER_STATUS_S structure describes the progress of a tuning operation for TV and radio tuner devices, including present tuning frequency.


## -syntax


````
typedef struct {
  KSPROPERTY Property;
  ULONG      CurrentFrequency;
  ULONG      PLLOffset;
  ULONG      SignalStrength;
  ULONG      Busy;
} KSPROPERTY_TUNER_STATUS_S, *PKSPROPERTY_TUNER_STATUS_S;
````


## -struct-fields




### -field Property

Specifies an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that describes the property set, property ID, and request type. 


### -field CurrentFrequency

Specifies the current tuner frequency. This value is in hertz (Hz).


### -field PLLOffset

Specifies the phase locked loop (PLL) offset in multiples of the tuning granularity. This is used if the tuner strategy is KS_TUNER_STRATEGY_PLL. If the tuner strategy is not KS_TUNER_STRATEGY_PLL, this value has no meaning. The following table demonstrates the value to be returned by the minidriver for various tuning conditions, assuming the tuning granularity is 62.5kHz:

<table>
<tr>
<th>Frequency Offset</th>
<th>PLLOffset</th>
</tr>
<tr>
<td>
+125,000

</td>
<td>
+2

</td>
</tr>
<tr>
<td>
+62,500

</td>
<td>
+1

</td>
</tr>
<tr>
<td>
Perfectly tuned

</td>
<td>
0

</td>
</tr>
<tr>
<td>
-62,500

</td>
<td>
-1

</td>
</tr>
<tr>
<td>
-125,000

</td>
<td>
-2

</td>
</tr>
</table>
 


### -field SignalStrength

Specifies the amplitude of the signal. This is used if the tuner strategy is KS_TUNER_STRATEGY_SIGNAL_STRENGTH. Regardless of the tuning strategy supported by the minidriver, the valid values for this member are:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
-1

</td>
<td>
Strength not Available.

</td>
</tr>
<tr>
<td>
0

</td>
<td>
Not on an acceptable frequency.

</td>
</tr>
<tr>
<td>
1

</td>
<td>
On an acceptable frequency.

</td>
</tr>
</table>
 


### -field Busy

Indicates if the minidriver is presently busy with the process of tuning. This member must be set to <b>TRUE</b> if the minidriver is currently tuning to a channel. Otherwise, if the minidriver is not currently tuning to a new channel, this member must be set to <b>FALSE</b>.


## -remarks



For more information about the <b>PLLOffset</b> and <b>SignalStrength</b> members see <a href="https://msdn.microsoft.com/ae97d5f7-82de-4d6e-9835-ff4c7427f333">PCI based TV capture</a>. If your tuner device supports radio tuning, see <a href="https://msdn.microsoft.com/36e3ca98-cb1b-46cc-809a-8c9ad08a53c8">Video Capture Devices with Radio Tuners</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565921">KSPROPERTY_TUNER_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567800">PROPSETID_TUNER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_TUNER_STATUS_S structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

