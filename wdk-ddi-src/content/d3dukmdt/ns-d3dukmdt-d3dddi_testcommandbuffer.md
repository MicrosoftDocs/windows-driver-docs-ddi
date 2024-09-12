---
UID: NS:d3dukmdt._D3DDDI_TESTCOMMANDBUFFER
tech.root: display
title: D3DDDI_TESTCOMMANDBUFFER
ms.date: 06/17/2024
targetos: Windows
description: Learn about the D3DDDI_TESTCOMMANDBUFFER structure.
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
req.typenames: D3DDDI_TESTCOMMANDBUFFER
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
 - _D3DDDI_TESTCOMMANDBUFFER
 - D3DDDI_TESTCOMMANDBUFFER
f1_keywords:
 - _D3DDDI_TESTCOMMANDBUFFER
 - d3dukmdt/_D3DDDI_TESTCOMMANDBUFFER
 - D3DDDI_TESTCOMMANDBUFFER
 - d3dukmdt/D3DDDI_TESTCOMMANDBUFFER
dev_langs:
 - c++
helpviewer_keywords:
 - _D3DDDI_TESTCOMMANDBUFFER
---

## -description

The **D3DDDI_TESTCOMMANDBUFFER** structure describes a test command buffer for kernel-mode testing.

## -struct-fields

### -field Copy

When **Operation** is **D3DDDI_TESTCOMMANDBUFFEROP_COPY**, this field is a [**D3DDDI_TESTCOMMANDBUFFER_COPY**](ns-d3dukmdt-d3dddi_testcommandbuffer_copy.md) structure for a copy operation.

### -field Fill

When **Operation** is **D3DDDI_TESTCOMMANDBUFFEROP_FILL**, this field is a [**D3DDDI_TESTCOMMANDBUFFER_FILL**](ns-d3dukmdt-d3dddi_testcommandbuffer_fill.md) structure for a fill operation.

### -field Reserved[64]

Reserved for future use.

### -field Operation

A [**D3DDDI_TESTCOMMANDBUFFEROP**](ne-d3dukmdt-d3dddi_testcommandbufferop.md) enumeration that specifies the type of operation for the test command buffer, and which operation-specific structure to use.

### -field Reserved1

Reserved.

## -remarks

For more information, see [Kernel-mode testing](/windows-hardware/drivers/display/kernel-mode-testing-of-wddm-features).

## -see-also

[**D3DDDI_DRIVERESCAPE_BUILDTESTCOMMANDBUFFER**](ns-d3dukmdt-d3dddi_driverescape_buildtestcommandbuffer.md)

[**D3DDDI_TESTCOMMANDBUFFER_COPY**](ns-d3dukmdt-d3dddi_testcommandbuffer_copy.md)

[**D3DDDI_TESTCOMMANDBUFFER_FILL**](ns-d3dukmdt-d3dddi_testcommandbuffer_fill.md)

[**D3DDDI_TESTCOMMANDBUFFEROP**](ne-d3dukmdt-d3dddi_testcommandbufferop.md)

[**DXGKARG_BUILDTESTCOMMANDBUFFER**](../d3dkmddi/ns-d3dkmddi-dxgkarg_buildtestcommandbuffer.md)

[**pfnBuildTestCommandBuffer**](../d3dkmddi/ns-d3dkmddi-dxgkddi_kernelmodetestinginterface.md)
