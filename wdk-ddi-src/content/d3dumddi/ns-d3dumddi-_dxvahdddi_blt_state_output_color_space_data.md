---
UID: NS:d3dumddi._DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE_DATA
title: "_DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE_DATA"
author: windows-driver-content
description: The DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE_DATA structure describes data that specifies the color space of the output.
old-location: display\dxvahdddi_blt_state_output_color_space_data.htm
tech.root: display
ms.assetid: 411246a5-9486-4194-9fb1-4ec0ba1dd47b
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DXVA2_Structs_87da73df-e65e-4c01-8294-1201215a8d7c.xml, DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE_DATA, DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE_DATA structure [Display Devices], _DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE_DATA, d3dumddi/DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE_DATA, display.dxvahdddi_blt_state_output_color_space_data
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE_DATA is supported beginning with the Windows 7 operating system.
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
-	DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE_DATA
product:
- Windows
targetos: Windows
req.typenames: DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE_DATA
---

# _DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE_DATA structure


## -description


The DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE_DATA structure describes data that specifies the color space of the output. 


## -struct-fields




### -field Usage

[in] A UINT value that specifies whether the decode device should perform video playback (for example, presenting to the screen) or video processing (for example, video editing or authoring). The driver can perform the optimal color conversion based on the output device context. The default value is zero, which indicates video playback.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001). 


### -field RGB_Range

[in] A UINT value that specifies whether the output is full range RGB (that is, 0 to 255) or limited range RGB (that is, 16 to 235). The default value is zero, which indicates full range RGB.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002). 


### -field YCbCr_Matrix

[in] A UINT value that specifies whether the output is BT.601 (for standard digital television) or BT.709 (for high-definition television). The default value is zero, which indicates BT.601. 

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).


### -field YCbCr_xvYCC

[in] A UINT value that specifies whether the output is conventional YCbCr or extended YCbCr (xvYCC). The default is zero, which indicates conventional YCbCr. 

Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).


### -field Nominal_Range

[in] A UINT value that specifies that the luminance range of YUV data is described by the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265432">DXVAHDDDI_NOMINAL_RANGE</a> enumeration. The default is zero, which indicates the studio luminance range of 16 to 255, inclusive [16, 235].

For more information on luminance range, see <a href="https://msdn.microsoft.com/D76FFB8C-CA42-446E-826F-52982B1849E5">YUV format ranges in Windows 8.1</a>.

Setting this member is equivalent to setting the fifth and sixth bits of the 32-bit <b>Value</b> member (0x00000030).

Supported starting with Windows 8.1.


### -field Reserved

[in] Reserved. Must be zero.

This member is equivalent to the remaining 26 bits (0xFFFFFFC0) of the 32-bit <b>Value</b> member.


### -field Value

[in] A 32-bit value that describes the color space of the output. 


## -remarks



If the driver does not set the DXVAHDDDI_DEVICE_CAPS_xvYCC value in the <b>DeviceCaps</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563113">DXVAHDDDI_VPDEVCAPS</a> structure when the driver's <a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a> function is called with the D3DDDICAPS_DXVAHD_GETVPDEVCAPS value set, the output ignores the <b>YCbCr_xvYCC</b> member.

Either RGB or YCbCr flags that correspond to the color space of the output format are referred. However, the driver might have to perform the color space conversion to the background color, in which case both RGB and YCbCr flags are referred.

An application should set the <b>Usage</b> member such that the driver can perform the optimal color conversion. If usage is set to video playback (<b>Usage</b>=0), the driver can use a sophisticated algorism to maximize the presentation experience (for example, auto gain control or dynamic gamma mapping is used to maximize the dynamic range while the super white is preserved). If the usage is set to video processing (<b>Usage</b>=1), the driver should accept the values that are set in the other members of DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE_DATA and perform the conversion exactly as specified in the other members.

RGB output can be out of [0.0, 1.0] range ([0, 255], when 8-bit presentation is used) in the event that the output RGB type is a wide range format (for example, XR_BIAS, FP16, or FP32 format). Especially when the input stream is extended YCbCr (xvYCC), the RGB output range becomes wider than sRGB color space.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265432">DXVAHDDDI_NOMINAL_RANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563113">DXVAHDDDI_VPDEVCAPS</a>



<a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a>
 

 

