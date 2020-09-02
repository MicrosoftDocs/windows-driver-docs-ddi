---
UID: NC:dxgiddi.PFNDDXGIDDI_PRESENTCB
title: PFNDDXGIDDI_PRESENTCB (dxgiddi.h)
description: The pfnPresentCbDXGI function copies content from a source allocation to a destination allocation.
old-location: display\pfnpresentcbdxgi.htm
tech.root: display
ms.assetid: eefb8f2c-e460-4f9c-851d-9a97dbcd728f
ms.date: 05/10/2018
keywords: ["PFNDDXGIDDI_PRESENTCB callback function"]
ms.keywords: PFNDDXGIDDI_PRESENTCB, PFNDDXGIDDI_PRESENTCB callback, d3d10state_functions_22004360-a0a0-4d54-ac0e-d7fadec2bf67.xml, display.pfnpresentcbdxgi, dxgiddi/pfnPresentCbDXGI, pfnPresentCbDXGI, pfnPresentCbDXGI callback function [Display Devices]
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PFNDDXGIDDI_PRESENTCB
 - dxgiddi/PFNDDXGIDDI_PRESENTCB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dxgiddi.h
api_name:
 - pfnPresentCbDXGI
---

# PFNDDXGIDDI_PRESENTCB callback function


## -description

The <b>pfnPresentCbDXGI</b> function copies content from a source allocation to a destination allocation.

## -parameters

### -param hDevice 

[in] A handle to a display device (graphics context).

### -param 

*pPresentData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgiddicb_present">DXGIDDICB_PRESENT</a> structure that describes the source and destination allocations that content is copied from and to.

## -returns

<b>pfnPresentCbDXGI</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | Content was successfully copied. | 
| **E_OUTOFMEMORY** | pfnPresentCbDXGI could not complete because of insufficient memory. | 
| **E_INVALIDARG** | Parameters were validated and determined to be incorrect. |

## -remarks

The <b>pDXGIContext</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgiddicb_present">DXGIDDICB_PRESENT</a> structure that the <i>pPresentData</i> parameter points to is an opaque communication mechanism. The runtime passes this DXGI context to the driver in the <b>pDXGIContext</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_present">DXGI_DDI_ARG_PRESENT</a> structure when the runtime calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">PresentDXGI</a> function. The driver should copy this DXGI context unchanged to the <b>pDXGIContext</b> member of DXGIDDICB_PRESENT when the driver calls <b>pfnPresentCbDXGI</b>. 

The Direct3D runtime restricts the set of formats that can be presented through a bit-block transfer (bitblt) operation. For more information about the restrictions, see the Remarks section of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">BltDXGI</a> reference page.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">BltDXGI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgiddicb_present">DXGIDDICB_PRESENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_present">DXGI_DDI_ARG_PRESENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_callbacks">DXGI_DDI_BASE_CALLBACKS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">PresentDXGI</a>

