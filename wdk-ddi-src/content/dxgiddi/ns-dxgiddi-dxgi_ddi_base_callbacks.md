---
UID: NS:dxgiddi.DXGI_DDI_BASE_CALLBACKS
title: DXGI_DDI_BASE_CALLBACKS (dxgiddi.h)
description: The DXGI_DDI_BASE_CALLBACKS structure contains pointers to Microsoft Direct3D 10 runtime callback functions that the user-mode display driver can use.
old-location: display\dxgi_ddi_base_callbacks.htm
tech.root: display
ms.assetid: dd1690e2-7eef-4086-a3e1-9ca456b79a6f
ms.date: 02/26/2018
ms.keywords: DXGI_DDI_BASE_CALLBACKS, DXGI_DDI_BASE_CALLBACKS structure [Display Devices], UMDisplayDriver_Dx10param_Structs_6622df62-429f-438b-aa1a-61fd7fb8df65.xml, display.dxgi_ddi_base_callbacks, dxgiddi/DXGI_DDI_BASE_CALLBACKS
f1_keywords:
 - "dxgiddi/DXGI_DDI_BASE_CALLBACKS"
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
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
- dxgiddi.h
api_name:
- DXGI_DDI_BASE_CALLBACKS
product: 
- Windows
targetos: Windows
req.typenames: DXGI_DDI_BASE_CALLBACKS
---

# DXGI_DDI_BASE_CALLBACKS structure


## -description


The DXGI_DDI_BASE_CALLBACKS structure contains pointers to Microsoft Direct3D 10 runtime callback functions that the user-mode display driver can use.


## -struct-fields




### -field pfnPresentCb

A pointer to the <a href="..\dxgiddi\nc-dxgiddi-pfnddxgiddi_presentcb.md">pfnPresentCbDXGI</a> function.


### -field pfnPresentMultiplaneOverlayCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/nc-dxgiddi-pfnddxgiddi_present_multiplane_overlaycb">pfnPresentMultiPlaneOverlayCb (DXGI)</a> function. Supported starting with Windows 8.1.


### -field pfnPresentMultiplaneOverlay1Cb

A pointer to the PFNDDXGIDDI_PRESENT_MULTIPLANE_OVERLAY1CB function. Supported starting with WDDM 2.1.

### -field pfnSubmitPresentBltToHwQueueCb

A pointer to the [PFNDDXGIDDI_SUBMITPRESENTBLTTOHWQUEUECB](../dxgiddi/nc-dxgiddi-pfnddxgiddi_submitpresentblttohwqueuecb.md) function. Supported starting with WDDM 2.4.

### -field pfnSubmitPresentToHwQueueCb

A pointer to the [PFNDDXGIDDI_SUBMITPRESENTTOHWQUEUECB](../dxgiddi/nc-dxgiddi-pfnddxgiddi_submitpresenttohwqueuecb.md) function. Supported starting with WDDM 2.5.

## -see-also

<a href="..\dxgiddi\nc-dxgiddi-pfnddxgiddi_presentcb.md">pfnPresentCbDXGI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/nc-dxgiddi-pfnddxgiddi_present_multiplane_overlaycb">pfnPresentMultiPlaneOverlayCb (DXGI)</a>



<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_base_args.md">DXGI_DDI_BASE_ARGS</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdevice.md">D3D10DDIARG_CREATEDEVICE</a>



 

 


