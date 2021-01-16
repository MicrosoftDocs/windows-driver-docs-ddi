---
UID: NS:d3dumddi._D3DDDIARG_RESOLVESHAREDRESOURCE
title: _D3DDDIARG_RESOLVESHAREDRESOURCE (d3dumddi.h)
description: The D3DDDIARG_RESOLVESHAREDRESOURCE structure specifies the resource that the user-mode display driver's ResolveSharedResource function uses as a synchronized shared surface or a GDI interoperable surface.
old-location: display\d3dddiarg_resolvesharedresource.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDIARG_RESOLVESHAREDRESOURCE structure"]
ms.keywords: D3DDDIARG_RESOLVESHAREDRESOURCE, D3DDDIARG_RESOLVESHAREDRESOURCE structure [Display Devices], UMDisplayDriver_param_Structs_94131b1d-aa0e-4d9a-92b5-baca06cf8247.xml, _D3DDDIARG_RESOLVESHAREDRESOURCE, d3dumddi/D3DDDIARG_RESOLVESHAREDRESOURCE, display.d3dddiarg_resolvesharedresource
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_RESOLVESHAREDRESOURCE is supported beginning with the Windows 7 operating system.
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
req.typenames: D3DDDIARG_RESOLVESHAREDRESOURCE
f1_keywords:
 - _D3DDDIARG_RESOLVESHAREDRESOURCE
 - d3dumddi/_D3DDDIARG_RESOLVESHAREDRESOURCE
 - D3DDDIARG_RESOLVESHAREDRESOURCE
 - d3dumddi/D3DDDIARG_RESOLVESHAREDRESOURCE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _D3DDDIARG_RESOLVESHAREDRESOURCE
 - D3DDDIARG_RESOLVESHAREDRESOURCE
---

# _D3DDDIARG_RESOLVESHAREDRESOURCE structure


## -description

The D3DDDIARG_RESOLVESHAREDRESOURCE structure specifies the resource that the user-mode display driver's <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_resolvesharedresource">ResolveSharedResource</a> function uses as a synchronized shared surface or a GDI interoperable surface.

## -struct-fields

### -field hResource

[in] A handle to the surface that the driver uses as a shared surface or in GDI interoperability.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_resolvesharedresource">ResolveSharedResource</a>

