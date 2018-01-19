---
UID: NC:d3dumddi.PFND3DDDI_FLIPOVERLAYCB
title: PFND3DDDI_FLIPOVERLAYCB
author: windows-driver-content
description: The pfnFlipOverlayCb function changes the allocation to display on the overlay or indicates to display the other field of the currently displaying allocation, when deinterlacing an interleaved resource.
old-location: display\pfnflipoverlaycb.htm
old-project: display
ms.assetid: 91e4876a-82c0-4e74-84c8-4b7a6abe0756
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
req.alt-api: pfnFlipOverlayCb
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

# PFND3DDDI_FLIPOVERLAYCB callback



## -description
The <b>pfnFlipOverlayCb</b> function changes the allocation to display on the overlay or indicates to display the other field of the currently displaying allocation, when deinterlacing an interleaved resource.



## -prototype

````
PFND3DDDI_FLIPOVERLAYCB pfnFlipOverlayCb;

__checkReturn HRESULT APIENTRY CALLBACK pfnFlipOverlayCb(
  _In_       HANDLE               hDevice,
  _In_ const D3DDDICB_FLIPOVERLAY *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to the display device (graphics context).


### -param pData [in]

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_flipoverlay.md">D3DDDICB_FLIPOVERLAY</a> structure that describes how to change the display on the overlay.


## -returns
<b>pfnFlipOverlayCb</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The display on the overlay object was successfully changed.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>Parameters were validated and determined to be incorrect.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><b>pfnFlipOverlayCb</b> could not allocate memory that was required for it to complete.

 

This function might also return other HRESULT values.

The following code example shows how to flip the overlay object.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicecallbacks.md">D3DDDI_DEVICECALLBACKS</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_flipoverlay.md">D3DDDICB_FLIPOVERLAY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_FLIPOVERLAYCB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

