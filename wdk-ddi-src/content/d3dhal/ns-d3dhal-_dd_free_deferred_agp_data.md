---
UID: NS:d3dhal._DD_FREE_DEFERRED_AGP_DATA
title: "_DD_FREE_DEFERRED_AGP_DATA"
author: windows-driver-content
description: DirectX 8.0 and later versions and NT-based operating systems only. DD_FREE_DEFERRED_AGP_DATA is the data structure pointed to by the lpvData field of DD_GETDRIVERINFODATA for D3DGDI2_TYPE_DEFER_AGP_FREES and D3DGDI2_TYPE_FREE_DEFERRED_AGP notifications.
old-location: display\dd_free_deferred_agp_data.htm
old-project: display
ms.assetid: 38830856-1f66-44d6-9501-9454a31571b7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DD_FREE_DEFERRED_AGP_DATA, DD_FREE_DEFERRED_AGP_DATA structure [Display Devices], _DD_FREE_DEFERRED_AGP_DATA, d3dhal/DD_FREE_DEFERRED_AGP_DATA, d3dstrct_06ad77f0-33c0-4297-a713-d23f0684dbee.xml, display.dd_free_deferred_agp_data
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dhal.h
api_name:
-	DD_FREE_DEFERRED_AGP_DATA
product:
- Windows
targetos: Windows
req.typenames: DD_FREE_DEFERRED_AGP_DATA
---

# _DD_FREE_DEFERRED_AGP_DATA structure


## -description



   DirectX 8.0 and later versions and NT-based operating systems only.
   

DD_FREE_DEFERRED_AGP_DATA is the data structure pointed to by the <b>lpvData</b> field of <a href="https://msdn.microsoft.com/library/windows/hardware/ff551550">DD_GETDRIVERINFODATA</a> for D3DGDI2_TYPE_DEFER_AGP_FREES and D3DGDI2_TYPE_FREE_DEFERRED_AGP notifications.


## -struct-fields




### -field gdi2

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551548">DD_GETDRIVERINFO2DATA</a> structure that contains the <b>GetDriverInfo2</b> data.


### -field dwProcessId

Specifies the process identifier (PID) of the process destroying the <a href="https://msdn.microsoft.com/05a2f942-4374-421e-8292-d122f9fe3571">AGP memory</a> for surfaces.


## -remarks



The driver sometimes receives a <b>GetDriverInfo2</b> call with D3DGDI2_TYPE_DEFER_AGP_FREES notification type before a display mode change occurs. The runtime only sends this notification type if it is to be used to perform the display mode change. Drivers should check the process identifier (PID) of the process destroying the surface against the process that created the surface. If the PIDs are different, the driver probably should not destroy the user-mode mappings of the AGP memory because an application might still be using the memory.

The driver receives a <b>GetDriverInfo2</b> call with D3DGDI2_TYPE_FREE_DEFERRED_AGP notification type when all display devices within the process stop using surfaces, textures, vertex buffers, and index buffers that were locked at the time of the display mode change. This notification type informs the driver that it is now safe to destroy all the user-mode mappings of the AGP memory. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551548">DD_GETDRIVERINFO2DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551550">DD_GETDRIVERINFODATA</a>
 

 

