---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_GETRESOURCELAYOUT
title: PFND3DWDDM2_0DDI_GETRESOURCELAYOUT
author: windows-driver-content
description: The pfnGetResourceLayout callback function supports getting resource layout information.
old-location: display\pfnd3dwddm2_0ddi_getresourcelayout.htm
old-project: display
ms.assetid: 0158F1B4-AA6E-41F9-BAEF-A3C688758205
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.pfnd3dwddm2_0ddi_getresourcelayout, pfnGetResourceLayout callback function [Display Devices], pfnGetResourceLayout, PFND3DWDDM2_0DDI_GETRESOURCELAYOUT, PFND3DWDDM2_0DDI_GETRESOURCELAYOUT, d3d10umddi/pfnGetResourceLayout
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3d10umddi.h
apiname:
-	pfnGetResourceLayout
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3DWDDM2_0DDI_GETRESOURCELAYOUT callback


## -description


The <i>pfnGetResourceLayout</i> callback function supports getting resource layout information. 


## -prototype


````
PFND3DWDDM2_0DDI_GETRESOURCELAYOUT pfnGetResourceLayout;

VOID APIENTRY* pfnGetResourceLayout(
            D3D10DDI_HDEVICE                                            hDevice,
            D3D10DDI_HRESOURCE                                          hResource,
            UINT                                                        SubresourceCount,
  _Out_     D3DKMT_HANDLE                                               *Handle,
  _Out_     D3DWDDM2_0DDI_TEXTURE_LAYOUT                                *TextureLayout,
  _Out_     UINT                                                        *pMipLevelSwizzleTransition,
  _Out_opt_ _writes_(SubresourceCount) D3DWDDM2_0DDI_SUBRESOURCE_LAYOUT *SubresourceLayout
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param D3D10DDI_HRESOURCE


### -param SubresourceCount

The subresource count.


### -param *








### -param *pMipLevelSwizzleTransition [out]

A pointer to a MIP level swizzle transition. 


#### - hDevice

A device handle.


#### - hResource

A resource handle. 


#### - Handle [out]

A kernel handle.


#### - TextureLayout [out]

A pointer to a texture layout.


#### - SubresourceLayout [out, optional]

A pointer to the subresource layout.


## -returns



This callback function does not return a value.



