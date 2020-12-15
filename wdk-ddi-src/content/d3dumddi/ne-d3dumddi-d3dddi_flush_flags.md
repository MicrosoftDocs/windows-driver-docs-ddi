---
UID: NE:d3dumddi.D3DDDI_FLUSH_FLAGS
title: D3DDDI_FLUSH_FLAGS (d3dumddi.h)
description: In calls to the pfnFlush1 function, indicates whether the driver should free as much memory as possible. Used by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.
old-location: display\d3dddi_flush_flags.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDI_FLUSH_FLAGS enumeration"]
ms.keywords: D3DDDI_FLUSH_FLAGS, D3DDDI_FLUSH_FLAGS enumeration [Display Devices], D3DDDI_TRIM_MEMORY, d3dumddi/D3DDDI_FLUSH_FLAGS, d3dumddi/D3DDDI_TRIM_MEMORY, display.d3dddi_flush_flags
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
req.typenames: D3DDDI_FLUSH_FLAGS
f1_keywords:
 - D3DDDI_FLUSH_FLAGS
 - d3dumddi/D3DDDI_FLUSH_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dumddi.h
api_name:
 - D3DDDI_FLUSH_FLAGS
---

# D3DDDI_FLUSH_FLAGS enumeration


## -description

In calls to the <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_flush1">pfnFlush1</a> function,  indicates whether the driver should free as much memory as possible. Used by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.

## -enum-fields

### -field D3DDDI_TRIM_MEMORY

The driver should free as much memory as it can. However, it should not free any memory that the driver requires to continue operating. Using this constant value therefore should not introduce new opportunities to run out of memory.

The driver must no longer call <a href="/windows-hardware/drivers/display/video-memory-offer-and-reclaim">Video memory offer and reclaim</a> DDIs on the memory that it frees.

Supported starting with Windows 8.1.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_flush1">pfnFlush1</a>
