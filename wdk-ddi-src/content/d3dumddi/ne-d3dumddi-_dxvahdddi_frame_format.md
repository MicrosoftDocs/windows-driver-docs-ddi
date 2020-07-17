---
UID: NE:d3dumddi._DXVAHDDDI_FRAME_FORMAT
title: _DXVAHDDDI_FRAME_FORMAT (d3dumddi.h)
description: The DXVAHDDDI_FRAME_FORMAT enumeration contains values that identify the frame format.
old-location: display\dxvahdddi_frame_format.htm
tech.root: display
ms.assetid: 82fded96-9321-47a8-8bdd-65c5a75951ac
ms.date: 05/10/2018
keywords: ["_DXVAHDDDI_FRAME_FORMAT enumeration"]
ms.keywords: DXVA2_Structs_7335a1ee-9d91-4764-aba3-5769351f7aa5.xml, DXVAHDDDI_FRAME_FORMAT, DXVAHDDDI_FRAME_FORMAT enumeration [Display Devices], DXVAHDDDI_FRAME_FORMAT_INTERLACED_BOTTOM_FIELD_FIRST, DXVAHDDDI_FRAME_FORMAT_INTERLACED_TOP_FIELD_FIRST, DXVAHDDDI_FRAME_FORMAT_PROGRESSIVE, _DXVAHDDDI_FRAME_FORMAT, d3dumddi/DXVAHDDDI_FRAME_FORMAT, d3dumddi/DXVAHDDDI_FRAME_FORMAT_INTERLACED_BOTTOM_FIELD_FIRST, d3dumddi/DXVAHDDDI_FRAME_FORMAT_INTERLACED_TOP_FIELD_FIRST, d3dumddi/DXVAHDDDI_FRAME_FORMAT_PROGRESSIVE, display.dxvahdddi_frame_format
f1_keywords:
 - "d3dumddi/DXVAHDDDI_FRAME_FORMAT"
 - "DXVAHDDDI_FRAME_FORMAT"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_FRAME_FORMAT is supported beginning with the Windows 7 operating system.
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
- DXVAHDDDI_FRAME_FORMAT
product:
- Windows
targetos: Windows
req.typenames: DXVAHDDDI_FRAME_FORMAT
---

# _DXVAHDDDI_FRAME_FORMAT enumeration


## -description


The DXVAHDDDI_FRAME_FORMAT enumeration contains values that identify the frame format. 


## -enum-fields




### -field DXVAHDDDI_FRAME_FORMAT_PROGRESSIVE

A value that specifies that the frame format is progressive. 


### -field DXVAHDDDI_FRAME_FORMAT_INTERLACED_TOP_FIELD_FIRST

A value that specifies that the frame format is interlaced with two fields. The top (even) field is displayed first. 


### -field DXVAHDDDI_FRAME_FORMAT_INTERLACED_BOTTOM_FIELD_FIRST

A value that specifies that the frame format is interlaced with two fields. The bottom (odd) field is displayed first. 


## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/">FOURCC</a> format of the surface defines whether the interlaced fields are interleaved or not. For example, NV12 is an interlaced format with interleaved fields whereas NV24 is an interlaced format with non-interleaved fields.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_frame_format_data">DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA</a>
 

 

