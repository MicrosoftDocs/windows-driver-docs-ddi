---
UID: NE:d3d10umddi.D3D11_1_DDI_FLUSH_FLAGS
title: D3D11_1_DDI_FLUSH_FLAGS (d3d10umddi.h)
description: In calls to the Flush(D3D11_1) function, indicates whether the driver should continue to submit command buffers. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location: display\d3d11_1_ddi_flush_flags.htm
ms.assetid: 0786c63d-ce4e-47c1-b54f-47f1da90cb64
ms.date: 05/10/2018
ms.keywords: D3D11_1DDI_FLUSH_UNLESS_NO_COMMANDS, D3D11_1_DDI_FLUSH_FLAGS, D3D11_1_DDI_FLUSH_FLAGS enumeration [Display Devices], D3DWDDM1_3DDI_TRIM_MEMORY, d3d10umddi/D3D11_1DDI_FLUSH_UNLESS_NO_COMMANDS, d3d10umddi/D3D11_1_DDI_FLUSH_FLAGS, d3d10umddi/D3DWDDM1_3DDI_TRIM_MEMORY, display.d3d11_1_ddi_flush_flags
ms.topic: enum
f1_keywords:
 - "d3d10umddi/D3D11_1_DDI_FLUSH_FLAGS"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d10umddi.h
api_name:
- D3D11_1_DDI_FLUSH_FLAGS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_1_DDI_FLUSH_FLAGS
---

# D3D11_1_DDI_FLUSH_FLAGS enumeration


## -description


In calls to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_flush">Flush(D3D11_1)</a> function,  indicates whether the driver should continue to submit command buffers. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.


## -enum-fields




### -field D3D11_1DDI_FLUSH_UNLESS_NO_COMMANDS

The driver should not submit command buffers if there have been no new commands since the last time the driver submitted a command buffer.


### -field D3DWDDM1_3DDI_TRIM_MEMORY

The driver should free as much memory as it can. However, it should not free any memory that the driver requires to continue operating. Using this constant value therefore should not introduce new opportunities to run out of memory.

The driver must no longer call <a href="https://docs.microsoft.com/windows-hardware/drivers/display/video-memory-offer-and-reclaim">Video memory offer and reclaim</a> DDIs on the memory that it frees.

Supported starting with Windows 8.1 for WDDM 1.3 and later user-mode display drivers.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_flush">Flush(D3D11_1)</a>
 

 

