---
UID: NC:d3dumddi.PFND3DDDI_DESTROYOVERLAYCB
title: PFND3DDDI_DESTROYOVERLAYCB
author: windows-driver-content
description: The pfnDestroyOverlayCb function disables the overlay hardware and destroys the kernel-mode overlay object.
old-location: display\pfndestroyoverlaycb.htm
old-project: display
ms.assetid: 9fc83bad-c183-4cba-9514-bfe1c676cba5
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
req.alt-api: pfnDestroyOverlayCb
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

# PFND3DDDI_DESTROYOVERLAYCB callback



## -description
The <b>pfnDestroyOverlayCb</b> function disables the overlay hardware and destroys the kernel-mode overlay object.



## -prototype

````
PFND3DDDI_DESTROYOVERLAYCB pfnDestroyOverlayCb;

_checkReturn HRESULT APIENTRY CALLBACK pfnDestroyOverlayCb(
  _In_       HANDLE                  hDevice,
  _In_ const D3DDDICB_DESTROYOVERLAY *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to the display device (graphics context).


### -param pData [in]

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_destroyoverlay.md">D3DDDICB_DESTROYOVERLAY</a> structure that contains a handle to the overlay object to be disabled.


## -returns
<b>pfnDestroyOverlayCb</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The overlay object was successfully disabled.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>Parameters were validated and determined to be incorrect.

 

This function might also return other HRESULT values.

The following code example shows how to destroy the overlay object.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicecallbacks.md">D3DDDI_DEVICECALLBACKS</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_destroyoverlay.md">D3DDDICB_DESTROYOVERLAY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DESTROYOVERLAYCB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

