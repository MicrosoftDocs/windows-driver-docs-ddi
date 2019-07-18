---
UID: NS:d3dkmddi._DXGKARG_CREATECONTEXT
title: _DXGKARG_CREATECONTEXT (d3dkmddi.h)
description: The DXGKARG_CREATECONTEXT structure describes parameters to create a device context.
old-location: display\dxgkarg_createcontext.htm
ms.assetid: 94239501-2eeb-479a-851a-14ae665c5887
ms.date: 05/10/2018
ms.keywords: "*INOUT_PDXGKARG_CREATECONTEXT, DXGKARG_CREATECONTEXT, DXGKARG_CREATECONTEXT structure [Display Devices], DmStructs_f88f9027-046c-482e-93c6-882c325d1a09.xml, _DXGKARG_CREATECONTEXT, d3dkmddi/DXGKARG_CREATECONTEXT, display.dxgkarg_createcontext"
ms.topic: struct
f1_keywords:
 - "d3dkmddi/DXGKARG_CREATECONTEXT"
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
- DXGKARG_CREATECONTEXT
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGKARG_CREATECONTEXT
---

# _DXGKARG_CREATECONTEXT structure


## -description


The DXGKARG_CREATECONTEXT structure describes parameters to create a device context.


## -struct-fields




### -field hContext

[out] A handle to the context that a display miniport driver returns from a call to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_createcontext">DxgkDdiCreateContext</a> function. This handle represents the context in subsequent calls to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_present">DxgkDdiPresent</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_render">DxgkDdiRender</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_destroycontext">DxgkDdiDestroyContext</a> functions.


### -field NodeOrdinal

[in] The node that the context is created for.


### -field EngineAffinity

[in] The engine within the node that <b>NodeOrdinal</b> specifies that the context is created for. 


### -field Flags

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_createcontextflags">DXGK_CREATECONTEXTFLAGS</a> structure that identifies how to create the context.


### -field pPrivateDriverData

[in] A pointer to a block of private data that is passed from the user-mode display driver to the display miniport driver. 


### -field PrivateDriverDataSize

[in] The size, in bytes, of the private data that <b>pPrivateDriverData</b> points to.


### -field ContextInfo

[out] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_contextinfo">DXGK_CONTEXTINFO</a> structure that the display miniport driver populates to describe the device context.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_contextinfo">DXGK_CONTEXTINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_createcontextflags">DXGK_CREATECONTEXTFLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_createcontext">DxgkDdiCreateContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_destroycontext">DxgkDdiDestroyContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_present">DxgkDdiPresent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_render">DxgkDdiRender</a>
 

 

