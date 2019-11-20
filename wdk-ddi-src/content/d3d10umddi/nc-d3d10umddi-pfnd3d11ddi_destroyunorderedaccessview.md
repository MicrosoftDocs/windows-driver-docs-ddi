---
UID: NC:d3d10umddi.PFND3D11DDI_DESTROYUNORDEREDACCESSVIEW
title: PFND3D11DDI_DESTROYUNORDEREDACCESSVIEW (d3d10umddi.h)
description: Destroys an unordered access view.
old-location: display\destroyunorderedaccessview.htm
ms.assetid: 1bce3519-f333-4b47-b29b-bde1b5c3005c
ms.date: 05/10/2018
ms.keywords: DestroyUnorderedAccessView, DestroyUnorderedAccessView callback function [Display Devices], PFND3D11DDI_DESTROYUNORDEREDACCESSVIEW, PFND3D11DDI_DESTROYUNORDEREDACCESSVIEW callback, UserModeDisplayDriverDx11_Functions_65ca10d0-2325-40f6-befa-8ad6ea5f0efd.xml, d3d10umddi/DestroyUnorderedAccessView, display.destroyunorderedaccessview
ms.topic: callback
f1_keywords:
 - "d3d10umddi/DestroyUnorderedAccessView"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: DestroyUnorderedAccessView is supported beginning with the Windows 7 operating system.
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
- d3d10umddi.h
api_name:
- DestroyUnorderedAccessView
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11DDI_DESTROYUNORDEREDACCESSVIEW callback function


## -description


Destroys an unordered access view.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hUnorderedAccessView* [in]

A handle to the driver's private data for the unordered access view to destroy. The Microsoft Direct3D runtime frees the memory region that it previously allocated for the unordered access view. Therefore, the driver can no longer access this memory region. 


## -remarks

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <i>DestroyUnorderedAccessView</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.<div class="alert"><b>Note</b>  During the destruction of the immediate context and device or the destruction of a deferred context, Windows 7 does not clear the Compute Shader Unordered Access View (CS UAV) bind points. 
As a result, a driver sees a UAV handle to still be bound to a context, which violates the general guarantees provided by the runtime. 
The driver can work around this problem by following these steps:
  <ul>
<li>Use either the    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_abandoncommandlist">AbandonCommandList</a> or the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createcommandlist">CreateCommandList</a> method because each marks the end of a command list.</li>
<li> Deduce the unbinding of CS UAV bind points by verifying that any one of the following states is set to NULL: blend state, rasterizer state, and depth/stencil state.</li>
</ul>
</div>
<div> </div>





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_abandoncommandlist">AbandonCommandList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createcommandlist">CreateCommandList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createunorderedaccessview">CreateUnorderedAccessView</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
 

 

