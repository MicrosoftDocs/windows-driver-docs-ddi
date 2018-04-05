---
UID: NS:dxgiddi.DXGI_DDI_MODE_DESC
title: DXGI_DDI_MODE_DESC
author: windows-driver-content
description: The DXGI_DDI_MODE_DESC structure describes a display mode.
old-location: display\dxgi_ddi_mode_desc.htm
old-project: display
ms.assetid: 9924f914-2812-4953-85d1-9c777404418b
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGI_DDI_MODE_DESC, DXGI_DDI_MODE_DESC structure [Display Devices], UMDisplayDriver_Dx10param_Structs_3687fd3c-7423-47bf-a376-a13b820ee787.xml, display.dxgi_ddi_mode_desc, dxgiddi/DXGI_DDI_MODE_DESC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	dxgiddi.h
api_name:
-	DXGI_DDI_MODE_DESC
product:
- Windows
targetos: Windows
req.typenames: DXGI_DDI_MODE_DESC
---

# DXGI_DDI_MODE_DESC structure


## -description


The DXGI_DDI_MODE_DESC structure describes a display mode.


## -struct-fields




### -field Width

[out] The screen width of the display mode, in pixels.


### -field Height

[out] The screen height of the display mode, in pixels.


### -field Format

[out] A DXGI_FORMAT-typed value that indicates the pixel format of the display mode.


### -field RefreshRate

[out] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff557516">DXGI_DDI_RATIONAL</a> structure that indicates the refresh rate of the display mode.


### -field ScanlineOrdering

[out] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff557507">DXGI_DDI_MODE_SCANLINE_ORDER</a>-typed value that indicates how scan lines are ordered in the display mode.


### -field Rotation

[out] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff557502">DXGI_DDI_MODE_ROTATION</a>-typed value that identifies the orientation of the display mode.


### -field Scaling

[out] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff557505">DXGI_DDI_MODE_SCALING</a>-typed value that identifies the scaling of the display mode.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557502">DXGI_DDI_MODE_ROTATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557505">DXGI_DDI_MODE_SCALING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557507">DXGI_DDI_MODE_SCANLINE_ORDER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557511">DXGI_DDI_PRIMARY_DESC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557516">DXGI_DDI_RATIONAL</a>
 

 

