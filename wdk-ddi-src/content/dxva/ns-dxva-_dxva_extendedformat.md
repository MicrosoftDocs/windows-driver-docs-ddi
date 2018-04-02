---
UID: NS:dxva._DXVA_ExtendedFormat
title: "_DXVA_ExtendedFormat"
author: windows-driver-content
description: The DXVA_ExtendedFormat structure describes the extended format of the video frame.
old-location: display\dxva_extendedformat.htm
old-project: display
ms.assetid: b4d01c1f-8267-490e-a808-87d9be666a94
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXVA_ExtendedFormat, DXVA_ExtendedFormat structure [Display Devices], _DXVA_ExtendedFormat, display.dxva_extendedformat, dxva/DXVA_ExtendedFormat, dxvaref_3e46e283-492a-4ec5-8213-ff05215b0676.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	dxva.h
api_name:
-	DXVA_ExtendedFormat
product: Windows
targetos: Windows
req.typenames: DXVA_ExtendedFormat
---

# _DXVA_ExtendedFormat structure


## -description


The DXVA_ExtendedFormat structure describes the extended format of the video frame. 


## -struct-fields




### -field SampleFormat

Specifies how a video frame is sampled. The 8 bits are defined by one of the enumerators in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564045">DXVA_SampleFormat</a> enumeration type.


### -field VideoChromaSubsampling

Specifies the chroma encoding scheme for Y'Cb'Cr' data. The 4 bits are defined by an ORed combination of the enumerators in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564067">DXVA_VideoChromaSubsampling</a> enumeration type. 


### -field NominalRange

Specifies whether sample data includes headroom (values beyond 1.0 white) and toeroom (superblacks below the reference 0.0 black). The 3 bits are defined by one of the enumerators in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564006">DXVA_NominalRange</a> enumeration type. 


### -field VideoTransferMatrix

Specifies the conversion matrix from Y'Cb'Cr' to (studio) R'G'B'. The 3 bits are defined by one of the enumerators in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564108">DXVA_VideoTransferMatrix</a> enumeration type. 


### -field VideoLighting

Specifies lighting conditions for viewing video. The 4 bits are defined by one of the enumerators in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564071">DXVA_VideoLighting</a> enumeration type. 


### -field VideoPrimaries

Specifies color primaries, which state which RGB basis functions are used. The 5 bits are defined by one of the enumerators in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564073">DXVA_VideoPrimaries</a> enumeration type. 


### -field VideoTransferFunction

Specifies the conversion function from R'G'B' to RGB. The 5 bits are defined by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564105">DXVA_VideoTransferFunction</a> enumeration type. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564006">DXVA_NominalRange</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564045">DXVA_SampleFormat</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564067">DXVA_VideoChromaSubsampling</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564071">DXVA_VideoLighting</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564073">DXVA_VideoPrimaries</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564105">DXVA_VideoTransferFunction</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564108">DXVA_VideoTransferMatrix</a>
 

 

