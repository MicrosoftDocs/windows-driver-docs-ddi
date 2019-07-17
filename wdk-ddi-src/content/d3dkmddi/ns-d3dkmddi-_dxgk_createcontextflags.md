---
UID: NS:d3dkmddi._DXGK_CREATECONTEXTFLAGS
title: _DXGK_CREATECONTEXTFLAGS (d3dkmddi.h)
description: The DXGK_CREATECONTEXTFLAGS structure identifies how to create contexts.
old-location: display\dxgk_createcontextflags.htm
ms.assetid: f7cadf78-c908-4034-889d-b5c7d0ffdaad
ms.date: 05/10/2018
ms.keywords: DXGK_CREATECONTEXTFLAGS, DXGK_CREATECONTEXTFLAGS structure [Display Devices], DmStructs_19418464-77f9-407f-8b04-c6a35561069b.xml, _DXGK_CREATECONTEXTFLAGS, d3dkmddi/DXGK_CREATECONTEXTFLAGS, display.dxgk_createcontextflags
ms.topic: struct
f1_keywords:
 - "d3dkmddi/DXGK_CREATECONTEXTFLAGS"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
- d3dkmddi.h
api_name:
- DXGK_CREATECONTEXTFLAGS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_CREATECONTEXTFLAGS
---

# _DXGK_CREATECONTEXTFLAGS structure


## -description


The DXGK_CREATECONTEXTFLAGS structure identifies how to create contexts.


## -struct-fields




### -field SystemContext

A UINT value that specifies whether contexts that a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_createcontext">DxgkDdiCreateContext</a> function creates are system contexts for the engine that the <b>EngineAffinity</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_createcontext">DXGKARG_CREATECONTEXT</a> structure specifies. A system context is created for the paging engine only.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field GdiContext

A UINT value that specifies whether the contexts that a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_createcontext">DxgkDdiCreateContext</a> function creates are GDI-specific contexts for the engine that the <b>EngineAffinity</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_createcontext">DXGKARG_CREATECONTEXT</a> structure specifies.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).

This member is available beginning with Windows 7.


### -field VirtualAddressing

A UINT value that specifies whether the contexts that a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_createcontext">DxgkDdiCreateContext</a> function creates use virtual addressing.

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).

Supported starting with Windows 10.


### -field SystemProtectedContext

A UINT value that specifies whether the context being used to modify the VPR will have access to allocations outside the VPR.

Supported starting with Windows 10.


### -field HwQueueSupported

 


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 28 bits (0xFFFFFFFB) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A member in the union that DXGK_CREATECONTEXTFLAGS contains that can hold a 32-bit value that identifies how to create contexts.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_createcontext">DXGKARG_CREATECONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_createcontext">DxgkDdiCreateContext</a>
 

 

