---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_GETRESOURCELAYOUT
title: PFND3DWDDM2_0DDI_GETRESOURCELAYOUT
author: windows-driver-content
description: The pfnGetResourceLayout callback function supports getting resource layout information.
old-location: display\pfnd3dwddm2_0ddi_getresourcelayout.htm
old-project: display
ms.assetid: 0158F1B4-AA6E-41F9-BAEF-A3C688758205
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _SETRESULT_INFO, *PSETRESULT_INFO, SETRESULT_INFO
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
req.alt-api: pfnGetResourceLayout
req.alt-loc: d3d10umddi.h
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
req.typenames: *PSETRESULT_INFO, SETRESULT_INFO
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

### -param hDevice 

A device handle.


### -param hResource 

A resource handle. 


### -param SubresourceCount 

The subresource count.


### -param Handle [out]

A kernel handle.


### -param TextureLayout [out]

A pointer to a texture layout.


### -param pMipLevelSwizzleTransition [out]

A pointer to a MIP level swizzle transition. 


### -param SubresourceLayout [out, optional]

A pointer to the subresource layout.


## -returns
This callback function does not return a value.


## -remarks
