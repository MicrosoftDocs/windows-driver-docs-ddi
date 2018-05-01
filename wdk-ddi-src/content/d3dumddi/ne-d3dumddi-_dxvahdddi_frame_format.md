---
UID: NE:d3dumddi._DXVAHDDDI_FRAME_FORMAT
title: "_DXVAHDDDI_FRAME_FORMAT"
author: windows-driver-content
description: The DXVAHDDDI_FRAME_FORMAT enumeration contains values that identify the frame format.
old-location: display\dxvahdddi_frame_format.htm
old-project: display
ms.assetid: 82fded96-9321-47a8-8bdd-65c5a75951ac
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXVA2_Structs_7335a1ee-9d91-4764-aba3-5769351f7aa5.xml, DXVAHDDDI_FRAME_FORMAT, DXVAHDDDI_FRAME_FORMAT enumeration [Display Devices], DXVAHDDDI_FRAME_FORMAT_INTERLACED_BOTTOM_FIELD_FIRST, DXVAHDDDI_FRAME_FORMAT_INTERLACED_TOP_FIELD_FIRST, DXVAHDDDI_FRAME_FORMAT_PROGRESSIVE, _DXVAHDDDI_FRAME_FORMAT, d3dumddi/DXVAHDDDI_FRAME_FORMAT, d3dumddi/DXVAHDDDI_FRAME_FORMAT_INTERLACED_BOTTOM_FIELD_FIRST, d3dumddi/DXVAHDDDI_FRAME_FORMAT_INTERLACED_TOP_FIELD_FIRST, d3dumddi/DXVAHDDDI_FRAME_FORMAT_PROGRESSIVE, display.dxvahdddi_frame_format
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	DXVAHDDDI_FRAME_FORMAT
product: Windows
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



The <a href="https://msdn.microsoft.com/f697e0db-1db0-4a81-94d8-0ca079885480">FOURCC</a> format of the surface defines whether the interlaced fields are interleaved or not. For example, NV12 is an interlaced format with interleaved fields whereas NV24 is an interlaced format with non-interleaved fields.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563081">DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA</a>
 

 

