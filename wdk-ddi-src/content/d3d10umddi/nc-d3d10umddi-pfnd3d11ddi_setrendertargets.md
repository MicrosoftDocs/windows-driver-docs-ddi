---
UID: NC:d3d10umddi.PFND3D11DDI_SETRENDERTARGETS
title: PFND3D11DDI_SETRENDERTARGETS
author: windows-driver-content
description: The SetRenderTargets(D3D11) function sets render target surfaces.
old-location: display\setrendertargets_d3d11_.htm
old-project: display
ms.assetid: cfe5f570-4e53-43ee-942d-56da8dfcfe80
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PFND3D11DDI_SETRENDERTARGETS, SetRenderTargets, SetRenderTargets callback function [Display Devices], UserModeDisplayDriverDx11_Functions_a24d5500-fe0a-4d17-a3fb-acb6ed9e4698.xml, d3d10umddi/SetRenderTargets, display.setrendertargets_d3d11_
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: SetRenderTargets(D3D11) is supported beginning with the Windows 7 operating system.
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	SetRenderTargets
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11DDI_SETRENDERTARGETS callback


## -description


The <i>SetRenderTargets(D3D11)</i> function sets render target surfaces.


## -prototype


````
PFND3D11DDI_SETRENDERTARGETS SetRenderTargets;

VOID APIENTRY SetRenderTargets(
  _In_       D3D10DDI_HDEVICE              hDevice,
  _In_ const D3D10DDI_HRENDERTARGETVIEW    *phRenderTargetView,
  _In_       UINT                          NumRTVs,
  _In_       UINT                          RTVNumbertoUnbind,
  _In_       D3D10DDI_HDEPTHSTENCILVIEW    hDepthStencilView,
  _In_ const D3D11DDI_HUNORDEREDACCESSVIEW *phUnorderedAccessView,
  _In_ const UINT                          *pUAVInitialCounts,
  _In_       UINT                          UAVIndex,
  _In_       UINT                          NumUAVs,
  _In_       UINT                          UAVFirsttoSet,
  _In_       UINT                          UAVNumberUpdated
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param *


### -param NumRTVs [in]

 The number of elements in the array that <i>phRenderTargetView</i> specifies for the render target views (RTVs) to set. 


### -param ClearSlots


### -param D3D10DDI_HDEPTHSTENCILVIEW


### -param UAVStartSlot


### -param NumUAVs [in]

 The number of unordered access view objects (UAVs) to set. 


### -param UAVRangeStart


### -param UAVRangeSize








#### - RTVNumbertoUnbind [in]

 The number of render target view (RTV) objects to unbind (that is, those render target view objects that are previously set but should be no longer set). 


#### - UAVFirsttoSet [in]

 The first unordered access view object (UAV) in the set of all updated UAVs (which includes <b>NULL</b> bindings). 


#### - UAVIndex [in]

Indicates the start element, in the array of bind points, where the passed unordered access view (UAV) array is going to be applied. <i>UAVIndex</i> should be at least as great as  the <i>NumRTVs</i> parameter.

<div class="alert"><b>Note</b>  Only one shared set of binding points exists for render target views (RTVs) and UAVs. RTVs are bound first, followed by UAVs.</div>
<div> </div>

#### - UAVNumberUpdated [in]

 The number of unordered access view objects (UAVs) in the set of all updated UAVs (which includes <b>NULL</b> bindings). 

<div class="alert"><b>Note</b>  The parameters <i>UAVNumberUpdated</i> and  <i>UAVFirsttoSet</i> specify which range, in the  UAVs array, contains changes in relation to the state previously bound. Notice that points in the range could be unchanged. Also, update range indexing is not different from other parameters. For example, <i>UAVFirsttoSet</i>      starts at 0 as the first element of the shared render target view (RTV) and UAV bound space. This parameter is a convenience that reveals the span of what actually changed given that the Direct3D DDI always binds everything (including what has not changed).</div>
<div> </div>

#### - hDepthStencilView [in]

 A handle to the depth-stencil buffer to set. 


#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pUAVInitialCounts [in]

An array of append and consume buffer offsets. <i>pUAV</i> is only relevant for unordered access views (UAVs)  of the <i>phUnorderedAccessView</i> array that were created with either <b>D3D11_DDI_BUFFER_UAV_FLAG_APPEND</b>  or <b>D3D11_DDI_BUFFER_UAV_FLAG_COUNTER</b> set in the <b>Flags</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_buffer_unorderedaccessview.md">D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW</a> structure when the UAV was created; otherwise, the argument is ignored. If an element in this array is set to -1, the current offset for that append and consume buffer should be kept. Any other value causes the driver to set the hidden counter for that UAV append and consume buffer.


#### - phRenderTargetView [in]

 An array of handles to the render target view objects to set. Note that some handle values can be <b>NULL</b>. 


#### - phUnorderedAccessView [in]

 An array of handles to the unordered access view (UAV) objects. 


## -returns



None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Microsoft Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <i>SetRenderTargets(D3D11)</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_buffer_unorderedaccessview.md">D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11DDI_SETRENDERTARGETS callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

