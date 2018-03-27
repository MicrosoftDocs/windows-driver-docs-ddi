---
UID: NS:dispmprt._DXGK_DISPLAY_OWNERSHIP_FLAGS
title: "_DXGK_DISPLAY_OWNERSHIP_FLAGS"
author: windows-driver-content
description: Structure filled in by OS upon successful completion of the DxgkCbAcquirePostDisplayOwnership2 callback to provide information about the display state a driver is inheriting.
old-location: display\dxgk_display_ownership_flags.htm
old-project: display
ms.assetid: F5CA04FD-5E2A-4C68-97CF-F3D425A958AA
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDXGK_DISPLAY_OWNERSHIP_FLAGS, DXGK_DISPLAY_OWNERSHIP_FLAGS, DXGK_DISPLAY_OWNERSHIP_FLAGS structure [Display Devices], PDXGK_DISPLAY_OWNERSHIP_FLAGS, PDXGK_DISPLAY_OWNERSHIP_FLAGS structure pointer [Display Devices], _DXGK_DISPLAY_OWNERSHIP_FLAGS, display.dxgk_display_ownership_flags, dispmprt/DXGK_DISPLAY_OWNERSHIP_FLAGS, dispmprt/PDXGK_DISPLAY_OWNERSHIP_FLAGS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dispmprt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	dispmprt.h
api_name:
-	DXGK_DISPLAY_OWNERSHIP_FLAGS
product: Windows
targetos: Windows
req.typenames: DXGK_DISPLAY_OWNERSHIP_FLAGS, *PDXGK_DISPLAY_OWNERSHIP_FLAGS
---

# _DXGK_DISPLAY_OWNERSHIP_FLAGS structure


## -description


Structure filled in by OS upon successful completion of the DxgkCbAcquirePostDisplayOwnership2 callback to provide information about the display state a driver is inheriting.


## -struct-fields




### -field FrameBufferState

Value indicating the state of the frame buffer.  See definition of DXGK_FRAMEBUFFER_STATE enum for details.  


#### - Value

The value used to operate over the combined bitfields.

