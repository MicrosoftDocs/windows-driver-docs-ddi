---
UID: NS:iddcx.IDDCX_SYSTEM_BUFFER_INFO
title: IDDCX_SYSTEM_BUFFER_INFO
ms.date: 10/20/2020
tech.root: display
ms.topic: language-reference
targetos: Windows
description: IDDCX_SYSTEM_BUFFER_INFO holds the resulting buffer-specific information after a buffer release and acquire operation.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: iddcx.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 21H1
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_SYSTEM_BUFFER_INFO
f1_keywords:
 - IDDCX_SYSTEM_BUFFER_INFO
 - iddcx/IDDCX_SYSTEM_BUFFER_INFO
dev_langs:
 - c++
---

## -description

> [!NOTE]
> Some information on this page relates to a pre-released product which may be substantially modified before it is commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

**IDDCX_SYSTEM_BUFFER_INFO** holds the resulting buffer-specific information after a buffer release and acquire operation.

## -struct-fields

### -field Size

Size of this structure, in bytes.

### -field Pitch

The pitch (also called stride) of the surface, in number of bytes.

### -field Height

The height of the surface, in number of pixels.

### -field Width

The width of the surface, in number of pixels.

### -field Format

A [**DXGI_FORMAT**](/windows/win32/api/dxgiformat/ne-dxgiformat-dxgi_format) structure that identifies the format of the surface pixel.

### -field pBuffer

Pointer in system memory to the surface buffer. **pBuffer** must be at lease 16-byte aligned.

## -remarks

## -see-also

[**IDARG_OUT_RELEASEANDACQUIRESYSTEMBUFFER**](ns-iddcx-idarg_out_releaseandacquiresystembuffer.md)

[**IddCxSwapChainReleaseAndAcquireSystemBuffer**](ns-iddcx-idarg_out_releaseandacquiresystembuffer.md)

