---
UID: NC:d3dumddi.PFND3DDDI_CREATEOVERLAY
title: PFND3DDDI_CREATEOVERLAY
author: windows-driver-content
description: The CreateOverlay function allocates overlay hardware and makes the overlay visible.
old-location: display\createoverlay.htm
old-project: display
ms.assetid: 761377ff-95a6-426b-8372-3f347870f9c4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CreateOverlay
req.alt-loc: d3dumddi.h
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

# PFND3DDDI_CREATEOVERLAY callback



## -description
The <b>CreateOverlay</b> function allocates overlay hardware and makes the overlay visible.



## -prototype

````
PFND3DDDI_CREATEOVERLAY CreateOverlay;

__checkReturn HRESULT APIENTRY CreateOverlay(
  _In_    HANDLE                  hDevice,
  _Inout_ D3DDDIARG_CREATEOVERLAY *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param pData [in, out]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createoverlay.md">D3DDDIARG_CREATEOVERLAY</a> structure that describes the overlay.


## -returns
<b>CreateOverlay</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The overlay is successfully created.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createoverlay.md">CreateOverlay</a> could not complete because of insufficient memory.
<dl>
<dt><b>D3DDDIERR_NOTAVAILABLE</b></dt>
</dl>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createoverlay.md">CreateOverlay</a> could not complete because insufficient bandwidth was available or the requested overlay hardware was unavailable.
<dl>
<dt><b>D3DDDIERR_UNSUPPORTEDOVERLAYFORMAT</b></dt>
</dl>The specified overlay format is not supported by the overlay hardware. 
<dl>
<dt><b>D3DDDIERR_UNSUPPORTEDOVERLAY</b></dt>
</dl>The overlay hardware is not supported for the specified size and display mode. 

 


## -remarks
Overlays are independent from the resources that are displayed by using the overlays.


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createoverlay.md">D3DDDIARG_CREATEOVERLAY</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_CREATEOVERLAY callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

