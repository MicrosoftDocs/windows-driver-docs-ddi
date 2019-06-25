---
UID: NC:d3dumddi.PFND3DDDI_CREATEOVERLAYCB
title: PFND3DDDI_CREATEOVERLAYCB (d3dumddi.h)
description: The pfnCreateOverlayCb function creates a kernel-mode overlay object and calls the display miniport driver to display the overlay.
old-location: display\pfncreateoverlaycb.htm
tech.root: display
ms.assetid: fbd5b3af-0963-4e41-8be3-41e3e1ecf8bc
ms.date: 05/10/2018
ms.keywords: D3Druntime_Functions_d30fc7c1-55b2-4444-9ac1-34baabc073f6.xml, PFND3DDDI_CREATEOVERLAYCB, PFND3DDDI_CREATEOVERLAYCB callback, d3dumddi/pfnCreateOverlayCb, display.pfncreateoverlaycb, pfnCreateOverlayCb, pfnCreateOverlayCb callback function [Display Devices]
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
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
- d3dumddi.h
api_name:
- pfnCreateOverlayCb
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_CREATEOVERLAYCB callback function


## -description


The <b>pfnCreateOverlayCb</b> function creates a kernel-mode overlay object and calls the display miniport driver to display the overlay.


## -parameters


### -param hDevice [in]

A handle to the display device (graphics context).


### -param *

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddicb_createoverlay">D3DDDICB_CREATEOVERLAY</a> structure that describes the overlay to create.


## -returns

<b>pfnCreateOverlayCb</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The overlay object was successfully created.|
|D3DDDIERR_NOTAVAILABLE|pfnCreateOverlayCb failed because of a lack of overlay hardware or bandwidth.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|
|E_OUTOFMEMORY|pfnCreateOverlayCb could not allocate memory that was required for it to complete.|

This function might also return other HRESULT values.




## -remarks



The <b>pfnCreateOverlayCb</b> function returns a handle to the newly created kernel-mode overlay object in the <b>hKernelOverlay</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddicb_createoverlay">D3DDDICB_CREATEOVERLAY</a> structure that is pointed to by <i>pData</i>. The user-mode display driver passes this handle in calls to the following functions:

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_destroyoverlaycb">pfnDestroyOverlayCb</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_flipoverlaycb">pfnFlipOverlayCb</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_updateoverlaycb">pfnUpdateOverlayCb</a>


</li>
</ul>
The following code example shows how to create an overlay object.

```cpp
D3DKMT_HANDLE g_hOverlay = NULL;

HRESULT CD3DContext::CreateOverlay(D3DDDIARG_CREATEOVERLAY* pCreateOverlay) {
    D3DDDICB_CREATEOVERLAY CreateCB;
    DWORD_PTR dwResource = (DWORD_PTR) pCreateOverlay->OverlayInfo.hResource;
    dwResource += pCreateOverlay->OverlayInfo.SubResourceIndex;
    LONG dwTempPitch;

    pCreateOverlay->hOverlay = (HANDLE) 0x27;

    CreateCB.VidPnSourceId = 0;
    CreateCB.OverlayInfo.hAllocation = R200GetAllocationHandle(m_pR200Ctx,
                                     (DWORD)dwResource,
                                      &dwTempPitch);

    CreateCB.OverlayInfo.DstRect.left = pCreateOverlay->OverlayInfo.DstRect.left;
    CreateCB.OverlayInfo.DstRect.right = pCreateOverlay->OverlayInfo.DstRect.right;
    CreateCB.OverlayInfo.DstRect.top = pCreateOverlay->OverlayInfo.DstRect.top;
    CreateCB.OverlayInfo.DstRect.bottom = pCreateOverlay->OverlayInfo.DstRect.bottom;

    CreateCB.OverlayInfo.SrcRect.left = pCreateOverlay->OverlayInfo.SrcRect.left;
    CreateCB.OverlayInfo.SrcRect.right = pCreateOverlay->OverlayInfo.SrcRect.right;
    CreateCB.OverlayInfo.SrcRect.top = pCreateOverlay->OverlayInfo.SrcRect.top;
    CreateCB.OverlayInfo.SrcRect.bottom = pCreateOverlay->OverlayInfo.SrcRect.bottom;

    CreateCB.OverlayInfo.pPrivateDriverData = "This is a test";
    CreateCB.OverlayInfo.PrivateDriverDataSize = 10;

    HRESULT hr = m_d3dCallbacks.pfnCreateOverlayCb(m_hD3D, &CreateCB);

    if (SUCCEEDED(hr)) {
        g_hOverlay = CreateCB.hKernelOverlay;
    }

    return hr;
}
```


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddicb_createoverlay">D3DDDICB_CREATEOVERLAY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddi_devicecallbacks">D3DDDI_DEVICECALLBACKS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_destroyoverlaycb">pfnDestroyOverlayCb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_flipoverlaycb">pfnFlipOverlayCb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_updateoverlaycb">pfnUpdateOverlayCb</a>
 

 

