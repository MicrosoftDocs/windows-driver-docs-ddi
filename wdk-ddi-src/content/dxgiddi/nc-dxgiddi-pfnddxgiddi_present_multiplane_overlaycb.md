---
UID: NC:dxgiddi.PFNDDXGIDDI_PRESENT_MULTIPLANE_OVERLAYCB
title: PFNDDXGIDDI_PRESENT_MULTIPLANE_OVERLAYCB (dxgiddi.h)
description: Called by the Microsoft DirectX Graphics Infrastructure (DXGI) runtime to notify the user-mode display driver that an application finished rendering and requests that the driver display the source surface by either copying or flipping or that the driver perform a color-fill operation. 
old-location: display\pfnpresentmultiplaneoverlay__dxgi_.htm
tech.root: display
ms.assetid: C6EB96AC-0D5B-4D75-9B44-B1744F6A4360
ms.date: 05/10/2018
ms.keywords: PFNDDXGIDDI_PRESENT_MULTIPLANE_OVERLAYCB, PFNDDXGIDDI_PRESENT_MULTIPLANE_OVERLAYCB callback, display.pfnpresentmultiplaneoverlay__dxgi_, dxgiddi/pfnPresentMultiPlaneOverlayCb, pfnPresentMultiPlaneOverlayCb, pfnPresentMultiPlaneOverlayCb callback function [Display Devices]
ms.topic: callback
f1_keywords:
 - "dxgiddi/pfnPresentMultiPlaneOverlayCb"
req.header: dxgiddi.h
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
- Dxgiddi.h
api_name:
- pfnPresentMultiPlaneOverlayCb
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNDDXGIDDI_PRESENT_MULTIPLANE_OVERLAYCB callback function


## -description


Called by the Microsoft DirectX Graphics Infrastructure (DXGI) runtime to notify  the user-mode display driver that an application finished rendering and requests that the driver display the source surface by either copying or flipping or that the driver perform a color-fill operation. Must be implemented by Windows Display Driver Model (WDDM) 1.3 or later drivers that support multiplane overlays.


## -parameters




### -param hDevice

A handle to a display device (graphics context).

### -param *


**pPresentDXGI**

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dxgiddi/ns-dxgiddi-_dxgi_ddi_arg_presentmultiplaneoverlay">DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY</a> structure that describes how to display to the destination surface. 


## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



When the user-mode display driver successfully completes its processing of a call to this function, it presents the source surface to the display by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dxgiddi/nc-dxgiddi-pfnddxgiddi_present_multiplane_overlaycb">pfnPresentMultiPlaneOverlayCb (DXGI)</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dxgiddi/ns-dxgiddi-_dxgi_ddi_arg_presentmultiplaneoverlay">DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dxgiddi/nc-dxgiddi-pfnddxgiddi_present_multiplane_overlaycb">pfnPresentMultiPlaneOverlayCb (DXGI)</a>
 

 

