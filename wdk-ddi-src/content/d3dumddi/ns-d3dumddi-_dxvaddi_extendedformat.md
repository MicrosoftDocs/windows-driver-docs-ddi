---
UID: NS:d3dumddi._DXVADDI_EXTENDEDFORMAT
title: "_DXVADDI_EXTENDEDFORMAT"
author: windows-driver-content
description: The DXVADDI_EXTENDEDFORMAT structure describes the extended format of the video frame.
old-location: display\dxvaddi_extendedformat.htm
old-project: display
ms.assetid: e4f863bd-12ec-489d-a6e0-6b9242fbb0b0
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXVA2_Structs_31dd9223-b889-4db9-acc0-520c8f16410a.xml, DXVADDI_EXTENDEDFORMAT, DXVADDI_EXTENDEDFORMAT structure [Display Devices], _DXVADDI_EXTENDEDFORMAT, d3dumddi/DXVADDI_EXTENDEDFORMAT, display.dxvaddi_extendedformat
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	d3dumddi.h
api_name:
-	DXVADDI_EXTENDEDFORMAT
product: Windows
targetos: Windows
req.typenames: DXVADDI_EXTENDEDFORMAT
---

# _DXVADDI_EXTENDEDFORMAT structure


## -description


The DXVADDI_EXTENDEDFORMAT structure describes the extended format of the video frame. 


## -struct-fields




### -field SampleFormat

[in] A UINT value that specifies how a video frame is sampled. The eight bits are defined by one of the values in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562937">DXVADDI_SAMPLEFORMAT</a> enumeration type.


### -field VideoChromaSubsampling

[in] The chroma encoding scheme for Y'Cb'Cr' data. The four bits are defined by a bitwise OR of the values in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562943">DXVADDI_VIDEOCHROMASUBSAMPLING</a> enumeration type. 


### -field NominalRange

[in] A UINT value that specifies whether sample data includes headroom (that is, values beyond 1.0 white) and toeroom (that is, superblacks below the reference 0.0 black). The three bits are defined by one of the values in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562912">DXVADDI_NOMINALRANGE</a> enumeration type. 


### -field VideoTransferMatrix

[in] The conversion matrix from Y'Cb'Cr' to (studio) R'G'B'. The three bits are defined by one of the values in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562970">DXVADDI_VIDEOTRANSFERMATRIX</a> enumeration type. 


### -field VideoLighting

[in] Lighting conditions for viewing video. The four bits are defined by one of the values in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562947">DXVADDI_VIDEOLIGHTING</a> enumeration type. 


### -field VideoPrimaries

[in] Color primaries, which state which RGB basis functions are used. The five bits are defined by one of the values in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562951">DXVADDI_VIDEOPRIMARIES</a> enumeration type. 


### -field VideoTransferFunction

[in] The conversion function from R'G'B' to RGB. The five bits are defined by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562962">DXVADDI_VIDEOTRANSFERFUNCTION</a> enumeration type. 


#### - Value

A 32-bit value that describes the extended format of the video frame.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562944">DXVADDI_VIDEODESC</a>
 

 

