---
UID: NS:ksmedia.KSDATARANGE_AUDIO
title: KSDATARANGE_AUDIO
author: windows-driver-content
description: The KSDATARANGE_AUDIO structure specifies a range of audio formats.
old-location: audio\ksdatarange_audio.htm
old-project: audio
ms.assetid: 53631f26-8377-4ab5-83db-ed241c11643a
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PKSDATARANGE_AUDIO, KSDATARANGE_AUDIO structure [Audio Devices], audio.ksdatarange_audio, aud-prop_9a59d4cd-4c84-4c22-8a36-741cf53ec08d.xml, ksmedia/PKSDATARANGE_AUDIO, PKSDATARANGE_AUDIO structure pointer [Audio Devices], KSDATARANGE_AUDIO, *PKSDATARANGE_AUDIO, ksmedia/KSDATARANGE_AUDIO
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
-	KSDATARANGE_AUDIO
product: Windows
targetos: Windows
req.typenames: "*PKSDATARANGE_AUDIO, KSDATARANGE_AUDIO"
---

# KSDATARANGE_AUDIO structure


## -description


The KSDATARANGE_AUDIO structure specifies a range of audio formats.


## -syntax


````
typedef struct {
  KSDATARANGE DataRange;
  ULONG       MaximumChannels;
  ULONG       MinimumBitsPerSample;
  ULONG       MaximumBitsPerSample;
  ULONG       MinimumSampleFrequency;
  ULONG       MaximumSampleFrequency;
} KSDATARANGE_AUDIO, *PKSDATARANGE_AUDIO;
````


## -struct-fields




### -field DataRange

Specifies the MajorFormat and SubFormat GUIDs as well as the Specifier GUID for the audio data. This member is an initialized <a href="..\ks\ns-ks-ksdataformat.md">KSDATARANGE</a> structure.


### -field MaximumChannels

Specifies the maximum number of channels supported. A value of (ULONG)-1 for this member means that the number of channels has no explicit limit, although the number of channels might be practically limited by the availability of resources such as memory or processing power.


### -field MinimumBitsPerSample

Specifies the minimum bits per sample supported.


### -field MaximumBitsPerSample

Specifies the maximum bits per sample supported.


### -field MinimumSampleFrequency

Specifies the minimum frequency allowed.


### -field MaximumSampleFrequency

Specifies the maximum frequency allowed.


## -remarks


For examples of data ranges that use the KSDATARANGE_AUDIO structure, see <a href="https://msdn.microsoft.com/e8a9b681-3bd2-46ed-970f-5217dbfb2e4e">PCM Stream Data Range</a>, <a href="https://msdn.microsoft.com/cc31eb2d-7421-4748-b14c-f4d3d15f9884">DirectSound Stream Data Range</a>, and <a href="https://msdn.microsoft.com/87d59554-43fa-4d61-9829-c38691d0a525">Specifying AC-3 Data Ranges</a>.

For information about data ranges and intersection handling, see <a href="https://msdn.microsoft.com/7206afdb-8a34-4b5a-8cea-87119f426161">Data-Intersection Handlers</a>.



## -see-also

<a href="..\ks\ns-ks-ksdataformat.md">KSDATARANGE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSDATARANGE_AUDIO structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

