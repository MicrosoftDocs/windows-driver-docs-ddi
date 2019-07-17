---
UID: NS:ksmedia.__unnamed_struct_1
title: KSDATAFORMAT_WAVEFORMATEX (ksmedia.h)
description: The KSDATAFORMAT_WAVEFORMATEX structure provides detailed information about the data format of an audio stream consisting of wave data.
old-location: audio\ksdataformat_waveformatex.htm
tech.root: audio
ms.assetid: b4c0cca8-6277-4458-b1f1-894848987074
ms.date: 05/08/2018
ms.keywords: "*PKSDATAFORMAT_WAVEFORMATEX, KSDATAFORMAT_WAVEFORMATEX, KSDATAFORMAT_WAVEFORMATEX structure [Audio Devices], PKSDATAFORMAT_WAVEFORMATEX, PKSDATAFORMAT_WAVEFORMATEX structure pointer [Audio Devices], aud-prop_a51a849b-8e4b-4516-adab-7d8ef992f75b.xml, audio.ksdataformat_waveformatex, ksmedia/KSDATAFORMAT_WAVEFORMATEX, ksmedia/PKSDATAFORMAT_WAVEFORMATEX"
ms.topic: struct
f1_keywords:
 - "ksmedia/KSDATAFORMAT_WAVEFORMATEX"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ksmedia.h
api_name:
- KSDATAFORMAT_WAVEFORMATEX
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

Specifies the general features of the stream's data format. This member is a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksdataformat">KSDATAFORMAT</a>.


### -field WaveFormatEx

Describes the wave-specific details of the audio stream's data format. This member contains an initialized <a href="https://docs.microsoft.com/windows/desktop/api/mmreg/ns-mmreg-twaveformatex">WAVEFORMATEX</a> structure.


## -remarks



In response to an input <i>DataRange</i> parameter that specifies a WAVEFORMATEX format (see example in <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/pcm-stream-data-range">PCM Stream Data Range</a>), the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iminiport-datarangeintersection">IMiniport::DataRangeIntersection</a> method checks to see if the specified pin supports a compatible WAVEFORMATEX format. If so, the method outputs a KSDATAFORMAT_WAVEFORMATEX structure (see example in <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/pcm-stream-data-format">PCM Stream Data Format</a>) to the buffer that its <i>ResultantFormat</i> parameter points to.

Note that the <b>WaveFormatEx</b> member of the KSDATAFORMAT_WAVEFORMATEX structure can be extended to include additional format information (for example, a channel configuration mask). For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksmedia/ns-ksmedia-waveformatextensible">WAVEFORMATEXTENSIBLE</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iminiport-datarangeintersection">IMiniport::DataRangeIntersection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksdataformat">KSDATAFORMAT</a>



<a href="https://docs.microsoft.com/windows/desktop/api/mmreg/ns-mmreg-twaveformatex">WAVEFORMATEX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksmedia/ns-ksmedia-waveformatextensible">WAVEFORMATEXTENSIBLE</a>
 

 

