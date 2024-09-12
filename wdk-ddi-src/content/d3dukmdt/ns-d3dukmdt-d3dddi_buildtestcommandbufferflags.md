---
UID: NS:d3dukmdt._D3DDDI_BUILDTESTCOMMANDBUFFERFLAGS
tech.root: display
title: D3DDDI_BUILDTESTCOMMANDBUFFERFLAGS
ms.date: 06/18/2024
targetos: Windows
description: Learn about the D3DDDI_BUILDTESTCOMMANDBUFFERFLAGS structure.
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
req.typenames: D3DDDI_BUILDTESTCOMMANDBUFFERFLAGS
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
 - _D3DDDI_BUILDTESTCOMMANDBUFFERFLAGS
 - D3DDDI_BUILDTESTCOMMANDBUFFERFLAGS
f1_keywords:
 - _D3DDDI_BUILDTESTCOMMANDBUFFERFLAGS
 - d3dukmdt/_D3DDDI_BUILDTESTCOMMANDBUFFERFLAGS
 - D3DDDI_BUILDTESTCOMMANDBUFFERFLAGS
 - d3dukmdt/D3DDDI_BUILDTESTCOMMANDBUFFERFLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - _D3DDDI_BUILDTESTCOMMANDBUFFERFLAGS
---

## -description

The **D3DDDI_BUILDTESTCOMMANDBUFFERFLAGS** structure specifies flags for [**DXGKDDI_BUILDTESTCOMMANDBUFFER**](../d3dkmddi/nc-d3dkmddi-dxgkddi_buildtestcommandbuffer.md) to use when building a command buffer for kernel-mode testing.

## -struct-fields

### -field HardwareQueue

Indicates the type of context handle in [**DXGKARG_BUILDTESTCOMMANDBUFFER::hContext**](../d3dkmddi/ns-d3dkmddi-dxgkarg_buildtestcommandbuffer.md). When **HardwareQueue** is 1, the context handle is a hardware queue handle. When **HardwareQueue** is 0, the context handle is a KMD context handle.

### -field Reserved

Reserved for future use.

### -field Value

Can be used to access the flags as a single value.

## -remarks

For more information, see [Kernel-mode testing](/windows-hardware/drivers/display/kernel-mode-testing-of-wddm-features).

## -see-also

[**DXGKARG_BUILDTESTCOMMANDBUFFER**](../d3dkmddi/ns-d3dkmddi-dxgkarg_buildtestcommandbuffer.md)

[**DxgkDdiCreateContext**](../d3dkmddi/nc-d3dkmddi-dxgkddi_createcontext.md)

[**DxgkDdiCreatehwqueue**](../d3dkmddi/nc-d3dkmddi-dxgkddi_createhwqueue.md)

[**pfnBuildTestCommandBuffer**](../d3dkmddi/ns-d3dkmddi-dxgkarg_buildtestcommandbuffer.md)
