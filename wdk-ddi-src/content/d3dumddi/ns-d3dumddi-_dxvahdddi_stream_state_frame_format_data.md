---
UID: NS:d3dumddi._DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA
title: "_DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA"
author: windows-driver-content
description: The DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA structure describes data that specifies the frame format of the input.
old-location: display\dxvahdddi_stream_state_frame_format_data.htm
old-project: display
ms.assetid: e04e21e7-6d13-4705-8cc9-cc1b00bf04e4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA, display.dxvahdddi_stream_state_frame_format_data, DXVA2_Structs_5dd1d1dc-aadc-4772-888e-f16eac3dd935.xml, d3dumddi/DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA, _DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA, DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA
product: Windows
targetos: Windows
req.typenames: DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA
---

# _DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA structure


## -description


The DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA structure describes data that specifies the frame format of the input. 


## -syntax


````
typedef struct _DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA {
  DXVAHDDDI_FRAME_FORMAT FrameFormat;
} DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA;
````


## -struct-fields




#### - FrameFormat

[in] A <a href="..\d3dumddi\ne-d3dumddi-_dxvahdddi_frame_format.md">DXVAHDDDI_FRAME_FORMAT</a>-typed value that indicates the frame format of the input stream. The default value is DXVAHDDDI_FRAME_FORMAT_PROGRESSIVE, which indicates progressive format. 


## -remarks


The Direct3D runtime specifies the DXVAHDDDI_STREAM_STATE_FRAME_FORMAT state in the <b>State</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_dxvahd_setvideoprocessstreamstate.md">D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE</a> structure in a call to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessstreamstate.md">SetVideoProcessStreamState</a> function to set the frame format of the input stream.

The driver might not set the DXVAHDDDI_INPUT_FORMAT_CAPS_RGB_INTERLACED value in the <b>InputFormatCaps</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_vpdevcaps.md">DXVAHDDDI_VPDEVCAPS</a> structure when the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a> function is called with the D3DDDICAPS_DXVAHD_GETVPDEVCAPS value set. If so and if the input stream is RGB format type, the interlaced frame format is ignored and assumed to be progressive.

The driver also might not set the DXVAHDDDI_INPUT_FORMAT_CAPS_PALETTE_INTERLACED value in the <b>InputFormatCaps</b> member of DXVAHDDDI_VPDEVCAPS. If so and if the input stream is palettized format type, the interlaced frame format is ignored and assumed to be progressive.



## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessstreamstate.md">SetVideoProcessStreamState</a>

<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_vpdevcaps.md">DXVAHDDDI_VPDEVCAPS</a>

<a href="..\d3dumddi\ne-d3dumddi-_dxvahdddi_frame_format.md">DXVAHDDDI_FRAME_FORMAT</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_dxvahd_setvideoprocessstreamstate.md">D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

