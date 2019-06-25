---
UID: NC:d3dumddi.PFND3DDDI_CHECKMULTIPLANEOVERLAYSUPPORT
title: PFND3DDDI_CHECKMULTIPLANEOVERLAYSUPPORT (d3dumddi.h)
description: Called by the Microsoft Direct3D runtime to check the details on hardware support for multiplane overlays.
old-location: display\pfncheckmultiplaneoverlaysupport__d3d_.htm
tech.root: display
ms.assetid: A439E695-D374-439A-8A69-6D4E247FF134
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_CHECKMULTIPLANEOVERLAYSUPPORT, PFND3DDDI_CHECKMULTIPLANEOVERLAYSUPPORT (D3D) callback, d3dumddi/pfnCheckMultiPlaneOverlaySupport, display.pfncheckmultiplaneoverlaysupport__d3d_, pfnCheckMultiPlaneOverlaySupport, pfnCheckMultiPlaneOverlaySupport callback function [Display Devices]
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
- UserDefined
api_location:
- D3dumddi.h
api_name:
- pfnCheckMultiPlaneOverlaySupport
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_CHECKMULTIPLANEOVERLAYSUPPORT callback function


## -description


Called by the Microsoft Direct3D runtime to check the details on hardware support for multiplane overlays.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).




### -param *

*pSupport* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_checkmultiplaneoverlaysupport">D3DDDIARG_CHECKMULTIPLANEOVERLAYSUPPORT</a> structure that provides details on hardware support for multiplane overlays.


## -returns



If this routine succeeds, it returns <b>S_OK</b>. Otherwise, it returns an <b>HRESULT</b> error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_checkmultiplaneoverlaysupport">D3DDDIARG_CHECKMULTIPLANEOVERLAYSUPPORT</a>
 

 

