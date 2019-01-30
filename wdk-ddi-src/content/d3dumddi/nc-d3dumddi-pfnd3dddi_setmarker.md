---
UID: NC:d3dumddi.PFND3DDDI_SETMARKER
title: PFND3DDDI_SETMARKER (d3dumddi.h)
description: Notifies the user-mode display driver that it must generate a new time stamp if any GPU work has completed since the last call to pfnSetMarker.
old-location: display\pfnsetmarker.htm
tech.root: display
ms.assetid: 6D4DB988-D339-4B2F-A9B8-41B4FD21FE66
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_SETMARKER, PFND3DDDI_SETMARKER callback, d3dumddi/pfnSetMarker, display.pfnsetmarker, pfnSetMarker, pfnSetMarker callback function [Display Devices]
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
-	pfnSetMarker
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_SETMARKER callback function


## -description


Notifies the user-mode display driver that it must generate a new time stamp if any GPU work has completed since the last call to <i>pfnSetMarker</i>. Optionally implemented by Windows Display Driver Model (WDDM) 1.3 and later drivers running on Microsoft Direct3D Level 9 hardware. (See requirements in [Direct3D rendering performance improvements](https://docs.microsoft.com/windows-hardware/drivers/display/direct3d-rendering-performance-improvements).)  For more advanced hardware, drivers should implement the <a href="https://msdn.microsoft.com/BE618B0C-18E7-4B2B-87EB-172DAD9BCE15">SetMarker</a> function.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


## -returns




      Returns <b>S_OK</b> or an appropriate error result if the function does not complete successfully.




## -remarks



If the marker event type from the  <i>Type</i> parameter of the <a href="https://msdn.microsoft.com/D45750D9-F722-4208-8D00-E14FD9C009CB">pfnSetMarkerMode</a> function is not <b>D3DDDIMT_NONE</b>, the user-mode display driver must perform this procedure with each call to <i>pfnSetMarker</i>:

<ol>
<li>Increment the value of the <b>APISequenceNumber</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn535965">D3DDDICB_LOGUMDMARKER</a> structure.</li>
<li>Determine which contexts associated with single-threaded device driver interface (DDI) render calls submitted work with the last call to <i>pfnSetMarker</i>. For each such context:<ol>
<li>If the command buffer for the context is empty, do nothing.</li>
<li>Otherwise:<ul>
<li>Ensure that more memory is available in the context's history buffer. Flush the buffer if necessary.</li>
<li>Add another entry to the context's API sequence number buffer that contains the low 32 bits of the current <b>APISequenceNumber</b> value.</li>
<li>Sample and write out time stamps that are appropriate for the current marker event type.</li>
</ul>
</li>
<li>Update tracking data that will be used the next time that <i>pfnSetMarker</i> is called.</li>
</ol>
</li>
</ol>



## -see-also




<a href="https://msdn.microsoft.com/BE618B0C-18E7-4B2B-87EB-172DAD9BCE15">SetMarker</a>



<a href="https://msdn.microsoft.com/D45750D9-F722-4208-8D00-E14FD9C009CB">pfnSetMarkerMode</a>
 

 

