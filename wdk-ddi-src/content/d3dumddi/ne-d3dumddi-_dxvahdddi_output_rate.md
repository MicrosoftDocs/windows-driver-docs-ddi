---
UID: NE:d3dumddi._DXVAHDDDI_OUTPUT_RATE
title: _DXVAHDDDI_OUTPUT_RATE (d3dumddi.h)
description: The DXVAHDDDI_OUTPUT_RATE enumeration contains values that identify the output rate that the driver should use.
old-location: display\dxvahdddi_output_rate.htm
tech.root: display
ms.assetid: 61418263-3159-413d-844f-83556ce6baf0
ms.date: 05/10/2018
keywords: ["_DXVAHDDDI_OUTPUT_RATE enumeration"]
ms.keywords: DXVA2_Structs_34010924-8e9c-440c-a972-e2ae58124666.xml, DXVAHDDDI_OUTPUT_RATE, DXVAHDDDI_OUTPUT_RATE enumeration [Display Devices], DXVAHDDDI_OUTPUT_RATE_CUSTOM, DXVAHDDDI_OUTPUT_RATE_HALF, DXVAHDDDI_OUTPUT_RATE_NORMAL, _DXVAHDDDI_OUTPUT_RATE, d3dumddi/DXVAHDDDI_OUTPUT_RATE, d3dumddi/DXVAHDDDI_OUTPUT_RATE_CUSTOM, d3dumddi/DXVAHDDDI_OUTPUT_RATE_HALF, d3dumddi/DXVAHDDDI_OUTPUT_RATE_NORMAL, display.dxvahdddi_output_rate
f1_keywords:
 - "d3dumddi/DXVAHDDDI_OUTPUT_RATE"
 - "DXVAHDDDI_OUTPUT_RATE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- DXVAHDDDI_OUTPUT_RATE
product:
- Windows
targetos: Windows
req.typenames: DXVAHDDDI_OUTPUT_RATE
---

# _DXVAHDDDI_OUTPUT_RATE enumeration


## -description


The DXVAHDDDI_OUTPUT_RATE enumeration contains values that identify the output rate that the driver should use. 


## -enum-fields




### -field DXVAHDDDI_OUTPUT_RATE_NORMAL

A value that specifies that the driver should use normal output rate, which is when one progressive frame becomes one progressive frame and one interlaced frame (two fields) becomes two progressive frames. 


### -field DXVAHDDDI_OUTPUT_RATE_HALF

A value that specifies that the driver should use half output rate, which is when one progressive frame becomes one progressive frame and one interlaced frame (two fields) becomes one progressive frame.


### -field DXVAHDDDI_OUTPUT_RATE_CUSTOM

A value that specifies that the driver should use a custom output rate for the frame rate conversion or the inverse telecine. For more information about custom output rate, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_custom_rate_data">DXVAHDDDI_CUSTOM_RATE_DATA</a>. 


## -remarks



For more information about output rate, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_output_rate_data">DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_data">DXVAHDDDI_STREAM_DATA</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_custom_rate_data">DXVAHDDDI_CUSTOM_RATE_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_data">DXVAHDDDI_STREAM_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_output_rate_data">DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA</a>
 

 

