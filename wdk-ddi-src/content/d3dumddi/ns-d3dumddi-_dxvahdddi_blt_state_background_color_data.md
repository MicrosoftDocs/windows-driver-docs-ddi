---
UID: NS:d3dumddi._DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA
title: _DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA (d3dumddi.h)
description: The DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA structure describes data that specifies the background color to fill in the target rectangle of the output.
old-location: display\dxvahdddi_blt_state_background_color_data.htm
tech.root: display
ms.assetid: 23eaa88a-a3c3-4630-92b0-d76b266a9c45
ms.date: 05/10/2018
ms.keywords: DXVA2_Structs_d4f86ea1-cbdd-48ab-84ca-1bc64ba4c8db.xml, DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA, DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA structure [Display Devices], _DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA, d3dumddi/DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA, display.dxvahdddi_blt_state_background_color_data
ms.topic: struct
f1_keywords:
 - "d3dumddi/DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA is supported beginning with the Windows 7 operating system.
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
- d3dumddi.h
api_name:
- DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA
product:
- Windows
targetos: Windows
req.typenames: DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA
---

# _DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA structure


## -description


The DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA structure describes data that specifies the background color to fill in the target rectangle of the output. 


## -struct-fields




### -field YCbCr

[in] A Boolean value that specifies whether the driver should determine whether the <b>BackgroundColor</b> member specifies a YCbCr or RGB color space. The default value is <b>FALSE</b>, which indicates a RGB color space. <b>TRUE</b> specifies a YCbCr color space. 


### -field BackgroundColor

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvahdddi_color">DXVAHDDDI_COLOR</a> union that specifies the background color as either a YCbCr or RGB color space. The default value is full range RGB black with opaque alpha, that is (R,G,B,A) = (0.0,0.0,0.0,1.0). 


## -remarks



The color space of the background color is determined by the color space of the output. For more information about output color space, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvahdddi_blt_state_output_color_space_data">DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE_DATA</a>. 

The alpha value of the background color is used when the DXVAHDDDI_ALPHA_FILL_MODE_BACKGROUND value is specified in the alpha fill mode (that is, the <b>Mode</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvahdddi_blt_state_alpha_fill_data">DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA</a> structure) when the DXVAHDDDI_BLT_STATE_ALPHA_FILL value is specified in the <b>State</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_dxvahd_setvideoprocessbltstate">D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE</a> structure in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessbltstate">SetVideoProcessBltState</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_dxvahd_setvideoprocessbltstate">D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvahdddi_blt_state_alpha_fill_data">DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvahdddi_blt_state_output_color_space_data">DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvahdddi_color">DXVAHDDDI_COLOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessbltstate">SetVideoProcessBltState</a>
 

 

