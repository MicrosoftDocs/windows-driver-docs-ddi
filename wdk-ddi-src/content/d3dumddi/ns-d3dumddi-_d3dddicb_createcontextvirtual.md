---
UID: NS:d3dumddi._D3DDDICB_CREATECONTEXTVIRTUAL
title: _D3DDDICB_CREATECONTEXTVIRTUAL (d3dumddi.h)
description: D3DDDICB_CREATECONTEXTVIRTUAL is used with pfnCreateContextVirtualCb to create contexts that support virtual addressing.
old-location: display\d3dddicb_createcontextvirtual.htm
tech.root: display
ms.assetid: 451D1CE2-A50D-4E42-BD93-879503EDE4B5
ms.date: 05/10/2018
ms.keywords: D3DDDICB_CREATECONTEXTVIRTUAL, D3DDDICB_CREATECONTEXTVIRTUAL structure [Display Devices], _D3DDDICB_CREATECONTEXTVIRTUAL, d3dumddi/D3DDDICB_CREATECONTEXTVIRTUAL, display.d3dddicb_createcontextvirtual
f1_keywords:
 - "d3dumddi/D3DDDICB_CREATECONTEXTVIRTUAL"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
- D3DDDICB_CREATECONTEXTVIRTUAL
product:
- Windows
targetos: Windows
req.typenames: D3DDDICB_CREATECONTEXTVIRTUAL
---

# _D3DDDICB_CREATECONTEXTVIRTUAL structure


## -description


<b>D3DDDICB_CREATECONTEXTVIRTUAL</b> is used with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createcontextvirtualcb">pfnCreateContextVirtualCb</a> to create contexts that support virtual addressing.


## -struct-fields




### -field NodeOrdinal

[in] The zero-based index for the node that the context is scheduled on.


### -field EngineAffinity

[in] The zero-based index for the engine, within the node that <b>NodeOrdinal</b> specifies, that the context can run in.


### -field Flags

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_createcontextflags">D3DDDI_CREATECONTEXTFLAGS</a> structure that indicates, in bit-field flags, how to create the context. 


### -field pPrivateDriverData

[in] A pointer to private data that is passed to a display miniport driver. 


### -field PrivateDriverDataSize

[in] The size, in bytes, of the private data that <b>pPrivateDriverData</b> points to.


### -field hContext

[out] A handle to the context that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createcontextvirtualcb">pfnCreateContextVirtualCb</a> function creates. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_createcontextflags">D3DDDI_CREATECONTEXTFLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createcontextvirtualcb">pfnCreateContextVirtualCb</a>
 

 

