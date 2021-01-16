---
UID: NE:d3dumddi._DXVAHDDDI_STREAM_STATE
title: _DXVAHDDDI_STREAM_STATE (d3dumddi.h)
description: The DXVAHDDDI_STREAM_STATE enumeration contains values that identify the stream-state data for a video processor.
old-location: display\dxvahdddi_stream_state.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXVAHDDDI_STREAM_STATE enumeration"]
ms.keywords: DXVA2_Structs_7202aa6b-cf67-4d88-aeca-a968e02bcfaf.xml, DXVAHDDDI_STREAM_STATE, DXVAHDDDI_STREAM_STATE enumeration [Display Devices], DXVAHDDDI_STREAM_STATE_ALPHA, DXVAHDDDI_STREAM_STATE_ASPECT_RATIO, DXVAHDDDI_STREAM_STATE_DESTINATION_RECT, DXVAHDDDI_STREAM_STATE_FILTER_ANAMORPHIC_SCALING, DXVAHDDDI_STREAM_STATE_FILTER_BRIGHTNESS, DXVAHDDDI_STREAM_STATE_FILTER_CONTRAST, DXVAHDDDI_STREAM_STATE_FILTER_EDGE_ENHANCEMENT, DXVAHDDDI_STREAM_STATE_FILTER_HUE, DXVAHDDDI_STREAM_STATE_FILTER_NOISE_REDUCTION, DXVAHDDDI_STREAM_STATE_FILTER_SATURATION, DXVAHDDDI_STREAM_STATE_FRAME_FORMAT, DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE, DXVAHDDDI_STREAM_STATE_LUMA_KEY, DXVAHDDDI_STREAM_STATE_OUTPUT_RATE, DXVAHDDDI_STREAM_STATE_PALETTE, DXVAHDDDI_STREAM_STATE_PRIVATE, DXVAHDDDI_STREAM_STATE_ROTATION, DXVAHDDDI_STREAM_STATE_SOURCE_RECT, _DXVAHDDDI_STREAM_STATE, d3dumddi/DXVAHDDDI_STREAM_STATE, d3dumddi/DXVAHDDDI_STREAM_STATE_ALPHA, d3dumddi/DXVAHDDDI_STREAM_STATE_ASPECT_RATIO, d3dumddi/DXVAHDDDI_STREAM_STATE_DESTINATION_RECT, d3dumddi/DXVAHDDDI_STREAM_STATE_FILTER_ANAMORPHIC_SCALING, d3dumddi/DXVAHDDDI_STREAM_STATE_FILTER_BRIGHTNESS, d3dumddi/DXVAHDDDI_STREAM_STATE_FILTER_CONTRAST, d3dumddi/DXVAHDDDI_STREAM_STATE_FILTER_EDGE_ENHANCEMENT, d3dumddi/DXVAHDDDI_STREAM_STATE_FILTER_HUE, d3dumddi/DXVAHDDDI_STREAM_STATE_FILTER_NOISE_REDUCTION, d3dumddi/DXVAHDDDI_STREAM_STATE_FILTER_SATURATION, d3dumddi/DXVAHDDDI_STREAM_STATE_FRAME_FORMAT, d3dumddi/DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE, d3dumddi/DXVAHDDDI_STREAM_STATE_LUMA_KEY, d3dumddi/DXVAHDDDI_STREAM_STATE_OUTPUT_RATE, d3dumddi/DXVAHDDDI_STREAM_STATE_PALETTE, d3dumddi/DXVAHDDDI_STREAM_STATE_PRIVATE, d3dumddi/DXVAHDDDI_STREAM_STATE_ROTATION, d3dumddi/DXVAHDDDI_STREAM_STATE_SOURCE_RECT, display.dxvahdddi_stream_state
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_STREAM_STATE is supported starting with Windows 7.
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
req.typenames: DXVAHDDDI_STREAM_STATE
f1_keywords:
 - _DXVAHDDDI_STREAM_STATE
 - d3dumddi/_DXVAHDDDI_STREAM_STATE
 - DXVAHDDDI_STREAM_STATE
 - d3dumddi/DXVAHDDDI_STREAM_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _DXVAHDDDI_STREAM_STATE
 - DXVAHDDDI_STREAM_STATE
---

# _DXVAHDDDI_STREAM_STATE enumeration


## -description

The DXVAHDDDI_STREAM_STATE enumeration contains values that identify the stream-state data for a video processor.

## -enum-fields

### -field DXVAHDDDI_STREAM_STATE_FRAME_FORMAT

The stream-state data specifies the frame format of the input in a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_frame_format_data">DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA</a> structure.

### -field DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE

The stream-state data specifies the color space of the input in a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_input_color_space_data">DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA</a> structure.

### -field DXVAHDDDI_STREAM_STATE_OUTPUT_RATE

