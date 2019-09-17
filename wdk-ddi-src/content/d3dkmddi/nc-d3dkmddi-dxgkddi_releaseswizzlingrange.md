---
UID: NC:d3dkmddi.DXGKDDI_RELEASESWIZZLINGRANGE
title: DXGKDDI_RELEASESWIZZLINGRANGE (d3dkmddi.h)
description: The DxgkDdiReleaseSwizzlingRange function releases a swizzling range that the DxgkDdiAcquireSwizzlingRange function previously set up.
old-location: display\dxgkddireleaseswizzlingrange.htm
ms.assetid: 6c583a48-baa4-429f-b2fc-5f86859617cc
ms.date: 05/10/2018
ms.keywords: DXGKDDI_RELEASESWIZZLINGRANGE, DXGKDDI_RELEASESWIZZLINGRANGE callback, DmFunctions_7dab2ff4-4f37-4b56-a15c-29dcf54f8b8d.xml, DxgkDdiReleaseSwizzlingRange, DxgkDdiReleaseSwizzlingRange callback function [Display Devices], d3dkmddi/DxgkDdiReleaseSwizzlingRange, display.dxgkddireleaseswizzlingrange
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3dkmddi/DxgkDdiReleaseSwizzlingRange"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DxgkDdiReleaseSwizzlingRange
product:
 - Windows
---

# DXGKDDI_RELEASESWIZZLINGRANGE callback function

## -description

The <i>DxgkDdiReleaseSwizzlingRange</i> function releases a swizzling range that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_acquireswizzlingrange">DxgkDdiAcquireSwizzlingRange</a> function previously set up.

## -parameters

### -param hAdapter

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function.

### -param pReleaseSwizzlingRange

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_releaseswizzlingrange">DXGKARG_RELEASESWIZZLINGRANGE</a> structure that contains information for releasing the swizzling range.

## -returns

<i>DxgkDdiReleaseSwizzlingRange</i> returns STATUS_SUCCESS, or an appropriate error result if the swizzling range is not successfully released.

## -remarks

The <i>DxgkDdiReleaseSwizzlingRange</i> function is typically called when the specified allocation (that is, the <b>hAllocation</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_releaseswizzlingrange">DXGKARG_RELEASESWIZZLINGRANGE</a> structure that the <i>pReleaseSwizzlingRange</i> parameter points to) is evicted or destroyed, or when another allocation requires the swizzling range that the <b>RangeId</b> member of DXGKARG_RELEASESWIZZLINGRANGE specifies.

If the specified allocation is currently associated with multiple swizzling ranges (through calls to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_acquireswizzlingrange">DxgkDdiAcquireSwizzlingRange</a> function), the display miniport driver should release only the swizzling range that the <b>RangeId</b> member of DXGKARG_RELEASESWIZZLINGRANGE specifies. If the display miniport driver releases all of the swizzling ranges that are associated with the allocation, random corruption in the allocation might result because an application might currently be using one or more of the swizzling ranges.

The driver must use memory-mapped I/O (MMIO) to set up a swizzling range. These swizzling-range accesses must not interfere with the execution of the GPU (that is, the GPU must not be idle when <i>DxgkDdiReleaseSwizzlingRange</i> is called). 

All calls to <i>DxgkDdiReleaseSwizzlingRange</i> are serialized among themselves but not with any other device driver interface (DDI) function.

<i>DxgkDdiReleaseSwizzlingRange</i> should be made pageable.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_releaseswizzlingrange">DXGKARG_RELEASESWIZZLINGRANGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_acquireswizzlingrange">DxgkDdiAcquireSwizzlingRange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>

