---
UID: NS:ksmedia.KSWAVE_COMPATCAPS
title: KSWAVE_COMPATCAPS
author: windows-driver-content
description: The KSWAVE_COMPATCAPS structure is used to describe the compatible capabilities of a device.
old-location: stream\kswave_compatcaps.htm
old-project: stream
ms.assetid: 92e6090e-6a31-45d9-ac6d-a20bf180f12e
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSWAVE_COMPATCAPS, PKSWAVE_COMPATCAPS structure pointer [Streaming Media Devices], PKSWAVE_COMPATCAPS, stream.kswave_compatcaps, ksmedia/PKSWAVE_COMPATCAPS, dvdref_496e945d-fb6d-47da-8668-4cb8f1b265e6.xml, KSWAVE_COMPATCAPS structure [Streaming Media Devices], ksmedia/KSWAVE_COMPATCAPS, *PKSWAVE_COMPATCAPS
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
-	KSWAVE_COMPATCAPS
product: Windows
targetos: Windows
req.typenames: "*PKSWAVE_COMPATCAPS, KSWAVE_COMPATCAPS"
---

# KSWAVE_COMPATCAPS structure


## -description


The KSWAVE_COMPATCAPS structure is used to describe the compatible capabilities of a device.


## -syntax


````
typedef struct {
  ULONG ulDeviceType;
} KSWAVE_COMPATCAPS, *PKSWAVE_COMPATCAPS;
````


## -struct-fields




### -field ulDeviceType

Specifies the following flags:
<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KSWAVE_COMPATCAPS_INPUT

</td>
<td>
Indicates that the device accepts input.

</td>
</tr>
<tr>
<td>
KSWAVE_COMPATCAPS_OUTPUT

</td>
<td>
Indicates that the device produces output.

</td>
</tr>
</table> 


## -remarks


This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566516">KSPROPERTY_WAVE_COMPATIBLE_CAPABILITIES</a> property.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566516">KSPROPERTY_WAVE_COMPATIBLE_CAPABILITIES</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSWAVE_COMPATCAPS structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

