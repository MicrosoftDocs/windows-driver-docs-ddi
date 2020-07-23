---
UID: NS:ksmedia.__unnamed_struct_6
title: KSDATAFORMAT_DSOUND (ksmedia.h)
description: The KSDATAFORMAT_DSOUND structure provides detailed information about a DirectSound audio stream.
old-location: audio\ksdataformat_dsound.htm
tech.root: audio
ms.assetid: 2b620e4f-8c26-479a-8b06-4e558b0813e5
ms.date: 05/08/2018
keywords: ["KSDATAFORMAT_DSOUND structure"]
ms.keywords: "*PKSDATAFORMAT_DSOUND, KSDATAFORMAT_DSOUND, KSDATAFORMAT_DSOUND structure [Audio Devices], PKSDATAFORMAT_DSOUND, PKSDATAFORMAT_DSOUND structure pointer [Audio Devices], aud-prop_2e782d9c-dfeb-4797-b902-e32e947d2542.xml, audio.ksdataformat_dsound, ksmedia/KSDATAFORMAT_DSOUND, ksmedia/PKSDATAFORMAT_DSOUND"
f1_keywords:
 - "ksmedia/KSDATAFORMAT_DSOUND"
 - "KSDATAFORMAT_DSOUND"
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
- KSDATAFORMAT_DSOUND
targetos: Windows
req.typenames: KSDATAFORMAT_DSOUND, *PKSDATAFORMAT_DSOUND
---

# KSDATAFORMAT_DSOUND structure


## -description


The KSDATAFORMAT_DSOUND structure provides detailed information about a DirectSound audio stream.


## -struct-fields




### -field DataFormat

Specifies the stream's data format. This member is a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksdataformat">KSDATAFORMAT</a>.


### -field BufferDesc

Describes the DirectSound buffer. This member is a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksdsound_bufferdesc">KSDSOUND_BUFFERDESC</a>.


## -remarks



In response to an input <i>DataRange</i> parameter that specifies a DirectSound format (see example in <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/directsound-stream-data-range">DirectSound Stream Data Range</a>), the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiport-datarangeintersection">IMiniport::DataRangeIntersection</a> method checks to see if the specified pin supports a compatible DirectSound format. If so, the method outputs a KSDATAFORMAT_DSOUND structure (see example in <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/directsound-stream-data-format">DirectSound Stream Data Format</a>) to the buffer that its <i>ResultantFormat</i> parameter points to.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiport-datarangeintersection">IMiniport::DataRangeIntersection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksdataformat">KSDATAFORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksdsound_bufferdesc">KSDSOUND_BUFFERDESC</a>
 

 

