---
UID: NC:d3dumddi.PFND3DDDI_CREATEOVERLAYCB
title: PFND3DDDI_CREATEOVERLAYCB
author: windows-driver-content
description: The pfnCreateOverlayCb function creates a kernel-mode overlay object and calls the display miniport driver to display the overlay.
old-location: display\pfncreateoverlaycb.htm
old-project: display
ms.assetid: fbd5b3af-0963-4e41-8be3-41e3e1ecf8bc
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
req.alt-api: pfnCreateOverlayCb
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

# PFND3DDDI_CREATEOVERLAYCB callback



## -description
The <b>pfnCreateOverlayCb</b> function creates a kernel-mode overlay object and calls the display miniport driver to display the overlay.



## -prototype

````
PFND3DDDI_CREATEOVERLAYCB pfnCreateOverlayCb;

__checkReturn HRESULT APIENTRY CALLBACK pfnCreateOverlayCb(
  _In_    HANDLE                 hDevice,
  _Inout_ D3DDDICB_CREATEOVERLAY *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to the display device (graphics context).


### -param pData [in, out]

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_createoverlay.md">D3DDDICB_CREATEOVERLAY</a> structure that describes the overlay to create.


## -returns
<b>pfnCreateOverlayCb</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The overlay object was successfully created.
<dl>
<dt><b>D3DDDIERR_NOTAVAILABLE</b></dt>
</dl><b>pfnCreateOverlayCb</b> failed because of a lack of overlay hardware or bandwidth.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>Parameters were validated and determined to be incorrect.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><b>pfnCreateOverlayCb</b> could not allocate memory that was required for it to complete.

 

This function might also return other HRESULT values.


## -remarks
The <b>pfnCreateOverlayCb</b> function returns a handle to the newly created kernel-mode overlay object in the <b>hKernelOverlay</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_createoverlay.md">D3DDDICB_CREATEOVERLAY</a> structure that is pointed to by <i>pData</i>. The user-mode display driver passes this handle in calls to the following functions:


<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroyoverlaycb.md">pfnDestroyOverlayCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_flipoverlaycb.md">pfnFlipOverlayCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updateoverlaycb.md">pfnUpdateOverlayCb</a>


The following code example shows how to create an overlay object.


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_createoverlay.md">D3DDDICB_CREATEOVERLAY</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicecallbacks.md">D3DDDI_DEVICECALLBACKS</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroyoverlaycb.md">pfnDestroyOverlayCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_flipoverlaycb.md">pfnFlipOverlayCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updateoverlaycb.md">pfnUpdateOverlayCb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_CREATEOVERLAYCB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

