---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_SETHARDWAREPROTECTION
title: PFND3DWDDM2_0DDI_SETHARDWAREPROTECTION
author: windows-driver-content
description: SetHardwareProtection allows the Desktop Window Manager (DWM) full-screen swap chain buffers to transfer between protected and non-protected states without having to be recreated.
old-location: display\sethardwareprotection.htm
old-project: display
ms.assetid: 9D41C504-1F84-4F1A-B767-D3B423A8AA46
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.sethardwareprotection, pfnSetHardwareProtection callback function [Display Devices], pfnSetHardwareProtection, PFND3DWDDM2_0DDI_SETHARDWAREPROTECTION, PFND3DWDDM2_0DDI_SETHARDWAREPROTECTION, d3d10umddi/pfnSetHardwareProtection
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	D3d10umddi.h
apiname:
-	pfnSetHardwareProtection
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3DWDDM2_0DDI_SETHARDWAREPROTECTION callback


## -description


<b>SetHardwareProtection</b> allows the Desktop Window Manager (DWM) full-screen swap chain buffers to transfer between protected and non-protected states without having to be recreated.


## -prototype


````
PFND3DWDDM2_0DDI_SETHARDWAREPROTECTION pfnSetHardwareProtection;

VOID APIENTRY* pfnSetHardwareProtection(
   D3D10DDI_HDEVICE   hDevice,
   D3D10DDI_HRESOURCE hResource,
   BOOL               Protected
)
{ ... }
````


## -parameters




#### - hDevice

A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a> structure at device creation.


#### - hResource

A handle to the resource object that was created through a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a>DDI. 


#### - Protected

Indicates that the buffer should be protected.


## -returns


This callback function does not return a value.



## -remarks


Destroying and re-creating the DWM swap chain buffers is a heavyweight operation that can be avoided on some hardware.  This DDI will only be called if the driver reports the <b>D3DWDDM2_0DDI_CONTENT_PROTECTION_CAPS_HARDWARE_PROTECTED_MEMORY_TRANSITION</b> capability.  If this is not set, the underlying DWM swap chain allocations will be destroyed and recreated.



<b>SetHardwareProtection</b> is called on the non-visible swap chain buffers allowing it to transition between protected and unprotected modes without causing a visual artifact.  When the DWM flips to the newly changed buffer, the DWM will call <b>SetHardwareProtection</b> on the next buffer in the swap chain buffer, and so on until the new protection state has been set on each of the swap chain buffers.


<div class="alert"><b>Note</b>  The DWM is guaranteed to re-render the entire swap chain buffer after the hardware protection state has changed.
</div><div> </div>


## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DWDDM2_0DDI_SETHARDWAREPROTECTION callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

