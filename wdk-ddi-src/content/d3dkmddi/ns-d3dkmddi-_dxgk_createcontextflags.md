---
UID: NS:d3dkmddi._DXGK_CREATECONTEXTFLAGS
title: DXGK_CREATECONTEXTFLAGS (d3dkmddi.h)
description: Learn more about the DXGK_CREATECONTEXTFLAGS structure.
ms.date: 05/21/2024
keywords: ["DXGK_CREATECONTEXTFLAGS structure"]
ms.keywords: DXGK_CREATECONTEXTFLAGS, DXGK_CREATECONTEXTFLAGS structure [Display Devices], DmStructs_19418464-77f9-407f-8b04-c6a35561069b.xml, _DXGK_CREATECONTEXTFLAGS, d3dkmddi/DXGK_CREATECONTEXTFLAGS, display.dxgk_createcontextflags
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
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
targetos: Windows
tech.root: display
req.typenames: DXGK_CREATECONTEXTFLAGS
f1_keywords:
 - _DXGK_CREATECONTEXTFLAGS
 - d3dkmddi/_DXGK_CREATECONTEXTFLAGS
 - DXGK_CREATECONTEXTFLAGS
 - d3dkmddi/DXGK_CREATECONTEXTFLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_CREATECONTEXTFLAGS
 - DXGK_CREATECONTEXTFLAGS
---

# DXGK_CREATECONTEXTFLAGS structure

## -description

The **DXGK_CREATECONTEXTFLAGS** structure identifies how to create contexts.

## -struct-fields

### -field SystemContext

A UINT value that specifies whether contexts that a driver's [**DxgkDdiCreateContext**](nc-d3dkmddi-dxgkddi_createcontext.md) function creates are system contexts for the engine that the **EngineAffinity** member of the [**DXGKARG_CREATECONTEXT**](ns-d3dkmddi-_dxgkarg_createcontext.md) structure specifies. A system context is created for the paging engine only.

### -field GdiContext

A UINT value that specifies whether the contexts that a driver's [**DxgkDdiCreateContext**](nc-d3dkmddi-dxgkddi_createcontext.md) function creates are GDI-specific contexts for the engine that the **EngineAffinity** member of the [**DXGKARG_CREATECONTEXT**](ns-d3dkmddi-_dxgkarg_createcontext.md) structure specifies.

This member is available beginning with Windows 7.

### -field VirtualAddressing

Specifies whether the contexts that a driver's [**DxgkDdiCreateContext**](nc-d3dkmddi-dxgkddi_createcontext.md) function creates use virtual addressing.

Supported starting with Windows 10.

### -field SystemProtectedContext

Specifies whether the context being used to modify the VPR will have access to allocations outside the VPR.

Supported starting with Windows 10.

### -field HwQueueSupported

Specifies whether the context supports hardware queues.

### -field TestContext

Specifies whether the context is a test context for [Kernel-mode testing](/windows-hardware/drivers/display/kernel-mode-testing-of-wddm-features). Available starting with Windows 11, version 24H2 (WDDM 3.2).

### -field Reserved

This member is reserved and should be set to zero.

### -field Value

A member in the union that **DXGK_CREATECONTEXTFLAGS** contains that can hold a 32-bit value that identifies how to create contexts.

## -see-also

[**DXGKARG_CREATECONTEXT**](ns-d3dkmddi-_dxgkarg_createcontext.md)

[**DxgkDdiCreateContext**](nc-d3dkmddi-dxgkddi_createcontext.md)
