---
UID: NS:d3dumddi._D3DDDIARG_SETSTREAMSOURCE
title: _D3DDDIARG_SETSTREAMSOURCE (d3dumddi.h)
description: The D3DDDIARG_SETSTREAMSOURCE structure describes the portion of the vertex stream to bind to a vertex buffer.
old-location: display\d3dddiarg_setstreamsource.htm
tech.root: display
ms.assetid: 6a178ef0-0741-4b0c-a688-cae3923135ac
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_SETSTREAMSOURCE, D3DDDIARG_SETSTREAMSOURCE structure [Display Devices], UMDisplayDriver_param_Structs_f90eed83-1d01-4502-84e4-22cff72016d6.xml, _D3DDDIARG_SETSTREAMSOURCE, d3dumddi/D3DDDIARG_SETSTREAMSOURCE, display.d3dddiarg_setstreamsource
ms.topic: struct
f1_keywords:
 - "d3dumddi/D3DDDIARG_SETSTREAMSOURCE"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
- D3DDDIARG_SETSTREAMSOURCE
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_SETSTREAMSOURCE
---

# _D3DDDIARG_SETSTREAMSOURCE structure


## -description


The D3DDDIARG_SETSTREAMSOURCE structure describes the portion of the vertex stream to bind to a vertex buffer. 


## -struct-fields




### -field Stream

[in] The stream to bind, which is a value between zero and the maximum number of streams that are specified by the driver.


### -field hVertexBuffer

[in] A handle to the vertex buffer. If this member is zero, the stream should no longer be bound to a vertex buffer.


### -field Offset

[in] The offset in bytes into the stream. 

The <b>Offset</b> value must be DWORD-aligned.


### -field Stride

[in] The size, in bytes, from one vertex to the next vertex. If <b>Stride</b> is set to zero, all of the vertices receive the same data for processing. 

For example, an application might use two input source streams where the first stream contains position information and the second stream contains normal information. If stride for the second stream is set to zero, all of the vertices in the second stream use the same normal information, which is the first normal information that occurs in the second stream.

The <b>Stride</b> value must be DWORD-aligned.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_setstreamsource">SetStreamSource</a>
 

 

