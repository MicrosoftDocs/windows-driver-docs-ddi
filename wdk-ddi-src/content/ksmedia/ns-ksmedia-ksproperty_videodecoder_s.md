---
UID: NS:ksmedia.KSPROPERTY_VIDEODECODER_S
title: KSPROPERTY_VIDEODECODER_S
author: windows-driver-content
description: The KSPROPERTY_VIDEODECODER_S structure describes property settings in the PROPSETID_VIDCAP_VIDEODECODER property set.
old-location: stream\ksproperty_videodecoder_s.htm
old-project: stream
ms.assetid: 9444835d-0290-49e7-8f49-a1506ce282cd
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSPROPERTY_VIDEODECODER_S, KSPROPERTY_VIDEODECODER_S, KSPROPERTY_VIDEODECODER_S structure [Streaming Media Devices], PKSPROPERTY_VIDEODECODER_S, PKSPROPERTY_VIDEODECODER_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_VIDEODECODER_S, ksmedia/PKSPROPERTY_VIDEODECODER_S, stream.ksproperty_videodecoder_s, vidcapstruct_fbca2e77-2e08-4a96-932d-706a7e8b9a2a.xml"
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
-	KSPROPERTY_VIDEODECODER_S
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_VIDEODECODER_S, *PKSPROPERTY_VIDEODECODER_S
---

# KSPROPERTY_VIDEODECODER_S structure


## -description


The KSPROPERTY_VIDEODECODER_S structure describes property settings in the PROPSETID_VIDCAP_VIDEODECODER property set.


## -syntax


````
typedef struct {
  KSPROPERTY Property;
  ULONG      Value;
} KSPROPERTY_VIDEODECODER_S, *PKSPROPERTY_VIDEODECODER_S;
````


## -struct-fields




### -field Property

Specifies an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field Value

Specifies the value of a request. For Set requests, the minidriver should set the property specified in <b>Property</b> to this value. For Get requests, the minidriver should return the value of the property specified in <b>Property</b>.


## -remarks



The KSPROPERTY_VIDEODECODER_S structure is shared among the KSPROPERTY_VIDEODECODER_STANDARD, KSPROPERTY_VIDEODECODER_OUTPUT_ENABLE, and KSPROPERTY_VIDEODECODER_VCR_TIMING properties within the property set. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566058">KSPROPERTY_VIDEODECODER_STANDARD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566062">KSPROPERTY_VIDEODECODER_VCR_TIMING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566051">KSPROPERTY_VIDEODECODER_OUTPUT_ENABLE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_VIDEODECODER_S structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

