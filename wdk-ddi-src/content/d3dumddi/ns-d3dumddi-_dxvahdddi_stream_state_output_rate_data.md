---
UID: NS:d3dumddi._DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA
title: "_DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA"
author: windows-driver-content
description: The DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA structure describes stream-state data that specifies the output rate of the input stream.
old-location: display\dxvahdddi_stream_state_output_rate_data.htm
old-project: display
ms.assetid: 97523719-d22a-4390-ac4a-6240f24144bf
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA, DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA structure [Display Devices], DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA, d3dumddi/DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA, display.dxvahdddi_stream_state_output_rate_data, DXVA2_Structs_32dedbf1-1052-4765-a0dd-4f536389dbb6.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA
product: Windows
targetos: Windows
req.typenames: DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA
---

# _DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA structure


## -description


The DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA structure describes stream-state data that specifies the output rate of the input stream. 


## -syntax


````
typedef struct _DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA {
  BOOL                  RepeatFrame;
  DXVAHDDDI_OUTPUT_RATE OutputRate;
  DXVAHDDDI_RATIONAL    CustomRate;
} DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA;
````


## -struct-fields




### -field RepeatFrame

[in] A Boolean value that specifies whether the frame rate conversion repeats or interpolates the frames. The driver refers to <b>RepeatFrame</b> only when it uses the frame rate conversion. The default value is <b>FALSE</b>, which indicates that the frame rate conversion interpolates the frames. 


### -field OutputRate

[in] A <a href="..\d3dumddi\ne-d3dumddi-_dxvahdddi_output_rate.md">DXVAHDDDI_OUTPUT_RATE</a>-typed value that indicates the output rate of the input stream. The default value is DXVAHDDDI_OUTPUT_RATE_NORMAL. 


### -field CustomRate

[in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_rational.md">DXVAHDDDI_RATIONAL</a> structure that specifies a fractional value that represents a custom output rate. The driver refers to <b>CustomRate</b> only when the value that is specified in <b>OutputRate</b> is DXVAHDDDI_OUTPUT_RATE_CUSTOM. The default value is 1/1. 


## -remarks


The driver uses the <b>RepeatFrame</b> member to control the frame rate conversion. For example, when the driver converts from 60i to 60p, if the video processor is capable of both the inverse telecine (60i to 24p) and the frame rate conversion (24p to 60p), then the converted frames contains interpolated frames. Sometimes the interpolation results in artifacts, and the application might require to repeat the frames instead.

The <b>CustomRate</b> member must specify one of the custom rates that the driver supplied in the members of the <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_custom_rate_data.md">DXVAHDDDI_CUSTOM_RATE_DATA</a> structure when the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a> function was called with the D3DDDICAPS_DXVAHD_GETVPCUSTOMRATES value set; otherwise, the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessstreamstate.md">SetVideoProcessStreamState</a> function returns an error.



## -see-also

<a href="..\d3dumddi\ne-d3dumddi-_dxvahdddi_output_rate.md">DXVAHDDDI_OUTPUT_RATE</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessstreamstate.md">SetVideoProcessStreamState</a>

<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_custom_rate_data.md">DXVAHDDDI_CUSTOM_RATE_DATA</a>

<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_rational.md">DXVAHDDDI_RATIONAL</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

