---
UID: NC:d3dumddi.PFND3DDDI_CHECKMULTIPLANEOVERLAYSUPPORT
title: PFND3DDDI_CHECKMULTIPLANEOVERLAYSUPPORT
author: windows-driver-content
description: Called by the Microsoft Direct3D runtime to check the details on hardware support for multiplane overlays.
old-location: display\pfncheckmultiplaneoverlaysupport__d3d_.htm
old-project: display
ms.assetid: A439E695-D374-439A-8A69-6D4E247FF134
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DDDI_CHECKMULTIPLANEOVERLAYSUPPORT, d3dumddi/pfnCheckMultiPlaneOverlaySupport, display.pfncheckmultiplaneoverlaysupport__d3d_, pfnCheckMultiPlaneOverlaySupport, pfnCheckMultiPlaneOverlaySupport callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3dumddi.h
api_name:
-	pfnCheckMultiPlaneOverlaySupport
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_CHECKMULTIPLANEOVERLAYSUPPORT callback


## -description


Called by the Microsoft Direct3D runtime to check the details on hardware support for multiplane overlays.


## -prototype


````
PFND3DDDI_CHECKMULTIPLANEOVERLAYSUPPORT pfnCheckMultiPlaneOverlaySupport;

_Check_return_ HRESULT APIENTRY* pfnCheckMultiPlaneOverlaySupport(
  _In_    HANDLE                                  hDevice,
  _Inout_ D3DDDIARG_CHECKMULTIPLANEOVERLAYSUPPORT *pSupport
)
{ ... }
````


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).




### -param *








#### - pSupport [in, out]

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_checkmultiplaneoverlaysupport.md">D3DDDIARG_CHECKMULTIPLANEOVERLAYSUPPORT</a> structure that provides details on hardware support for multiplane overlays.


## -returns



If this routine succeeds, it returns <b>S_OK</b>. Otherwise, it returns an <b>HRESULT</b> error code.




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_checkmultiplaneoverlaysupport.md">D3DDDIARG_CHECKMULTIPLANEOVERLAYSUPPORT</a>



 

 


