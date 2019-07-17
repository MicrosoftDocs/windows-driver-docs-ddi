---
UID: NS:d3dumddi._D3DDDIARG_BUFFERBLT1
title: _D3DDDIARG_BUFFERBLT1 (d3dumddi.h)
description: Describes the parameters of a buffer bit-block transfer (bitblt) operation.
old-location: display\d3dddiarg_bufferblt1.htm
tech.root: display
ms.assetid: 1dd2bf12-741b-4f3a-9c80-367b5d5036b5
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_BUFFERBLT1, D3DDDIARG_BUFFERBLT1 structure [Display Devices], _D3DDDIARG_BUFFERBLT1, d3dumddi/D3DDDIARG_BUFFERBLT1, display.d3dddiarg_bufferblt1
ms.topic: struct
f1_keywords:
 - "d3dumddi/D3DDDIARG_BUFFERBLT1"
req.header: d3dumddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- D3dumddi.h
api_name:
- D3DDDIARG_BUFFERBLT1
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_BUFFERBLT1
---

# _D3DDDIARG_BUFFERBLT1 structure


## -description


Describes the parameters of a buffer bit-block transfer (bitblt) operation.


## -struct-fields




### -field hDstResource

A handle to the destination resource.


### -field hSrcResource

A handle to the source resource.


### -field Offset

The offset in the destination surface, in bytes.


### -field SrcRange

The source range.


### -field CopyFlags

A value that specifies characteristics of a copy operation as a bitwise OR of the values in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ne-d3dumddi-d3dddi_copy_flags">D3DDDI_COPY_FLAGS</a> enumeration type.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ne-d3dumddi-d3dddi_copy_flags">D3DDDI_COPY_FLAGS</a>
 

 

