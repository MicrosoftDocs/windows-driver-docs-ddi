---
UID: NS:d3dumddi._D3DDDIARG_RESOLVESHAREDRESOURCE
title: _D3DDDIARG_RESOLVESHAREDRESOURCE (d3dumddi.h)
description: The D3DDDIARG_RESOLVESHAREDRESOURCE structure specifies the resource that the user-mode display driver's ResolveSharedResource function uses as a synchronized shared surface or a GDI interoperable surface.
old-location: display\d3dddiarg_resolvesharedresource.htm
tech.root: display
ms.assetid: f8baaa47-9b3a-4a85-8943-0878105bb5fe
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_RESOLVESHAREDRESOURCE, D3DDDIARG_RESOLVESHAREDRESOURCE structure [Display Devices], UMDisplayDriver_param_Structs_94131b1d-aa0e-4d9a-92b5-baca06cf8247.xml, _D3DDDIARG_RESOLVESHAREDRESOURCE, d3dumddi/D3DDDIARG_RESOLVESHAREDRESOURCE, display.d3dddiarg_resolvesharedresource
ms.topic: struct
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- D3DDDIARG_RESOLVESHAREDRESOURCE
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_RESOLVESHAREDRESOURCE
---

# _D3DDDIARG_RESOLVESHAREDRESOURCE structure


## -description


The D3DDDIARG_RESOLVESHAREDRESOURCE structure specifies the resource that the user-mode display driver's <a href="https://msdn.microsoft.com/8ad9130e-bade-4fd2-b345-b6361fd001ef">ResolveSharedResource</a> function uses as a synchronized shared surface or a GDI interoperable surface. 


## -struct-fields




### -field hResource

[in] A handle to the surface that the driver uses as a shared surface or in GDI interoperability. 


## -see-also




<a href="https://msdn.microsoft.com/8ad9130e-bade-4fd2-b345-b6361fd001ef">ResolveSharedResource</a>
 

 

