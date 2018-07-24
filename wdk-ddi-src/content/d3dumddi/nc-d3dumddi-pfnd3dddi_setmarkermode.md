---
UID: NC:d3dumddi.PFND3DDDI_SETMARKERMODE
title: PFND3DDDI_SETMARKERMODE
author: windows-driver-content
description: Notifies the user-mode display driver that it should support a type of Event Tracing for Windows (ETW) marker event.
old-location: display\pfnsetmarkermode.htm
tech.root: display
ms.assetid: D45750D9-F722-4208-8D00-E14FD9C009CB
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3DDDI_SETMARKERMODE, PFND3DDDI_SETMARKERMODE callback, d3dumddi/pfnSetMarkerMode, display.pfnsetmarkermode, pfnSetMarkerMode, pfnSetMarkerMode callback function [Display Devices]
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
-	pfnSetMarkerMode
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_SETMARKERMODE callback function


## -description


Notifies the user-mode display driver that it should support a type of Event Tracing for Windows (ETW) marker event. Optionally implemented by Windows Display Driver Model (WDDM) 1.3 and later drivers running on Microsoft Direct3D Level 9 hardware. (See requirements in <a href="https://msdn.microsoft.com/F9AAE489-EC45-4EE6-875E-E084BB3054EE">Direct3D rendering performance improvements</a>.) For more advanced hardware, drivers should implement the <a href="https://msdn.microsoft.com/18B13509-7692-4336-937C-264B31A6FB78">SetMarkerMode</a> function.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param Type [in]

A value from the <a href="https://msdn.microsoft.com/library/windows/hardware/dn535967">D3DDDI_MARKERTYPE</a> enumeration that indicates the type of marker event  that the driver should support.


### -param Flags

A <b>UINT</b> value that indicates whether the driver should provide custom info in command buffers. If set to <b>D3DDDI_SETMARKERMODE_CUSTOMDRIVEREVENTS</b>, the driver should annotate and instrument command buffers with custom event info. Otherwise, the driver should not annotate command buffers.

The annotation can be in the form of a text string in the English-US locale, or in the form of an index value to a location in a string table. For the latter option, the driver must also implement a function that describes the strings that the index values indicate.


## -returns




      Returns <b>S_OK</b> or an appropriate error result if the function does not complete successfully.




## -remarks



Follow these guidelines when you set up profile-type marker events in your user-mode driver, indicated by the <b>D3DDDIMT_PROFILE</b> type:

<ol>
<li>Use lightweight instrumentation that doesn't produce a strong correlation with graphics command boundaries.</li>
<li>The driver must be able to sample the GPU time stamp at the end of the graphics pipeline.</li>
<li>Don't use sampling commands that place a high performance burden on the graphics pipeline, such as wait-for-idle commands. To be able to instrument profile-type marker events, your driver shouldn't have to flush the pipeline or caches.</li>
</ol>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn535967">D3DDDI_MARKERTYPE</a>



<a href="https://msdn.microsoft.com/18B13509-7692-4336-937C-264B31A6FB78">SetMarkerMode</a>
 

 

