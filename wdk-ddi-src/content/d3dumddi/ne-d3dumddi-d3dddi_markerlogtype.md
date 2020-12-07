---
UID: NE:d3dumddi.D3DDDI_MARKERLOGTYPE
title: D3DDDI_MARKERLOGTYPE (d3dumddi.h)
description: Indicates the type of marker in the Event Tracing for Windows (ETW) log that the user-mode display driver supports.
old-location: display\d3dddi_markerlogtype.htm
tech.root: display
ms.date: 03/24/2020
keywords: ["D3DDDI_MARKERLOGTYPE enumeration"]
ms.keywords: D3DDDIMLT_FT_PROFILE, D3DDDIMLT_NONE, D3DDDIMLT_PROFILE, D3DDDI_MARKERLOGTYPE, D3DDDI_MARKERLOGTYPE enumeration [Display Devices], d3dumddi/D3DDDIMLT_FT_PROFILE, d3dumddi/D3DDDIMLT_NONE, d3dumddi/D3DDDIMLT_PROFILE, d3dumddi/D3DDDI_MARKERLOGTYPE, display.d3dddi_markerlogtype
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
targetos: Windows
req.typenames: D3DDDI_MARKERLOGTYPE
f1_keywords:
 - D3DDDI_MARKERLOGTYPE
 - d3dumddi/D3DDDI_MARKERLOGTYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dumddi.h
api_name:
 - D3DDDI_MARKERLOGTYPE
---

# D3DDDI_MARKERLOGTYPE enumeration


## -description

Indicates the type of marker in the Event Tracing for Windows (ETW) log that the user-mode display driver supports.

## -enum-fields

### -field D3DDDIMLT_NONE

No marker type is supported. In this case, the marker type of submitted commands must be [**D3DDDI_MARKERTYPE**](./ne-d3dumddi-d3dddi_markertype.md).**D3DDDIMT_NONE**.

### -field D3DDDIMLT_PROFILE

The context submits GPU work for single-threaded user-mode DDIs. In this case, each time stamp denotes the end of GPU work.

### -field D3DDDIMLT_FT_PROFILE

The context submits GPU work for free-threaded user-mode DDIs. In this case, the driver must have set the **Caps** member of the [**D3D11DDI_THREADING_CAPS**](../d3d10umddi/ns-d3d10umddi-d3d11ddi_threading_caps.md) structure to **D3D11DDICAPS_FREETHREADED**.

### -field D3DDDIMLT_BATCHED

The driver is submitting data that may correspond to multiple command lists in a single submission. If the D3D12 runtime calls [**ExecuteCommandLists**](/windows/win32/api/d3d12/nf-d3d12-id3d12commandqueue-executecommandlists) with multiple command lists, the driver must use the batched marker mode when submitting history buffers.

## -see-also

[**D3D11DDI_THREADING_CAPS**](../d3d10umddi/ns-d3d10umddi-d3d11ddi_threading_caps.md)

[**D3DDDI_MARKERTYPE**](./ne-d3dumddi-d3dddi_markertype.md)

[**ExecuteCommandLists**](/windows/win32/api/d3d12/nf-d3d12-id3d12commandqueue-executecommandlists)
