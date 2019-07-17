---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_SETHARDWAREPROTECTION
title: PFND3DWDDM2_0DDI_SETHARDWAREPROTECTION (d3d10umddi.h)
description: SetHardwareProtection allows the Desktop Window Manager (DWM) full-screen swap chain buffers to transfer between protected and non-protected states without having to be recreated.
old-location: display\sethardwareprotection.htm
ms.assetid: 9D41C504-1F84-4F1A-B767-D3B423A8AA46
ms.date: 05/10/2018
ms.keywords: PFND3DWDDM2_0DDI_SETHARDWAREPROTECTION, PFND3DWDDM2_0DDI_SETHARDWAREPROTECTION callback, d3d10umddi/pfnSetHardwareProtection, display.sethardwareprotection, pfnSetHardwareProtection, pfnSetHardwareProtection callback function [Display Devices]
ms.topic: callback
f1_keywords:
 - "d3d10umddi/pfnSetHardwareProtection"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
- UserDefined
api_location:
- D3d10umddi.h
api_name:
- pfnSetHardwareProtection
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3DWDDM2_0DDI_SETHARDWAREPROTECTION callback function


## -description


<b>SetHardwareProtection</b> allows the Desktop Window Manager (DWM) full-screen swap chain buffers to transfer between protected and non-protected states without having to be recreated.


## -parameters




### -param hDevice

A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a> structure at device creation.


### -param hResource

A handle to the resource object that was created through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_createresource">CreateResource</a>DDI. 


### -param Protected

Indicates that the buffer should be protected.


## -returns



This callback function does not return a value.




## -remarks



Destroying and re-creating the DWM swap chain buffers is a heavyweight operation that can be avoided on some hardware.  This DDI will only be called if the driver reports the <b>D3DWDDM2_0DDI_CONTENT_PROTECTION_CAPS_HARDWARE_PROTECTED_MEMORY_TRANSITION</b> capability.  If this is not set, the underlying DWM swap chain allocations will be destroyed and recreated.



<b>SetHardwareProtection</b> is called on the non-visible swap chain buffers allowing it to transition between protected and unprotected modes without causing a visual artifact.  When the DWM flips to the newly changed buffer, the DWM will call <b>SetHardwareProtection</b> on the next buffer in the swap chain buffer, and so on until the new protection state has been set on each of the swap chain buffers.



<div class="alert"><b>Note</b>  The DWM is guaranteed to re-render the entire swap chain buffer after the hardware protection state has changed.
</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_createresource">CreateResource</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a>
 

 

