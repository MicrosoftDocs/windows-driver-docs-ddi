---
UID: NS:dxva._DXVA_ExtendedFormat
title: _DXVA_ExtendedFormat (dxva.h)
description: The DXVA_ExtendedFormat structure describes the extended format of the video frame.
old-location: display\dxva_extendedformat.htm
tech.root: display
ms.assetid: b4d01c1f-8267-490e-a808-87d9be666a94
ms.date: 05/10/2018
ms.keywords: DXVA_ExtendedFormat, DXVA_ExtendedFormat structure [Display Devices], _DXVA_ExtendedFormat, display.dxva_extendedformat, dxva/DXVA_ExtendedFormat, dxvaref_3e46e283-492a-4ec5-8213-ff05215b0676.xml
f1_keywords:
 - "dxva/DXVA_ExtendedFormat"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- dxva.h
api_name:
- DXVA_ExtendedFormat
product:
- Windows
targetos: Windows
req.typenames: DXVA_ExtendedFormat
---

# _DXVA_ExtendedFormat structure


## -description


The DXVA_ExtendedFormat structure describes the extended format of the video frame. 


## -struct-fields




### -field SampleFormat

Specifies how a video frame is sampled. The 8 bits are defined by one of the enumerators in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ne-dxva-_dxva_sampleformat">DXVA_SampleFormat</a> enumeration type.


### -field VideoChromaSubsampling

Specifies the chroma encoding scheme for Y'Cb'Cr' data. The 4 bits are defined by an ORed combination of the enumerators in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ne-dxva-_dxva_videochromasubsampling">DXVA_VideoChromaSubsampling</a> enumeration type. 


### -field NominalRange

Specifies whether sample data includes headroom (values beyond 1.0 white) and toeroom (superblacks below the reference 0.0 black). The 3 bits are defined by one of the enumerators in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ne-dxva-_dxva_nominalrange">DXVA_NominalRange</a> enumeration type. 


### -field VideoTransferMatrix

Specifies the conversion matrix from Y'Cb'Cr' to (studio) R'G'B'. The 3 bits are defined by one of the enumerators in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ne-dxva-_dxva_videotransfermatrix">DXVA_VideoTransferMatrix</a> enumeration type. 


### -field VideoLighting

Specifies lighting conditions for viewing video. The 4 bits are defined by one of the enumerators in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ne-dxva-_dxva_videolighting">DXVA_VideoLighting</a> enumeration type. 


### -field VideoPrimaries

Specifies color primaries, which state which RGB basis functions are used. The 5 bits are defined by one of the enumerators in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ne-dxva-_dxva_videoprimaries">DXVA_VideoPrimaries</a> enumeration type. 


### -field VideoTransferFunction

Specifies the conversion function from R'G'B' to RGB. The 5 bits are defined by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ne-dxva-_dxva_videotransferfunction">DXVA_VideoTransferFunction</a> enumeration type. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ne-dxva-_dxva_nominalrange">DXVA_NominalRange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ne-dxva-_dxva_sampleformat">DXVA_SampleFormat</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ne-dxva-_dxva_videochromasubsampling">DXVA_VideoChromaSubsampling</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ne-dxva-_dxva_videolighting">DXVA_VideoLighting</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ne-dxva-_dxva_videoprimaries">DXVA_VideoPrimaries</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ne-dxva-_dxva_videotransferfunction">DXVA_VideoTransferFunction</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ne-dxva-_dxva_videotransfermatrix">DXVA_VideoTransferMatrix</a>
 

 

