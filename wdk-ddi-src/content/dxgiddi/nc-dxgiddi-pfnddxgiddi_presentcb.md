---
UID: NC:dxgiddi.PFNDDXGIDDI_PRESENTCB
title: PFNDDXGIDDI_PRESENTCB (dxgiddi.h)
description: Learn more about the PFNDDXGIDDI_PRESENTCB callback function.
tech.root: display
ms.date: 10/12/2023
keywords: ["PFNDDXGIDDI_PRESENTCB callback function"]
ms.keywords: PFNDDXGIDDI_PRESENTCB, PFNDDXGIDDI_PRESENTCB callback, d3d10state_functions_22004360-a0a0-4d54-ac0e-d7fadec2bf67.xml, display.pfnpresentcbdxgi, dxgiddi/pfnPresentCbDXGI, pfnPresentCbDXGI, pfnPresentCbDXGI callback function [Display Devices]
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows Vista
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
 - PFNDDXGIDDI_PRESENTCB
---

# PFNDDXGIDDI_PRESENTCB callback function

## -description

The **pfnPresentCbDXGI** function copies content from a source allocation to a destination allocation.

## -parameters

### -param hDevice

[in] A handle to a display device (graphics context).

### -param unnamedParam2

[in] **pPresentData** is a pointer to a [**DXGIDDICB_PRESENT**](ns-dxgiddi-dxgiddicb_present.md) structure that describes the source and destination allocations that content is copied from and to.

## -returns

**pfnPresentCbDXGI** returns one of the following values:

| **Return code** | **Description** |
|:--|:--|
| **S_OK** | Content was successfully copied. |
| **E_OUTOFMEMORY** | pfnPresentCbDXGI could not complete because of insufficient memory. |
| **E_INVALIDARG** | Parameters were validated and determined to be incorrect. |

## -remarks

The **pDXGIContext** member of the [**DXGIDDICB_PRESENT**](ns-dxgiddi-dxgiddicb_present.md) structure that the **pPresentData** parameter points to is an opaque communication mechanism. The runtime passes this DXGI context to the driver in the **pDXGIContext** member of the [**DXGI_DDI_ARG_PRESENT**](ns-dxgiddi-dxgi_ddi_arg_present.md) structure when the runtime calls the driver's [**PresentDXGI**](ns-dxgiddi-dxgi_ddi_base_functions.md) function. The driver should copy this DXGI context unchanged to the **pDXGIContext** member of DXGIDDICB_PRESENT when the driver calls **pfnPresentCbDXGI**.

The Direct3D runtime restricts the set of formats that can be presented through a bit-block transfer (bitblt) operation. For more information about the restrictions, see the Remarks section of the [**BltDXGI**](ns-dxgiddi-dxgi_ddi_base_functions.md) reference page.

## -see-also

[**BltDXGI**](ns-dxgiddi-dxgi_ddi_base_functions.md)

[**CreateDevice(D3D10)**](../d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice.md)

[**DXGIDDICB_PRESENT**](ns-dxgiddi-dxgiddicb_present.md)

[**DXGI_DDI_ARG_PRESENT**](ns-dxgiddi-dxgi_ddi_arg_present.md)

[**DXGI_DDI_BASE_CALLBACKS**](ns-dxgiddi-dxgi_ddi_base_callbacks.md)

[**PresentDXGI**](ns-dxgiddi-dxgi_ddi_base_functions.md)
