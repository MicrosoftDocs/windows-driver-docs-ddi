---
UID: NC:d3d10umddi.PFND3D11_1DDI_DISCARD
title: PFND3D11_1DDI_DISCARD (d3d10umddi.h)
description: Discards (evicts) an allocation from video display memory. Implemented by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location: display\discard_d3d11_1_.htm
ms.assetid: d94234ab-712b-4449-96de-16b9e310d250
ms.date: 05/10/2018
ms.keywords: Discard(D3D11_1), Discard(D3D11_1) callback function [Display Devices], PFND3D11_1DDI_DISCARD, PFND3D11_1DDI_DISCARD callback, d3d10umddi/Discard(D3D11_1), display.discard_d3d11_1_, display.pfndiscard
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
tech.root: display
req.typenames: 
f1_keywords:
 - "d3d10umddi/Discard(D3D11_1)"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - Discard(D3D11_1)
product:
 - Windows
---

# PFND3D11_1DDI_DISCARD callback function

## -description

Discards (evicts) an allocation from video display memory. Implemented by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param HandleType

A value, of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11ddi_handletype">D3D11DDI_HANDLETYPE</a>, that identifies the context handle type.

### -param hResourceOrView

A pointer to a handle to the resource or to the view that is to be discarded.

### -param Arg4

*pRects* [in, optional]

An optional array of <a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-tagrect">RECT</a> structures for the rectangles in the resource view to discard. If <b>NULL</b>, the <i>Discard(D3D11_1)</i> function discards the entire surface.

### -param NumRects

The number of rectangles in the array that the  <i>pRects</i> parameter specifies.

## -remarks

The D3D10_DDI_RECT structure is defined as a <a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-tagrect">RECT</a> structure.

```cpp
typedef RECT D3D10_DDI_RECT;
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11ddi_handletype">D3D11DDI_HANDLETYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_devicefuncs">D3D11_1DDI_DEVICEFUNCS</a>

