---
UID: NS:d3d10umddi.D3D11DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY
title: D3D11DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY (d3d10umddi.h)
description: The D3D11DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY structure describes a portion of the stream output for a geometry shader.
old-location: display\d3d11ddiarg_stream_output_declaration_entry.htm
ms.assetid: 336bfc9d-325b-4ff1-8d6b-ec2ef4158cb9
ms.date: 05/10/2018
ms.keywords: D3D11DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY, D3D11DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY structure [Display Devices], UMDisplayDriver_Dx11param_Structs_c3324903-51b0-4679-ad77-b24cb5619bef.xml, d3d10umddi/D3D11DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY, display.d3d11ddiarg_stream_output_declaration_entry
ms.topic: struct
f1_keywords:
 - "d3d10umddi/D3D11DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY is supported beginning with the Windows 7 operating system.
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
- d3d10umddi.h
api_name:
- D3D11DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY
---

# D3D11DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY structure


## -description


The D3D11DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY structure describes a portion of the stream output for a geometry shader.


## -struct-fields




### -field Stream

[in] The stream to output from, which is a value between zero and the maximum number of streams that are specified by the driver. 


### -field OutputSlot

[in] The number of the slot for the portion of the stream output. 


### -field RegisterIndex

[in] The number of the register for the portion of the stream output. 


### -field RegisterMask

[in] The xyzw register mask for the portion of the stream output. That is, the four least significant bits (LSBs) of the mask represent xyzw respectively. 

