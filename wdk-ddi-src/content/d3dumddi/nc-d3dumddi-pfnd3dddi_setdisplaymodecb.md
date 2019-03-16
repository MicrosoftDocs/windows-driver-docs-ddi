---
UID: NC:d3dumddi.PFND3DDDI_SETDISPLAYMODECB
title: PFND3DDDI_SETDISPLAYMODECB (d3dumddi.h)
description: The pfnSetDisplayModeCb function sets the allocation that is used to scan out to the display.
old-location: display\pfnsetdisplaymodecb.htm
tech.root: display
ms.assetid: a1f58757-809d-4351-8b1a-fd4420981c24
ms.date: 05/10/2018
ms.keywords: D3Druntime_Functions_717329e1-853d-498e-8792-ba6468825cbb.xml, PFND3DDDI_SETDISPLAYMODECB, PFND3DDDI_SETDISPLAYMODECB callback, d3dumddi/pfnSetDisplayModeCb, display.pfnsetdisplaymodecb, pfnSetDisplayModeCb, pfnSetDisplayModeCb callback function [Display Devices]
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
- pfnSetDisplayModeCb
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_SETDISPLAYMODECB callback function


## -description


The <b>pfnSetDisplayModeCb</b> function sets the allocation that is used to scan out to the display.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544255">D3DDDICB_SETDISPLAYMODE</a> structure that describes the allocation that is used to scan out.


## -returns



<b>pfnSetDisplayModeCb</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The display mode was successfully set. | 
| **E_INVALIDARG** |     Parameters were validated and determined to be incorrect. | 
| **D3DDDIERR_INCOMPATIBLEPRIVATEFORMAT** | The user-mode display driver must convert the format of the surface that is associated with the allocation that the hPrimaryAllocation member of [D3DDDICB_SETDISPLAYMODE](https://msdn.microsoft.com/library/windows/hardware/ff544255) specifies into the format attribute that the PrivateDriverFormatAttributemember of D3DDDICB_SETDISPLAYMODE specifies. The driver should then call pfnSetDisplayModeCb again. The driver could allocate a new allocation, perform a conversion bit-block transfer (bitblt) from the old primary surface to the new, and then destroy the old primary as long as the driver uses the new allocation handle for this allocation for all subsequent operations. The driver should repeat this process until pfnSetDisplayModeCb returns a different return value. | 
This function might also return other HRESULT values.






## -remarks



After the Microsoft Direct3D runtime calls the user-mode display driver's <a href="https://msdn.microsoft.com/d0e409fe-1c64-4468-b52e-b0ede39f6601">SetDisplayMode</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff569536">SetDisplayModeDXGI</a> function to set the primary surface to be scanned out to the display, the user-mode display driver calls the <b>pfnSetDisplayModeCb</b> function to set the underlying primary allocation that is used for scanning out. 

<div class="alert"><b>Note</b>  Before the user-mode display driver calls <b>pfnSetDisplayModeCb</b> to set a new display mode that uses an extended format, a multiple-sampling method, or both, the driver must ensure that the current GDI display mode has the same resolution as the new display mode; otherwise, <b>pfnSetDisplayModeCb</b> returns E_INVALIDARG.
     </div>
<div> </div>

<b>Direct3D Version 11 Note:  </b>For more information about how the driver calls <b>pfnSetDisplayModeCb</b>, see <a href="https://msdn.microsoft.com/014a5e44-f8c4-45c0-96e8-d82f37b8b28d">Changes from Direct3D 10</a>.




#### Examples

The following code example shows how to set the allocation for scanning out to the display.

```cpp
HRESULT CD3DContext::SetDisplayMode(CONST D3DDDIARG_SETDISPLAYMODE* pSetDisplayMode) {
    DWORD   dwSrcSurf = ((DWORD)(DWORD_PTR)pSetDisplayMode-&gt;hResource) + pSetDisplayMode-&gt;SubResourceIndex;
    HRESULT hr;
    // Timestamp the source surface
    m_RTbl[dwSrcSurf].m_qwBatch = m_qwBatch;
    // Send the presentation request to the display miniport driver
    D3DDDICB_SETDISPLAYMODE SetDisplayModeCBData = {0};

    SetDisplayModeCBData.hPrimaryAllocation = R200GetSurfaceAllocHandle(m_pR200Ctx,
                                        dwSrcSurf);

    hr = m_d3dCallbacks.pfnSetDisplayModeCb(m_hD3D, &amp;SetDisplayModeCBData);

    return (hr);
}
```


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544255">D3DDDICB_SETDISPLAYMODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544512">D3DDDI_DEVICECALLBACKS</a>



<a href="https://msdn.microsoft.com/d0e409fe-1c64-4468-b52e-b0ede39f6601">SetDisplayMode</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569536">SetDisplayModeDXGI</a>
 

 

