---
UID: NS:d3dumddi._DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA
title: _DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA (d3dumddi.h)
description: The DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA structure describes data that specifies the frame format of the input.
old-location: display\dxvahdddi_stream_state_frame_format_data.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA structure"]
ms.keywords: DXVA2_Structs_5dd1d1dc-aadc-4772-888e-f16eac3dd935.xml, DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA, DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA structure [Display Devices], _DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA, d3dumddi/DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA, display.dxvahdddi_stream_state_frame_format_data
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA is supported beginning with the Windows 7 operating system.
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
targetos: Windows
req.typenames: DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA
f1_keywords:
 - _DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA
 - d3dumddi/_DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA
 - DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA
 - d3dumddi/DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA
 - DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA
---

# _DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA structure


## -description

The DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA structure describes data that specifies the frame format of the input.

## -struct-fields

### -field FrameFormat

[in] A <a href="/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-_dxvahdddi_frame_format">DXVAHDDDI_FRAME_FORMAT</a>-typed value that indicates the frame format of the input stream. The default value is DXVAHDDDI_FRAME_FORMAT_PROGRESSIVE, which indicates progressive format.

## -remarks

The Direct3D runtime specifies the DXVAHDDDI_STREAM_STATE_FRAME_FORMAT state in the <b>State</b> member of the <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_dxvahd_setvideoprocessstreamstate">D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE</a> structure in a call to the driver's <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessstreamstate">SetVideoProcessStreamState</a> function to set the frame format of the input stream.

The driver might not set the DXVAHDDDI_INPUT_FORMAT_CAPS_RGB_INTERLACED value in the <b>InputFormatCaps</b> member of the <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_vpdevcaps">DXVAHDDDI_VPDEVCAPS</a> structure when the driver's <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a> function is called with the D3DDDICAPS_DXVAHD_GETVPDEVCAPS value set. If so and if the input stream is RGB format type, the interlaced frame format is ignored and assumed to be progressive.

The driver also might not set the DXVAHDDDI_INPUT_FORMAT_CAPS_PALETTE_INTERLACED value in the <b>InputFormatCaps</b> member of DXVAHDDDI_VPDEVCAPS. If so and if the input stream is palettized format type, the interlaced frame format is ignored and assumed to be progressive.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_dxvahd_setvideoprocessstreamstate">D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-_dxvahdddi_frame_format">DXVAHDDDI_FRAME_FORMAT</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_vpdevcaps">DXVAHDDDI_VPDEVCAPS</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessstreamstate">SetVideoProcessStreamState</a>

