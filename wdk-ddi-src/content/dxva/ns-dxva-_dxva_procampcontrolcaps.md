---
UID: NS:dxva._DXVA_ProcAmpControlCaps
title: "_DXVA_ProcAmpControlCaps"
author: windows-driver-content
description: The DXVA_ProcAmpControlCaps structure identifies the ProcAmp operations that the hardware supports.
old-location: display\dxva_procampcontrolcaps.htm
tech.root: display
ms.assetid: 93de54dc-8826-4b1c-acf7-1861f337318a
ms.date: 05/10/2018
ms.keywords: "*LPDXVA_ProcAmpControlCaps, DXVA_ProcAmpControlCaps, DXVA_ProcAmpControlCaps structure [Display Devices], LPDXVA_ProcAmpControlCaps, LPDXVA_ProcAmpControlCaps structure pointer [Display Devices], _DXVA_ProcAmpControlCaps, display.dxva_procampcontrolcaps, dxva/DXVA_ProcAmpControlCaps, dxva/LPDXVA_ProcAmpControlCaps, dxvaref_7641df03-ca9f-462a-b6b8-bddd7c8a14b7.xml"
ms.topic: struct
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: DirectX 9.0 and later versions only.
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
-	DXVA_ProcAmpControlCaps
product:
- Windows
targetos: Windows
req.typenames: DXVA_ProcAmpControlCaps, *LPDXVA_ProcAmpControlCaps
---

# _DXVA_ProcAmpControlCaps structure


## -description


The DXVA_ProcAmpControlCaps structure identifies the ProcAmp operations that the hardware supports.


## -struct-fields

### -field Size

Specifies the size of this structure in bytes.

### -field InputPool

Indicates the memory pool from which the ProcAmp control source surfaces should be allocated. For more information, see the D3DPOOL enumeration in the Microsoft Window SDK documentation.

### -field d3dOutputFormat

Indicates the Direct3D surface format of the output frames. Usually the ProcAmp device outputs frames in a surface format that matches the input surface format. This member ensures that the <a href="https://msdn.microsoft.com/a1de1905-09f3-4689-ace9-06690a1f930a">VMR</a> or other video renderer is able to supply the correct format for the output frame surfaces to the ProcAmp control hardware. If the <b>DXVA_VideoProcess_YUV2RGB</b> flag is returned in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564076">DXVA_VideoProcessCaps</a> structure, the VMR assumes that valid output formats are specified by this member as well as the RGB32 format.


### -field ProcAmpControlProps

Identifies the ProcAmp operations that the hardware supports. The driver should return a logical combination of the following ProcAmp operations.

|Value|Description|
|--- |--- |
|DXVA_ProcAmp_None|No operations are allowed.|
|DXVA_ProcAmp_Brightness|Brightness adjustments to the video image are allowed.|
|DXVA_ProcAmp_Contrast|Contrast adjustments to the video image are allowed.|
|DXVA_ProcAmp_Hue|Hue adjustments to the video image are allowed.|
|DXVA_ProcAmp_Saturation|Saturation adjustments to the video image are allowed.|

### -field VideoProcessingCaps

Identifies the operations that can be performed by the ProcAmp control hardware concurrently with the requested ProcAmp adjustment. The driver should return a logical combination of one of the following ProcAmp operations.

|Value|Description|
|--- |--- |
|DXVA_VideoProcess_None|No operations are allowed.|
|DXVA_VideoProcess_YUV2RGB|Video conversion from the YUV color space to the RGB color space is allowed. The RGB format used will have at least 8 bits of precision for each color component. If this is possible, a buffer copy within the VMR can be avoided. Note that there is no requirement to convert from the RGB color space to the YUV color space.|
|DXVA_VideoProcess_StretchX|Aspect ratio correction can be performed at the same time as the video is being ProcAmp-adjusted if the hardware is able to stretch or shrink horizontally.|
|DXVA_VideoProcess_StretchY|Aspect ratio adjustment is combined with a general picture resizing operation to scale the video image within an application-defined composition space. This is rare and not an essential feature. It is best if the scaling needed for resizing the video to fit into the application window can be done at the same time as the scaling needed for ProcAmp adjustment. This avoids cumulative artifacts.|
|DXVA_VideoProcess_AlphaBlend|Indicates that the VMR will not perform a buffer copy when an alpha value is changed. It is rare that applications alter the constant alpha value associated with the video stream, so this is a low priority feature.|

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564027">DXVA_ProcAmpControlProp</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564076">DXVA_VideoProcessCaps</a>
 

 

