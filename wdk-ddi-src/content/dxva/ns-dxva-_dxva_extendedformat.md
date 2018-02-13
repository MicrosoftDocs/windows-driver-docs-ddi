---
UID: NS:dxva._DXVA_ExtendedFormat
title: "_DXVA_ExtendedFormat"
author: windows-driver-content
description: The DXVA_ExtendedFormat structure describes the extended format of the video frame.
old-location: display\dxva_extendedformat.htm
old-project: display
ms.assetid: b4d01c1f-8267-490e-a808-87d9be666a94
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxva_extendedformat, _DXVA_ExtendedFormat, dxva/DXVA_ExtendedFormat, DXVA_ExtendedFormat, DXVA_ExtendedFormat structure [Display Devices], dxvaref_3e46e283-492a-4ec5-8213-ff05215b0676.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: This structure applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later.
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
-	DXVA_ExtendedFormat
product: Windows
targetos: Windows
req.typenames: DXVA_ExtendedFormat
---

# _DXVA_ExtendedFormat structure


## -description


The DXVA_ExtendedFormat structure describes the extended format of the video frame. 


## -syntax


````
typedef struct _DXVA_ExtendedFormat {
  UINT                       SampleFormat  :8;
  UINT                       VideoChromaSubsampling  :4;
  DXVA_NominalRange          NominalRange  :3;
  DXVA_VideoTransferMatrix   VideoTransferMatrix  :3;
  DXVA_VideoLighting         VideoLighting  :4;
  DXVA_VideoPrimaries        VideoPrimaries  :5;
  DXVA_VideoTransferFunction VideoTransferFunction  :5;
} DXVA_ExtendedFormat;
````


## -struct-fields




### -field SampleFormat

Specifies how a video frame is sampled. The 8 bits are defined by one of the enumerators in the <a href="..\dxva\ne-dxva-_dxva_sampleformat.md">DXVA_SampleFormat</a> enumeration type.


### -field VideoChromaSubsampling

Specifies the chroma encoding scheme for Y'Cb'Cr' data. The 4 bits are defined by an ORed combination of the enumerators in the <a href="..\dxva\ne-dxva-_dxva_videochromasubsampling.md">DXVA_VideoChromaSubsampling</a> enumeration type. 


### -field NominalRange

Specifies whether sample data includes headroom (values beyond 1.0 white) and toeroom (superblacks below the reference 0.0 black). The 3 bits are defined by one of the enumerators in the <a href="..\dxva\ne-dxva-_dxva_nominalrange.md">DXVA_NominalRange</a> enumeration type. 


### -field VideoTransferMatrix

Specifies the conversion matrix from Y'Cb'Cr' to (studio) R'G'B'. The 3 bits are defined by one of the enumerators in the <a href="..\dxva\ne-dxva-_dxva_videotransfermatrix.md">DXVA_VideoTransferMatrix</a> enumeration type. 


### -field VideoLighting

Specifies lighting conditions for viewing video. The 4 bits are defined by one of the enumerators in the <a href="..\dxva\ne-dxva-_dxva_videolighting.md">DXVA_VideoLighting</a> enumeration type. 


### -field VideoPrimaries

Specifies color primaries, which state which RGB basis functions are used. The 5 bits are defined by one of the enumerators in the <a href="..\dxva\ne-dxva-_dxva_videoprimaries.md">DXVA_VideoPrimaries</a> enumeration type. 


### -field VideoTransferFunction

Specifies the conversion function from R'G'B' to RGB. The 5 bits are defined by the <a href="..\dxva\ne-dxva-_dxva_videotransferfunction.md">DXVA_VideoTransferFunction</a> enumeration type. 


## -see-also

<a href="..\dxva\ne-dxva-_dxva_sampleformat.md">DXVA_SampleFormat</a>



<a href="..\dxva\ne-dxva-_dxva_videolighting.md">DXVA_VideoLighting</a>



<a href="..\dxva\ne-dxva-_dxva_nominalrange.md">DXVA_NominalRange</a>



<a href="..\dxva\ne-dxva-_dxva_videochromasubsampling.md">DXVA_VideoChromaSubsampling</a>



<a href="..\dxva\ne-dxva-_dxva_videoprimaries.md">DXVA_VideoPrimaries</a>



<a href="..\dxva\ne-dxva-_dxva_videotransferfunction.md">DXVA_VideoTransferFunction</a>



<a href="..\dxva\ne-dxva-_dxva_videotransfermatrix.md">DXVA_VideoTransferMatrix</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_ExtendedFormat structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

