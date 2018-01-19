---
UID: NC:dxgiddi.PFNDDXGIDDI_PRESENTCB
title: PFNDDXGIDDI_PRESENTCB
author: windows-driver-content
description: The pfnPresentCbDXGI function copies content from a source allocation to a destination allocation.
old-location: display\pfnpresentcbdxgi.htm
old-project: display
ms.assetid: eefb8f2c-e460-4f9c-851d-9a97dbcd728f
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DxApiGetVersion
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: pfnPresentCbDXGI
req.alt-loc: dxgiddi.h
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
req.typenames: DRMRIGHTS, *PDRMRIGHTS
---

# PFNDDXGIDDI_PRESENTCB callback



## -description
The <b>pfnPresentCbDXGI</b> function copies content from a source allocation to a destination allocation.



## -prototype

````
PFNDDXGIDDI_PRESENTCB pfnPresentCbDXGI;

HRESULT pfnPresentCbDXGI(
  _In_       HANDLE            hDevice,
  _In_ const DXGIDDICB_PRESENT *pPresentData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to a display device (graphics context). 


### -param pPresentData [in]

 A pointer to a <a href="..\dxgiddi\ns-dxgiddi-dxgiddicb_present.md">DXGIDDICB_PRESENT</a> structure that describes the source and destination allocations that content is copied from and to. 


## -returns
<b>pfnPresentCbDXGI</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>Content was successfully copied.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><b>pfnPresentCbDXGI</b> could not complete because of insufficient memory.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>Parameters were validated and determined to be incorrect.

 


## -remarks
The <b>pDXGIContext</b> member of the <a href="..\dxgiddi\ns-dxgiddi-dxgiddicb_present.md">DXGIDDICB_PRESENT</a> structure that the <i>pPresentData</i> parameter points to is an opaque communication mechanism. The runtime passes this DXGI context to the driver in the <b>pDXGIContext</b> member of the <a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_arg_present.md">DXGI_DDI_ARG_PRESENT</a> structure when the runtime calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff569179">PresentDXGI</a> function. The driver should copy this DXGI context unchanged to the <b>pDXGIContext</b> member of DXGIDDICB_PRESENT when the driver calls <b>pfnPresentCbDXGI</b>. 

The Direct3D runtime restricts the set of formats that can be presented through a bit-block transfer (bitblt) operation. For more information about the restrictions, see the Remarks section of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff538252">BltDXGI</a> reference page.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538252">BltDXGI</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>
</dt>
<dt>
<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_arg_present.md">DXGI_DDI_ARG_PRESENT</a>
</dt>
<dt>
<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_base_callbacks.md">DXGI_DDI_BASE_CALLBACKS</a>
</dt>
<dt>
<a href="..\dxgiddi\ns-dxgiddi-dxgiddicb_present.md">DXGIDDICB_PRESENT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569179">PresentDXGI</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFNDDXGIDDI_PRESENTCB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

