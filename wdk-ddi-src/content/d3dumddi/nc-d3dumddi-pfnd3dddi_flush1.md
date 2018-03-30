---
UID: NC:d3dumddi.PFND3DDDI_FLUSH1
title: PFND3DDDI_FLUSH1
author: windows-driver-content
description: Called by the Microsoft Direct3D runtime to submit outstanding hardware commands that are in the hardware command buffer to the display miniport driver. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.
old-location: display\pfnflush1.htm
old-project: display
ms.assetid: 6BAC104A-85CE-42FC-AE30-969B2FF6AFEF
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DDDI_FLUSH1, d3dumddi/pfnFlush1, display.pfnflush1, pfnFlush1, pfnFlush1 callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3dumddi.h
api_name:
-	pfnFlush1
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_FLUSH1 callback


## -description


Called by the Microsoft Direct3D runtime to submit outstanding hardware commands that are in the hardware command buffer to the display miniport driver. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.



## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).




### -param FlushFlags

A value from the <a href="https://msdn.microsoft.com/library/windows/hardware/dn449154">D3DDDI_FLUSH_FLAGS</a> enumeration that indicates whether the driver should continue to submit command buffers if there have been no new commands.


## -returns



If this routine succeeds, it returns <b>S_OK</b>. Otherwise, it returns an <b>HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn449154">D3DDDI_FLUSH_FLAGS</a>
 

 

