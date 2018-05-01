---
UID: NS:ksmedia.KSDATAFORMAT_DSOUND
title: KSDATAFORMAT_DSOUND
author: windows-driver-content
description: The KSDATAFORMAT_DSOUND structure provides detailed information about a DirectSound audio stream.
old-location: audio\ksdataformat_dsound.htm
old-project: audio
ms.assetid: 2b620e4f-8c26-479a-8b06-4e558b0813e5
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*PKSDATAFORMAT_DSOUND, KSDATAFORMAT_DSOUND, KSDATAFORMAT_DSOUND structure [Audio Devices], PKSDATAFORMAT_DSOUND, PKSDATAFORMAT_DSOUND structure pointer [Audio Devices], aud-prop_2e782d9c-dfeb-4797-b902-e32e947d2542.xml, audio.ksdataformat_dsound, ksmedia/KSDATAFORMAT_DSOUND, ksmedia/PKSDATAFORMAT_DSOUND"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KSDATAFORMAT_DSOUND
product: Windows
targetos: Windows
req.typenames: KSDATAFORMAT_DSOUND, *PKSDATAFORMAT_DSOUND
---

# KSDATAFORMAT_DSOUND structure


## -description


The KSDATAFORMAT_DSOUND structure provides detailed information about a DirectSound audio stream.


## -struct-fields




### -field DataFormat

Specifies the stream's data format. This member is a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff561656">KSDATAFORMAT</a>.


### -field BufferDesc

Describes the DirectSound buffer. This member is a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff537121">KSDSOUND_BUFFERDESC</a>.


## -remarks



In response to an input <i>DataRange</i> parameter that specifies a DirectSound format (see example in <a href="https://msdn.microsoft.com/cc31eb2d-7421-4748-b14c-f4d3d15f9884">DirectSound Stream Data Range</a>), the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536764">IMiniport::DataRangeIntersection</a> method checks to see if the specified pin supports a compatible DirectSound format. If so, the method outputs a KSDATAFORMAT_DSOUND structure (see example in <a href="https://msdn.microsoft.com/41d3d5ad-7336-4ecf-b6e2-a24ee4ec731f">DirectSound Stream Data Format</a>) to the buffer that its <i>ResultantFormat</i> parameter points to.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536764">IMiniport::DataRangeIntersection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561656">KSDATAFORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537121">KSDSOUND_BUFFERDESC</a>
 

 