The stream-state data specifies the output rate of the input in a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_output_rate_data">DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA</a> structure.

### -field DXVAHDDDI_STREAM_STATE_SOURCE_RECT

The stream-state data specifies the source rectangle of the input in a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_source_rect_data">DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA</a> structure.

### -field DXVAHDDDI_STREAM_STATE_DESTINATION_RECT

The stream-state data specifies the destination rectangle in a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_destination_rect_data">DXVAHDDDI_STREAM_STATE_DESTINATION_RECT_DATA</a> structure.

### -field DXVAHDDDI_STREAM_STATE_ALPHA

The stream-state data specifies the alpha blend level per-plane in a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_alpha_data">DXVAHDDDI_STREAM_STATE_ALPHA_DATA</a> structure.

### -field DXVAHDDDI_STREAM_STATE_PALETTE

The stream-state data specifies the palette entries of the input in a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_palette_data">DXVAHDDDI_STREAM_STATE_PALETTE_DATA</a> structure.

### -field DXVAHDDDI_STREAM_STATE_LUMA_KEY

The stream-state data specifies the luma key of the input in a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_luma_key_data">DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA</a> structure.

### -field DXVAHDDDI_STREAM_STATE_ASPECT_RATIO

The stream-state data specifies the aspect ratio of the input in a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_aspect_ratio_data">DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA</a> structure.

### -field DXVAHDDDI_STREAM_STATE_ROTATION

The stream-state data specifies the  clockwise rotation of the display output surface in a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_rotation_data">DXVAHDDDI_STREAM_STATE_ROTATION_DATA</a> structure.

Supported starting with Windows 8.

### -field DXVAHDDDI_STREAM_STATE_FILTER_BRIGHTNESS

The stream-state data specifies the brightness ProcAmp level in a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_filter_data">DXVAHDDDI_STREAM_STATE_FILTER_DATA</a> structure.

### -field DXVAHDDDI_STREAM_STATE_FILTER_CONTRAST

The stream-state data specifies the contrast ProcAmp level in a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_filter_data">DXVAHDDDI_STREAM_STATE_FILTER_DATA</a> structure.

### -field DXVAHDDDI_STREAM_STATE_FILTER_HUE

The stream-state data specifies the hue ProcAmp level in a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_filter_data">DXVAHDDDI_STREAM_STATE_FILTER_DATA</a> structure.

### -field DXVAHDDDI_STREAM_STATE_FILTER_SATURATION

The stream-state data specifies the saturation ProcAmp level in a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_filter_data">DXVAHDDDI_STREAM_STATE_FILTER_DATA</a> structure.

### -field DXVAHDDDI_STREAM_STATE_FILTER_NOISE_REDUCTION

The stream-state data specifies the noise reduction filter level in a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_filter_data">DXVAHDDDI_STREAM_STATE_FILTER_DATA</a> structure.

### -field DXVAHDDDI_STREAM_STATE_FILTER_EDGE_ENHANCEMENT

The stream-state data specifies the edge enhancement filter level in a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_filter_data">DXVAHDDDI_STREAM_STATE_FILTER_DATA</a> structure.

### -field DXVAHDDDI_STREAM_STATE_FILTER_ANAMORPHIC_SCALING

The stream-state data specifies the anamorphic scaling level in a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_filter_data">DXVAHDDDI_STREAM_STATE_FILTER_DATA</a> structure.

### -field DXVAHDDDI_STREAM_STATE_PRIVATE

The stream-state data specifies private parameters in a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_private_data">DXVAHDDDI_STREAM_STATE_PRIVATE_DATA</a> structure.

## -remarks

A DXVAHDDDI_STREAM_STATE-typed value is specified in the <b>State</b> member of the <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_dxvahd_setvideoprocessstreamstate">D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE</a> structure in a call to the <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessstreamstate">SetVideoProcessStreamState</a> function to set the stream state for a video processor. Stream-state data that corresponds to the supplied DXVAHDDDI_STREAM_STATE-typed value is pointed to by the <b>pData</b> member of D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_dxvahd_setvideoprocessstreamstate">D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_alpha_data">DXVAHDDDI_STREAM_STATE_ALPHA_DATA</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_aspect_ratio_data">DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_destination_rect_data">DXVAHDDDI_STREAM_STATE_DESTINATION_RECT_DATA</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_filter_data">DXVAHDDDI_STREAM_STATE_FILTER_DATA</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_frame_format_data">DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_input_color_space_data">DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_luma_key_data">DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_output_rate_data">DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_palette_data">DXVAHDDDI_STREAM_STATE_PALETTE_DATA</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_private_data">DXVAHDDDI_STREAM_STATE_PRIVATE_DATA</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_rotation_data">DXVAHDDDI_STREAM_STATE_ROTATION_DATA</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_source_rect_data">DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessstreamstate">SetVideoProcessStreamState</a>

