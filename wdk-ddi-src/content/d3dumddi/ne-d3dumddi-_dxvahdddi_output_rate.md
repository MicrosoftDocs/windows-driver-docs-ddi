---
UID: NE:d3dumddi._DXVAHDDDI_OUTPUT_RATE
title: "_DXVAHDDDI_OUTPUT_RATE"
author: windows-driver-content
description: The DXVAHDDDI_OUTPUT_RATE enumeration contains values that identify the output rate that the driver should use.
old-location: display\dxvahdddi_output_rate.htm
old-project: display
ms.assetid: 61418263-3159-413d-844f-83556ce6baf0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dumddi/DXVAHDDDI_OUTPUT_RATE, d3dumddi/DXVAHDDDI_OUTPUT_RATE_CUSTOM, DXVAHDDDI_OUTPUT_RATE enumeration [Display Devices], DXVAHDDDI_OUTPUT_RATE, _DXVAHDDDI_OUTPUT_RATE, d3dumddi/DXVAHDDDI_OUTPUT_RATE_NORMAL, DXVAHDDDI_OUTPUT_RATE_NORMAL, DXVAHDDDI_OUTPUT_RATE_HALF, d3dumddi/DXVAHDDDI_OUTPUT_RATE_HALF, DXVA2_Structs_34010924-8e9c-440c-a972-e2ae58124666.xml, display.dxvahdddi_output_rate, DXVAHDDDI_OUTPUT_RATE_CUSTOM
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_OUTPUT_RATE is supported beginning with the Windows 7 operating system.
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
-	DXVAHDDDI_OUTPUT_RATE
product: Windows
targetos: Windows
req.typenames: DXVAHDDDI_OUTPUT_RATE
---

# _DXVAHDDDI_OUTPUT_RATE enumeration


## -description


The DXVAHDDDI_OUTPUT_RATE enumeration contains values that identify the output rate that the driver should use. 


## -syntax


````
typedef enum _DXVAHDDDI_OUTPUT_RATE { 
  DXVAHDDDI_OUTPUT_RATE_NORMAL  = 0,
  DXVAHDDDI_OUTPUT_RATE_HALF    = 1,
  DXVAHDDDI_OUTPUT_RATE_CUSTOM  = 2
} DXVAHDDDI_OUTPUT_RATE;
````


## -enum-fields




### -field DXVAHDDDI_OUTPUT_RATE_NORMAL

A value that specifies that the driver should use normal output rate, which is when one progressive frame becomes one progressive frame and one interlaced frame (two fields) becomes two progressive frames. 


### -field DXVAHDDDI_OUTPUT_RATE_HALF

A value that specifies that the driver should use half output rate, which is when one progressive frame becomes one progressive frame and one interlaced frame (two fields) becomes one progressive frame.


### -field DXVAHDDDI_OUTPUT_RATE_CUSTOM

A value that specifies that the driver should use a custom output rate for the frame rate conversion or the inverse telecine. For more information about custom output rate, see <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_custom_rate_data.md">DXVAHDDDI_CUSTOM_RATE_DATA</a>. 


## -remarks


For more information about output rate, see <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_output_rate_data.md">DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA</a> and <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_data.md">DXVAHDDDI_STREAM_DATA</a>.



## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_custom_rate_data.md">DXVAHDDDI_CUSTOM_RATE_DATA</a>

<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_data.md">DXVAHDDDI_STREAM_DATA</a>

<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_output_rate_data.md">DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_OUTPUT_RATE enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

