---
UID: NC:d3d10umddi.PFND3D11DDI_SETUNORDEREDACCESSVIEWS
title: PFND3D11DDI_SETUNORDEREDACCESSVIEWS
author: windows-driver-content
description: The CsSetUnorderedAccessViews function sets unordered access view (UAV) objects for a compute shader.
old-location: display\cssetunorderedaccessviews.htm
ms.assetid: ab8c529b-19e2-4a2a-af68-0e3998829788
ms.date: 05/10/2018
ms.keywords: CsSetUnorderedAccessViews, CsSetUnorderedAccessViews callback function [Display Devices], PFND3D11DDI_SETUNORDEREDACCESSVIEWS, PFND3D11DDI_SETUNORDEREDACCESSVIEWS callback, UserModeDisplayDriverDx11_Functions_2e3d1f2b-5113-4cbe-afa8-11f4caf88859.xml, d3d10umddi/CsSetUnorderedAccessViews, display.cssetunorderedaccessviews
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	CsSetUnorderedAccessViews
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11DDI_SETUNORDEREDACCESSVIEWS callback function


## -description


The <i>CsSetUnorderedAccessViews</i> function sets unordered access view (UAV) objects for a compute shader.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param StartSlot

The offset to the first view to set. 

### -param NumViews [in]

The total number of views to set. 


### -param *

*pUAVInitialCounts* [in]

An array of append and consume buffer offsets. A value of -1 indicates that the current offset should be kept. Any other values set the hidden counter for that appendable and consumable UAV. <i>pUAVInitialCounts</i> is only relevant for UAVs  of the <i>phUnorderedAccessView</i> array that were created with either <b>D3D11_DDI_BUFFER_UAV_FLAG_APPEND</b>  or <b>D3D11_DDI_BUFFER_UAV_FLAG_COUNTER</b> specified in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542033">D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW</a> structure when the UAV was created; otherwise, the argument is ignored.

### -param *

*phUnorderedAccessView* [in]

An array of handles to the driver's private data for unordered access view objects to set. Note that some handle values can be <b>NULL</b>. 


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function, the Microsoft Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <i>CsSetUnorderedAccessViews</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542033">D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

