---
UID: NS:d3dumddi._DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA
title: _DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA (d3dumddi.h)
description: The DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA structure describes stream-state data that specifies the output rate of the input stream.
old-location: display\dxvahdddi_stream_state_output_rate_data.htm
tech.root: display
ms.assetid: 97523719-d22a-4390-ac4a-6240f24144bf
ms.date: 05/10/2018
ms.keywords: DXVA2_Structs_32dedbf1-1052-4765-a0dd-4f536389dbb6.xml, DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA, DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA structure [Display Devices], _DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA, d3dumddi/DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA, display.dxvahdddi_stream_state_output_rate_data
f1_keywords:
 - "d3dumddi/DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA is supported beginning with the Windows 7 operating system.
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
- DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA
product:
- Windows
targetos: Windows
req.typenames: DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA
---

# _DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA structure


## -description


The DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA structure describes stream-state data that specifies the output rate of the input stream. 


## -struct-fields




### -field RepeatFrame

[in] A Boolean value that specifies whether the frame rate conversion repeats or interpolates the frames. The driver refers to <b>RepeatFrame</b> only when it uses the frame rate conversion. The default value is <b>FALSE</b>, which indicates that the frame rate conversion interpolates the frames. 


### -field OutputRate

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-_dxvahdddi_output_rate">DXVAHDDDI_OUTPUT_RATE</a>-typed value that indicates the output rate of the input stream. The default value is DXVAHDDDI_OUTPUT_RATE_NORMAL. 


### -field CustomRate

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_rational">DXVAHDDDI_RATIONAL</a> structure that specifies a fractional value that represents a custom output rate. The driver refers to <b>CustomRate</b> only when the value that is specified in <b>OutputRate</b> is DXVAHDDDI_OUTPUT_RATE_CUSTOM. The default value is 1/1. 


## -remarks



The driver uses the <b>RepeatFrame</b> member to control the frame rate conversion. For example, when the driver converts from 60i to 60p, if the video processor is capable of both the inverse telecine (60i to 24p) and the frame rate conversion (24p to 60p), then the converted frames contains interpolated frames. Sometimes the interpolation results in artifacts, and the application might require to repeat the frames instead.

The <b>CustomRate</b> member must specify one of the custom rates that the driver supplied in the members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_custom_rate_data">DXVAHDDDI_CUSTOM_RATE_DATA</a> structure when the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a> function was called with the D3DDDICAPS_DXVAHD_GETVPCUSTOMRATES value set; otherwise, the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessstreamstate">SetVideoProcessStreamState</a> function returns an error.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_custom_rate_data">DXVAHDDDI_CUSTOM_RATE_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-_dxvahdddi_output_rate">DXVAHDDDI_OUTPUT_RATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_rational">DXVAHDDDI_RATIONAL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessstreamstate">SetVideoProcessStreamState</a>
 

 

