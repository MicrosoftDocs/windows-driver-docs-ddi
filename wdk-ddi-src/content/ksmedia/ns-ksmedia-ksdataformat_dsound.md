---
UID: NS:ksmedia.KSDATAFORMAT_DSOUND
title: KSDATAFORMAT_DSOUND
author: windows-driver-content
description: The KSDATAFORMAT_DSOUND structure provides detailed information about a DirectSound audio stream.
old-location: audio\ksdataformat_dsound.htm
old-project: audio
ms.assetid: 2b620e4f-8c26-479a-8b06-4e558b0813e5
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: ksmedia/KSDATAFORMAT_DSOUND, KSDATAFORMAT_DSOUND, PKSDATAFORMAT_DSOUND, PKSDATAFORMAT_DSOUND structure pointer [Audio Devices], aud-prop_2e782d9c-dfeb-4797-b902-e32e947d2542.xml, ksmedia/PKSDATAFORMAT_DSOUND, *PKSDATAFORMAT_DSOUND, KSDATAFORMAT_DSOUND structure [Audio Devices], audio.ksdataformat_dsound
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
-	KSDATAFORMAT_DSOUND
product: Windows
targetos: Windows
req.typenames: KSDATAFORMAT_DSOUND, *PKSDATAFORMAT_DSOUND
---

# KSDATAFORMAT_DSOUND structure


## -description


The KSDATAFORMAT_DSOUND structure provides detailed information about a DirectSound audio stream.


## -syntax


````
typedef struct {
  KSDATAFORMAT        DataFormat;
  KSDSOUND_BUFFERDESC BufferDesc;
} KSDATAFORMAT_DSOUND, *PKSDATAFORMAT_DSOUND;
````


## -struct-fields




### -field DataFormat

Specifies the stream's data format. This member is a structure of type <a href="..\ks\ns-ks-ksdataformat.md">KSDATAFORMAT</a>.


### -field BufferDesc

Describes the DirectSound buffer. This member is a structure of type <a href="..\ksmedia\ns-ksmedia-ksdsound_bufferdesc.md">KSDSOUND_BUFFERDESC</a>.


## -remarks



In response to an input <i>DataRange</i> parameter that specifies a DirectSound format (see example in <a href="https://msdn.microsoft.com/cc31eb2d-7421-4748-b14c-f4d3d15f9884">DirectSound Stream Data Range</a>), the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536764">IMiniport::DataRangeIntersection</a> method checks to see if the specified pin supports a compatible DirectSound format. If so, the method outputs a KSDATAFORMAT_DSOUND structure (see example in <a href="https://msdn.microsoft.com/41d3d5ad-7336-4ecf-b6e2-a24ee4ec731f">DirectSound Stream Data Format</a>) to the buffer that its <i>ResultantFormat</i> parameter points to.




## -see-also

<a href="..\ksmedia\ns-ksmedia-ksdsound_bufferdesc.md">KSDSOUND_BUFFERDESC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536764">IMiniport::DataRangeIntersection</a>



<a href="..\ks\ns-ks-ksdataformat.md">KSDATAFORMAT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSDATAFORMAT_DSOUND structure%20 RELEASE:%20(2/21/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

