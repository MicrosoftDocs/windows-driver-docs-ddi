---
UID: NC:d3d10umddi.PFND3D11DDI_CLEARUNORDEREDACCESSVIEWFLOAT
title: PFND3D11DDI_CLEARUNORDEREDACCESSVIEWFLOAT (d3d10umddi.h)
description: The ClearUnorderedAccessViewFLOAT function clears the specified unordered-access view by setting it to a constant value.
old-location: display\clearunorderedaccessviewfloat.htm
ms.assetid: 31734efd-0c17-4476-918d-942c015072bd
ms.date: 05/10/2018
keywords: ["PFND3D11DDI_CLEARUNORDEREDACCESSVIEWFLOAT callback function"]
ms.keywords: ClearUnorderedAccessViewFLOAT, ClearUnorderedAccessViewFLOAT callback function [Display Devices], PFND3D11DDI_CLEARUNORDEREDACCESSVIEWFLOAT, PFND3D11DDI_CLEARUNORDEREDACCESSVIEWFLOAT callback, UserModeDisplayDriverDx11_Functions_002fe9ed-bdd4-46c4-b7fe-6b783ab47060.xml, d3d10umddi/ClearUnorderedAccessViewFLOAT, display.clearunorderedaccessviewfloat
f1_keywords:
 - "d3d10umddi/ClearUnorderedAccessViewFLOAT"
 - "ClearUnorderedAccessViewFLOAT"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: ClearUnorderedAccessViewFLOAT is supported beginning with the Windows 7 operating system.
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
- ClearUnorderedAccessViewFLOAT
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11DDI_CLEARUNORDEREDACCESSVIEWFLOAT callback function


## -description


The <b>ClearUnorderedAccessViewFLOAT</b> function clears the specified unordered-access view by setting it to a constant value. 


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hUnorderedAccessView* [in]

A handle to the unordered-access view to clear. 

### -param FLOAT
[4]
[in]

A four-element array of single-precision float vectors that the driver uses to clear an unordered-access view. 


## -remarks

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <b>ClearUnorderedAccessViewFLOAT</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
 

 

