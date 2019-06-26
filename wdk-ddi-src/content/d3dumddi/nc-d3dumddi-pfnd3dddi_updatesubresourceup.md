---
UID: NC:d3dumddi.PFND3DDDI_UPDATESUBRESOURCEUP
title: PFND3DDDI_UPDATESUBRESOURCEUP (d3dumddi.h)
description: Called by the Microsoft Direct3D runtime to update a destination subresource region from a source system-memory region. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.
old-location: display\pfnupdatesubresourceup.htm
tech.root: display
ms.assetid: 5AF55FED-6FD6-41BE-A743-1E9D0EA51C9C
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_UPDATESUBRESOURCEUP, PFND3DDDI_UPDATESUBRESOURCEUP callback, d3dumddi/pfnUpdateSubresourceUP, display.pfnupdatesubresourceup, pfnUpdateSubresourceUP, pfnUpdateSubresourceUP callback function [Display Devices]
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
- pfnUpdateSubresourceUP
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_UPDATESUBRESOURCEUP callback function


## -description


Called by the Microsoft Direct3D runtime to update a destination subresource region from a source system-memory region. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).




### -param *

*pCounterInfo* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-d3dddiarg_updatesubresourceup">D3DDDIARG_UPDATESUBRESOURCEUP</a> structure that describes how to update a destination subresource region from a source system-memory region.


## -returns



If this routine succeeds, it returns <b>S_OK</b>. Otherwise, it returns an <b>HRESULT</b> error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-d3dddiarg_updatesubresourceup">D3DDDIARG_UPDATESUBRESOURCEUP</a>
 

 

