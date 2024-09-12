---
UID: NS:d3dukmdt._D3DDDI_TESTCOMMANDBUFFER_FILL
tech.root: display
title: D3DDDI_TESTCOMMANDBUFFER_FILL
ms.date: 06/17/2024
targetos: Windows
description: Learn about the D3DDDI_TESTCOMMANDBUFFER_FILL structure.
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
req.typenames: D3DDDI_TESTCOMMANDBUFFER_FILL
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
 - _D3DDDI_TESTCOMMANDBUFFER_FILL
 - D3DDDI_TESTCOMMANDBUFFER_FILL
f1_keywords:
 - _D3DDDI_TESTCOMMANDBUFFER_FILL
 - d3dukmdt/_D3DDDI_TESTCOMMANDBUFFER_FILL
 - D3DDDI_TESTCOMMANDBUFFER_FILL
 - d3dukmdt/D3DDDI_TESTCOMMANDBUFFER_FILL
dev_langs:
 - c++
helpviewer_keywords:
 - _D3DDDI_TESTCOMMANDBUFFER_FILL
---

## -description

The **D3DDDI_TESTCOMMANDBUFFER_FILL** structure describes a fill operation for a test command buffer for kernel-mode testing.

## -struct-fields

### -field DstAddress

Destination GPU virtual address for the fill operation.

### -field NumBytes

Number of bytes to fill. **NumBytes** must be a multiple of 4.

### -field Pattern

Pattern to fill. The pattern is 4 bytes that should be copied sequentially.

## -remarks

For more information, see [Kernel-mode testing](/windows-hardware/drivers/display/kernel-mode-testing-of-wddm-features).

## -see-also

[**D3DDDI_TESTCOMMANDBUFFER**](ns-d3dukmdt-d3dddi_testcommandbuffer.md)

[**D3DDDI_TESTCOMMANDBUFFER_COPY**](ns-d3dukmdt-d3dddi_testcommandbuffer_copy.md)

[**pfnBuildTestCommandBuffer**](../d3dkmddi/nc-d3dkmddi-dxgkddi_buildtestcommandbuffer.md)