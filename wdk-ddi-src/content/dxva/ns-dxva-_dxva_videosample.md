---
UID: NS:dxva._DXVA_VideoSample
title: "_DXVA_VideoSample"
author: windows-driver-content
description: The DXVA_VideoSample structure is sent by the renderer to the driver to specify the format of a video sample.
old-location: display\dxva_videosample.htm
old-project: display
ms.assetid: 2fab4993-0b34-44ce-a905-5094e6e3ce47
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: dxvaref_08c56205-0793-4556-bb9a-e682eb6ca354.xml, DXVA_VideoSample, DXVA_VideoSample structure [Display Devices], dxva/DXVA_VideoSample, LPDXVA_VideoSample, LPDXVA_VideoSample structure pointer [Display Devices], _DXVA_VideoSample, display.dxva_videosample, *LPDXVA_VideoSample, dxva/LPDXVA_VideoSample
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxva.h
req.include-header: Dxva.h
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
-	dxva.h
apiname:
-	DXVA_VideoSample
product: Windows
targetos: Windows
req.typenames: "*LPDXVA_VideoSample, DXVA_VideoSample"
---

# _DXVA_VideoSample structure


## -description


The DXVA_VideoSample structure is sent by the renderer to the driver to specify the format of a video sample.


## -syntax


````
typedef struct _DXVA_VideoSample {
  REFERENCE_TIME    rtStart;
  REFERENCE_TIME    rtEnd;
  DXVA_SampleFormat SampleFormat;
  VOID              *lpDDSSrcSurface;
} DXVA_VideoSample, *LPDXVA_VideoSample;
````


## -struct-fields




### -field rtStart

Specifies the start time of the sample.


### -field rtEnd

Specifies the end time of the sample.


### -field SampleFormat

Specifies the format of the sample as defined by a <a href="..\dxva\ne-dxva-_dxva_sampleformat.md">DXVA_SampleFormat</a> structure.


### -field lpDDSSrcSurface

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551733">DD_SURFACE_LOCAL</a> structure.


## -see-also

<a href="..\dxva\ne-dxva-_dxva_sampleformat.md">DXVA_SampleFormat</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551733">DD_SURFACE_LOCAL</a>



<a href="..\dxva\ns-dxva-_dxva_deinterlaceblt.md">DXVA_DeinterlaceBlt</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_VideoSample structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

