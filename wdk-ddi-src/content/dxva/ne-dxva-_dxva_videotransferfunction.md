---
UID: NE:dxva._DXVA_VideoTransferFunction
title: "_DXVA_VideoTransferFunction"
author: windows-driver-content
description: The DXVA_VideoTransferFunction enumeration type contains enumerators that identify the conversion function from R'G'B' to RGB.
old-location: display\dxva_videotransferfunction.htm
old-project: display
ms.assetid: 2ed04fd0-685d-4b5a-a23f-337a14506f8b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXVA_VideoTransFunc_18, dxva/DXVA_VideoTransFuncMask, DXVA_VideoTransferFunction, DXVA_VideoTransFuncShift, DXVA_VideoTransferFunction enumeration [Display Devices], _DXVA_VideoTransferFunction, DXVA_VideoTransFunc_Unknown, dxva/DXVA_VideoTransFunc_22_709, DXVA_VideoTransFunc_22_240M, dxva/DXVA_VideoTransFunc_20, dxva/DXVA_VideoTransFunc_28, dxvaref_67be6e0a-79c6-4821-b3c3-899c2a2f9234.xml, dxva/DXVA_VideoTransFunc_10, dxva/DXVA_VideoTransFunc_22_8bit_sRGB, dxva/DXVA_VideoTransFunc_Unknown, DXVA_VideoTransFunc_22_8bit_sRGB, DXVA_VideoTransFunc_28, dxva/DXVA_VideoTransFunc_22_240M, dxva/DXVA_VideoTransFunc_22, DXVA_VideoTransFunc_20, dxva/DXVA_VideoTransFuncShift, DXVA_VideoTransFuncMask, DXVA_VideoTransFunc_10, display.dxva_videotransferfunction, DXVA_VideoTransFunc_22_709, dxva/DXVA_VideoTransferFunction, DXVA_VideoTransFunc_22, dxva/DXVA_VideoTransFunc_18
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: This enumeration type applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later.
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
-	DXVA_VideoTransferFunction
product: Windows
targetos: Windows
req.typenames: DXVA_VideoTransferFunction
---

# _DXVA_VideoTransferFunction enumeration


## -description


The DXVA_VideoTransferFunction enumeration type contains enumerators that identify the conversion function from R'G'B' to RGB.


## -syntax


````
typedef enum _DXVA_VideoTransferFunction { 
  DXVA_VideoTransFuncShift          = (DXVA_ExtColorData_ShiftBase + 19),
  DXVA_VideoTransFuncMask           = DXVAColorMask(5, DXVA_VideoTransFuncShift),
  DXVA_VideoTransFunc_Unknown       = 0,
  DXVA_VideoTransFunc_10            = 1,
  DXVA_VideoTransFunc_18            = 2,
  DXVA_VideoTransFunc_20            = 3,
  DXVA_VideoTransFunc_22            = 4,
  DXVA_VideoTransFunc_22_709        = 5,
  DXVA_VideoTransFunc_22_240M       = 6,
  DXVA_VideoTransFunc_22_8bit_sRGB  = 7,
  DXVA_VideoTransFunc_28            = 8
} DXVA_VideoTransferFunction;
````


## -enum-fields




#### - DXVA_VideoTransFuncShift

Specifies to shift bits by 27 positions (DXVA_ExtColorData_ShiftBase + 19, or 8 + 19).


#### - DXVA_VideoTransFuncMask

Specifies the video transfer function mask. 5 (0xF8000000) bits of a DWORD can be used to specify the video transfer function.


#### - DXVA_VideoTransFunc_Unknown

Specifies that the video transfer function is not specified. The default is 22_8bit_sRGB if required for a computation.


#### - DXVA_VideoTransFunc_10

Specifies linear RGB conversion (corresponds to gamma = 1.0).


#### - DXVA_VideoTransFunc_18

Specifies true 1.8 gamma. That is, L' = pow(L, 1/gamma) for L=0..1.


#### - DXVA_VideoTransFunc_20

Specifies true 2.0 gamma. That is, L' = pow(L, 1/gamma) for L=0..1.


#### - DXVA_VideoTransFunc_22



#### 



#### 



#### - DXVA_VideoTransFunc_22_709



#### 



#### 



#### - DXVA_VideoTransFunc_22_240M



#### 



#### 



#### - DXVA_VideoTransFunc_22_8bit_sRGB

Specifies gamma 2.4 curve with a linear range in the low range, which makes it match an accurate 2.2 gamma 8 bit curve. 


#### - DXVA_VideoTransFunc_28

Specifies true 2.8 gamma. That is, L' = pow(L, 1/gamma) for L=0..1.


## -remarks


One of the enumerators of DXVA_VideoTransferFunction can be specified in the <b>VideoTransferFunction</b> member of the <a href="..\dxva\ns-dxva-_dxva_extendedformat.md">DXVA_ExtendedFormat</a> structure.

DXVA_VideoTransferFunction corresponds to the gamma function of the data. Some transfer functions have corrections to account for 8 bit integer quantization effects.



## -see-also

<a href="..\dxva\ns-dxva-_dxva_extendedformat.md">DXVA_ExtendedFormat</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_VideoTransferFunction enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

