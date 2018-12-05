---
UID: NS:ksmedia.__unnamed_struct_1
title: KSDATAFORMAT_WAVEFORMATEX
author: windows-driver-content
description: The KSDATAFORMAT_WAVEFORMATEX structure provides detailed information about the data format of an audio stream consisting of wave data.
old-location: audio\ksdataformat_waveformatex.htm
tech.root: audio
ms.assetid: b4c0cca8-6277-4458-b1f1-894848987074
ms.date: 05/08/2018
ms.keywords: "*PKSDATAFORMAT_WAVEFORMATEX, KSDATAFORMAT_WAVEFORMATEX, KSDATAFORMAT_WAVEFORMATEX structure [Audio Devices], PKSDATAFORMAT_WAVEFORMATEX, PKSDATAFORMAT_WAVEFORMATEX structure pointer [Audio Devices], aud-prop_a51a849b-8e4b-4516-adab-7d8ef992f75b.xml, audio.ksdataformat_waveformatex, ksmedia/KSDATAFORMAT_WAVEFORMATEX, ksmedia/PKSDATAFORMAT_WAVEFORMATEX"
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
-	KSDATAFORMAT_WAVEFORMATEX
product:
- Windows
targetos: Windows
req.typenames: KSDATAFORMAT_WAVEFORMATEX, *PKSDATAFORMAT_WAVEFORMATEX
---

# KSDATAFORMAT_WAVEFORMATEX structure


## -description


The KSDATAFORMAT_WAVEFORMATEX structure provides detailed information about the data format of an audio stream consisting of wave data.


## -struct-fields




### -field DataFormat

Specifies the general features of the stream's data format. This member is a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff561656(v=vs.85).aspx">KSDATAFORMAT</a>.


### -field WaveFormatEx

Describes the wave-specific details of the audio stream's data format. This member contains an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff538799">WAVEFORMATEX</a> structure.


## -remarks



In response to an input <i>DataRange</i> parameter that specifies a WAVEFORMATEX format (see example in <a href="https://msdn.microsoft.com/e8a9b681-3bd2-46ed-970f-5217dbfb2e4e">PCM Stream Data Range</a>), the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536764">IMiniport::DataRangeIntersection</a> method checks to see if the specified pin supports a compatible WAVEFORMATEX format. If so, the method outputs a KSDATAFORMAT_WAVEFORMATEX structure (see example in <a href="https://msdn.microsoft.com/86599e55-e771-4d6e-ad59-6dc905c53cd8">PCM Stream Data Format</a>) to the buffer that its <i>ResultantFormat</i> parameter points to.

Note that the <b>WaveFormatEx</b> member of the KSDATAFORMAT_WAVEFORMATEX structure can be extended to include additional format information (for example, a channel configuration mask). For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff538802">WAVEFORMATEXTENSIBLE</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536764">IMiniport::DataRangeIntersection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561656(v=vs.85).aspx">KSDATAFORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538799">WAVEFORMATEX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538802">WAVEFORMATEXTENSIBLE</a>
 

 

