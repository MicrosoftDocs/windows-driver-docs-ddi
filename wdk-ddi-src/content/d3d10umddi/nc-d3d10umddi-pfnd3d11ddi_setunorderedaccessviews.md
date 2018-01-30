---
UID: NC:d3d10umddi.PFND3D11DDI_SETUNORDEREDACCESSVIEWS
title: PFND3D11DDI_SETUNORDEREDACCESSVIEWS
author: windows-driver-content
description: The CsSetUnorderedAccessViews function sets unordered access view (UAV) objects for a compute shader.
old-location: display\cssetunorderedaccessviews.htm
old-project: display
ms.assetid: ab8c529b-19e2-4a2a-af68-0e3998829788
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.cssetunorderedaccessviews, CsSetUnorderedAccessViews callback function [Display Devices], CsSetUnorderedAccessViews, PFND3D11DDI_SETUNORDEREDACCESSVIEWS, PFND3D11DDI_SETUNORDEREDACCESSVIEWS, d3d10umddi/CsSetUnorderedAccessViews, UserModeDisplayDriverDx11_Functions_2e3d1f2b-5113-4cbe-afa8-11f4caf88859.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CsSetUnorderedAccessViews is supported beginning with the Windows 7 operating system.
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
-	CsSetUnorderedAccessViews
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11DDI_SETUNORDEREDACCESSVIEWS callback


## -description


The <i>CsSetUnorderedAccessViews</i> function sets unordered access view (UAV) objects for a compute shader.


## -prototype


````
PFND3D11DDI_SETUNORDEREDACCESSVIEWS CsSetUnorderedAccessViews;

VOID APIENTRY CsSetUnorderedAccessViews(
  _In_       D3D10DDI_HDEVICE              hDevice,
  _In_       UINT                          Offset,
  _In_       UINT                          NumViews,
  _In_ const D3D11DDI_HUNORDEREDACCESSVIEW *phUnorderedAccessView,
  _In_ const UINT                          *pUAVInitialCounts
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE



### -param StartSlot



### -param NumViews [in]

 The total number of views to set. 


### -param *






#### - hDevice [in]

 A handle to the display device (graphics context).


#### - Offset [in]

 The offset to the first view to set. 


#### - phUnorderedAccessView [in]

 An array of handles to the driver's private data for unordered access view objects to set. Note that some handle values can be <b>NULL</b>. 


#### - pUAVInitialCounts [in]

An array of append and consume buffer offsets. A value of -1 indicates that the current offset should be kept. Any other values set the hidden counter for that appendable and consumable UAV. <i>pUAVInitialCounts</i> is only relevant for UAVs  of the <i>phUnorderedAccessView</i> array that were created with either <b>D3D11_DDI_BUFFER_UAV_FLAG_APPEND</b>  or <b>D3D11_DDI_BUFFER_UAV_FLAG_COUNTER</b> specified in the <b>Flags</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_buffer_unorderedaccessview.md">D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW</a> structure when the UAV was created; otherwise, the argument is ignored.


## -returns


None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.



## -remarks


The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Microsoft Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <i>CsSetUnorderedAccessViews</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.



## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_buffer_unorderedaccessview.md">D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11DDI_SETUNORDEREDACCESSVIEWS callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

