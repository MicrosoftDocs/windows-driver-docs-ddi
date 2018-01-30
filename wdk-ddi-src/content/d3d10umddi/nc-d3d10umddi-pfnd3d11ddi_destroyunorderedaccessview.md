---
UID: NC:d3d10umddi.PFND3D11DDI_DESTROYUNORDEREDACCESSVIEW
title: PFND3D11DDI_DESTROYUNORDEREDACCESSVIEW
author: windows-driver-content
description: Destroys an unordered access view.
old-location: display\destroyunorderedaccessview.htm
old-project: display
ms.assetid: 1bce3519-f333-4b47-b29b-bde1b5c3005c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.destroyunorderedaccessview, DestroyUnorderedAccessView callback function [Display Devices], DestroyUnorderedAccessView, PFND3D11DDI_DESTROYUNORDEREDACCESSVIEW, PFND3D11DDI_DESTROYUNORDEREDACCESSVIEW, d3d10umddi/DestroyUnorderedAccessView, UserModeDisplayDriverDx11_Functions_65ca10d0-2325-40f6-befa-8ad6ea5f0efd.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3d10umddi.h
apiname:
-	DestroyUnorderedAccessView
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11DDI_DESTROYUNORDEREDACCESSVIEW callback


## -description


Destroys an unordered access view.


## -prototype


````
PFND3D11DDI_DESTROYUNORDEREDACCESSVIEW DestroyUnorderedAccessView;

VOID APIENTRY DestroyUnorderedAccessView(
  _In_ D3D10DDI_HDEVICE              hDevice,
  _In_ D3D11DDI_HUNORDEREDACCESSVIEW hUnorderedAccessView
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE



### -param D3D11DDI_HUNORDEREDACCESSVIEW






#### - hDevice [in]

 A handle to the display device (graphics context).


#### - hUnorderedAccessView [in]

 A handle to the driver's private data for the unordered access view to destroy. The Microsoft Direct3D runtime frees the memory region that it previously allocated for the unordered access view. Therefore, the driver can no longer access this memory region. 


## -returns


None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.



## -remarks


The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <i>DestroyUnorderedAccessView</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.<div class="alert"><b>Note</b>  During the destruction of the immediate context and device or the destruction of a deferred context, Windows 7 does not clear the Compute Shader Unordered Access View (CS UAV) bind points. 
As a result, a driver sees a UAV handle to still be bound to a context, which violates the general guarantees provided by the runtime. 
The driver can work around this problem by following these steps:
  <ul>
<li>Use either the    <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_abandoncommandlist.md">AbandonCommandList</a> or the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createcommandlist.md">CreateCommandList</a> method because each marks the end of a command list.</li>
<li> Deduce the unbinding of CS UAV bind points by verifying that any one of the following states is set to NULL: blend state, rasterizer state, and depth/stencil state.</li>
</ul>
</div>
<div> </div>




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_abandoncommandlist.md">AbandonCommandList</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createunorderedaccessview.md">CreateUnorderedAccessView</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createcommandlist.md">CreateCommandList</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11DDI_DESTROYUNORDEREDACCESSVIEW callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

