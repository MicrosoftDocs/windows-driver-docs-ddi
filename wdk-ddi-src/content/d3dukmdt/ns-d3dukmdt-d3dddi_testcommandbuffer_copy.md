---
UID: NS:d3dukmdt._D3DDDI_TESTCOMMANDBUFFER_COPY
tech.root: display
title: D3DDDI_TESTCOMMANDBUFFER_COPY
ms.date: 06/17/2024
targetos: Windows
description: Learn about the D3DDDI_TESTCOMMANDBUFFER_COPY structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dukmdt.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3DDDI_TESTCOMMANDBUFFER_COPY
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _D3DDDI_TESTCOMMANDBUFFER_COPY
 - D3DDDI_TESTCOMMANDBUFFER_COPY
f1_keywords:
 - _D3DDDI_TESTCOMMANDBUFFER_COPY
 - d3dukmdt/_D3DDDI_TESTCOMMANDBUFFER_COPY
 - D3DDDI_TESTCOMMANDBUFFER_COPY
 - d3dukmdt/D3DDDI_TESTCOMMANDBUFFER_COPY
dev_langs:
 - c++
helpviewer_keywords:
 - _D3DDDI_TESTCOMMANDBUFFER_COPY
---

## -description

The **D3DDDI_TESTCOMMANDBUFFER_COPY** structure describes a copy operation for a test command buffer for kernel-mode testing.

## -struct-fields

### -field SrcAddress

The source GPU virtual address for the copy operation.

### -field DstAddress

The destination GPU virtual address for the copy operation.

### -field NumBytes

The number of bytes to copy. **NumBytes** must be a multiple of 4.

## -remarks

**D3DDDI_TESTCOMMANDBUFFER_COPY** is used to copy bytes using source and destination GPU virtual addresses.

For more information, see [Kernel-mode testing](/windows-hardware/drivers/display/kernel-mode-testing-of-wddm-features).

## -see-also

[**D3DDDI_TESTCOMMANDBUFFER**](ns-d3dukmdt-d3dddi_testcommandbuffer.md)

[**D3DDDI_TESTCOMMANDBUFFER_FILL**](ns-d3dukmdt-d3dddi_testcommandbuffer_fill.md)

[**pfnBuildTestCommandBuffer**](../d3dkmddi/ns-d3dkmddi-dxgkarg_buildtestcommandbuffer.md)
