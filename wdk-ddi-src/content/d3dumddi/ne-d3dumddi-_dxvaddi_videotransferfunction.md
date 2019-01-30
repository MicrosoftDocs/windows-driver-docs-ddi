---
UID: NE:d3dumddi._DXVADDI_VIDEOTRANSFERFUNCTION
title: "_DXVADDI_VIDEOTRANSFERFUNCTION" (d3dumddi.h)
description: The DXVADDI_VIDEOTRANSFERFUNCTION enumeration type contains values that identify the conversion function from R'G'B' to RGB.
old-location: display\dxvaddi_videotransferfunction.htm
tech.root: display
ms.assetid: 8d798afe-dc75-4cd0-aad7-1f9824bdcf00
ms.date: 05/10/2018
ms.keywords: DXVA2_Structs_a6fcb795-da10-4824-99b3-5f75a50a17ce.xml, DXVADDI_VIDEOTRANSFERFUNCTION, DXVADDI_VIDEOTRANSFERFUNCTION enumeration [Display Devices], DXVADDI_VideoTransFuncMask, DXVADDI_VideoTransFunc_10, DXVADDI_VideoTransFunc_18, DXVADDI_VideoTransFunc_20, DXVADDI_VideoTransFunc_22, DXVADDI_VideoTransFunc_240M, DXVADDI_VideoTransFunc_28, DXVADDI_VideoTransFunc_709, DXVADDI_VideoTransFunc_Unknown, DXVADDI_VideoTransFunc_sRGB, _DXVADDI_VIDEOTRANSFERFUNCTION, d3dumddi/DXVADDI_VIDEOTRANSFERFUNCTION, d3dumddi/DXVADDI_VideoTransFuncMask, d3dumddi/DXVADDI_VideoTransFunc_10, d3dumddi/DXVADDI_VideoTransFunc_18, d3dumddi/DXVADDI_VideoTransFunc_20, d3dumddi/DXVADDI_VideoTransFunc_22, d3dumddi/DXVADDI_VideoTransFunc_240M, d3dumddi/DXVADDI_VideoTransFunc_28, d3dumddi/DXVADDI_VideoTransFunc_709, d3dumddi/DXVADDI_VideoTransFunc_Unknown, d3dumddi/DXVADDI_VideoTransFunc_sRGB, display.dxvaddi_videotransferfunction
ms.topic: enum
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
-	DXVADDI_VIDEOTRANSFERFUNCTION
product:
- Windows
targetos: Windows
req.typenames: DXVADDI_VIDEOTRANSFERFUNCTION
---

# _DXVADDI_VIDEOTRANSFERFUNCTION enumeration


## -description


The DXVADDI_VIDEOTRANSFERFUNCTION enumeration type contains values that identify the conversion function from R'G'B' to RGB.


## -enum-fields




### -field DXVADDI_VideoTransFuncMask

Specifies the video transfer function mask. The first 5 (0x001F) bits of a DWORD can be used to specify the video transfer function.


### -field DXVADDI_VideoTransFunc_Unknown

Specifies that the video transfer function is not specified. The default is 22_8bit_sRGB if required for a computation.


### -field DXVADDI_VideoTransFunc_10

Specifies linear RGB conversion (corresponds to gamma = 1.0).


### -field DXVADDI_VideoTransFunc_18

Specifies true 1.8 gamma--that is, L' = pow(L, 1/gamma) for L=0..1.


### -field DXVADDI_VideoTransFunc_20

Specifies true 2.0 gamma--that is, L' = pow(L, 1/gamma) for L=0..1.


### -field DXVADDI_VideoTransFunc_22

Specifies true 2.2 gamma--that is, L' = pow(L, 1/gamma) for L=0..1. 

The BT470-2 SysM primaries (that is, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562951">DXVADDI_VIDEOPRIMARIES</a> enumeration type) use gamma 2.2.


### -field DXVADDI_VideoTransFunc_709

Specifies gamma 2.2 curve with a linear range in the low range. 

The BT709, SMPTE296M, SMPTE170M, BT470, and SMPTE274M primaries (that is, the DXVADDI_VIDEOPRIMARIES enumeration type) use this video transfer function. 


### -field DXVADDI_VideoTransFunc_240M

Specifies gamma 2.2 curve with a linear range in the low range. 

The SMPTE240M and interim 274M primaries (that is, the DXVADDI_VIDEOPRIMARIES enumeration type) use this video transfer function. 


### -field DXVADDI_VideoTransFunc_sRGB

Specifies gamma 2.4 curve with a linear range in the low range, which makes it match an accurate 2.2 gamma 8-bit curve. 


### -field DXVADDI_VideoTransFunc_28

Specifies true 2.8 gamma--that is, L' = pow(L, 1/gamma) for L=0..1.


## -remarks



One of the values of DXVADDI_VIDEOTRANSFERFUNCTION can be specified in the <b>VideoTransferFunction</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562904">DXVADDI_EXTENDEDFORMAT</a> structure.

DXVADDI_VIDEOTRANSFERFUNCTION corresponds to the gamma function of the data. Some transfer functions have corrections to account for 8-bit integer quantization effects.

The following constants can also be used for gamma function:

```cpp
#define DXVADDI_VideoTransFunc_22_709  DXVADDI_VideoTransFunc_709
#define DXVADDI_VideoTransFunc_22_240M  DXVADDI_VideoTransFunc_240M
#define DXVADDI_VideoTransFunc_22_8bit_sRGB  DXVADDI_VideoTransFunc_sRGB
```


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562904">DXVADDI_EXTENDEDFORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562951">DXVADDI_VIDEOPRIMARIES</a>
 

 

