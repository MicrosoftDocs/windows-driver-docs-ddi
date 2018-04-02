---
UID: NC:d3dumddi.PFND3DDDI_CHECKPRESENTDURATIONSUPPORT
title: PFND3DDDI_CHECKPRESENTDURATIONSUPPORT
author: windows-driver-content
description: Called by the Microsoft Direct3D runtime to request that the user-mode display driver get hardware device capabilities for seamlessly switching to a new monitor refresh rate.
old-location: display\checkpresentdurationsupport.htm
old-project: display
ms.assetid: 4D3FC503-A502-41D3-AB76-5A2BEBE4C551
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CheckPresentDurationSupport, CheckPresentDurationSupport callback function [Display Devices], PFND3DDDI_CHECKPRESENTDURATIONSUPPORT, d3dumddi/CheckPresentDurationSupport, display.checkpresentdurationsupport
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
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
-	CheckPresentDurationSupport
product:
- Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_CHECKPRESENTDURATIONSUPPORT callback


## -description


Called by the Microsoft Direct3D runtime to request that the user-mode display driver  get  hardware device capabilities for seamlessly switching to a new monitor refresh rate. Optionally implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








#### - pPresentDurationSupport [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn465881">D3DDDIARG_CHECKPRESENTDURATIONSUPPORT</a> structure that contains info on hardware device support for seamlessly switching to a new monitor refresh rate.


## -returns



If this routine succeeds, it returns <b>S_OK</b>. The driver should always return a success code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn465881">D3DDDIARG_CHECKPRESENTDURATIONSUPPORT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 

