---
UID: NC:d3dumddi.PFND3DDDI_SETMARKER
title: PFND3DDDI_SETMARKER
author: windows-driver-content
description: Notifies the user-mode display driver that it must generate a new time stamp if any GPU work has completed since the last call to pfnSetMarker.
old-location: display\pfnsetmarker.htm
old-project: display
ms.assetid: 6D4DB988-D339-4B2F-A9B8-41B4FD21FE66
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
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
req.alt-api: pfnSetMarker
req.alt-loc: D3dumddi.h
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
req.typenames: DXGK_PTE
---

# PFND3DDDI_SETMARKER callback



## -description
Notifies the user-mode display driver that it must generate a new time stamp if any GPU work has completed since the last call to <i>pfnSetMarker</i>. Optionally implemented by Windows Display Driver Model (WDDM) 1.3 and later drivers running on Microsoft Direct3D Level 9 hardware. (See requirements in  <a href="https://msdn.microsoft.com/F9AAE489-EC45-4EE6-875E-E084BB3054EE">Direct3D rendering performance improvements</a>.)  For more advanced hardware, drivers should implement the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm1_3ddi_setmarker.md">SetMarker</a> function.



## -prototype

````
PFND3DDDI_SETMARKER pfnSetMarker;

_Check_return_ HRESULT APIENTRY* pfnSetMarker(
  _In_ HANDLE hDevice
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to the display device (graphics context).


## -returns

      Returns <b>S_OK</b> or an appropriate error result if the function does not complete successfully.


## -remarks
If the marker event type from the  <i>Type</i> parameter of the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setmarkermode.md">pfnSetMarkerMode</a> function is not <b>D3DDDIMT_NONE</b>, the user-mode display driver must perform this procedure with each call to <i>pfnSetMarker</i>:


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setmarkermode.md">pfnSetMarkerMode</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm1_3ddi_setmarker.md">SetMarker</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETMARKER callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

