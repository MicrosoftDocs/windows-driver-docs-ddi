---
UID: NE:d3d10umddi.D3D11_1_DDI_FLUSH_FLAGS
title: D3D11_1_DDI_FLUSH_FLAGS
author: windows-driver-content
description: In calls to the Flush(D3D11_1) function, indicates whether the driver should continue to submit command buffers. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location: display\d3d11_1_ddi_flush_flags.htm
old-project: display
ms.assetid: 0786c63d-ce4e-47c1-b54f-47f1da90cb64
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D11_1DDI_FLUSH_UNLESS_NO_COMMANDS, D3D11_1_DDI_FLUSH_FLAGS, D3D11_1_DDI_FLUSH_FLAGS enumeration [Display Devices], D3DWDDM1_3DDI_TRIM_MEMORY, d3d10umddi/D3D11_1DDI_FLUSH_UNLESS_NO_COMMANDS, d3d10umddi/D3D11_1_DDI_FLUSH_FLAGS, d3d10umddi/D3DWDDM1_3DDI_TRIM_MEMORY, display.d3d11_1_ddi_flush_flags
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3D11_1_DDI_FLUSH_FLAGS
product:
- Windows
targetos: Windows
req.typenames: D3D11_1_DDI_FLUSH_FLAGS
---

# D3D11_1_DDI_FLUSH_FLAGS enumeration


## -description


In calls to the <a href="https://msdn.microsoft.com/6f4bda19-2d51-4058-ba68-cbb5deb44a54">Flush(D3D11_1)</a> function,  indicates whether the driver should continue to submit command buffers. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.


## -enum-fields




### -field D3D11_1DDI_FLUSH_UNLESS_NO_COMMANDS

The driver should not submit command buffers if there have been no new commands since the last time the driver submitted a command buffer.


### -field D3DWDDM1_3DDI_TRIM_MEMORY

The driver should free as much memory as it can. However, it should not free any memory that the driver requires to continue operating. Using this constant value therefore should not introduce new opportunities to run out of memory.

The driver must no longer call <a href="https://msdn.microsoft.com/8BB6A7A3-E102-4069-BFC2-9605DDE9F020">Video memory offer and reclaim</a> DDIs on the memory that it frees.

Supported starting with Windows 8.1 for WDDM 1.3 and later user-mode display drivers.


## -see-also




<a href="https://msdn.microsoft.com/6f4bda19-2d51-4058-ba68-cbb5deb44a54">Flush(D3D11_1)</a>
 

 

