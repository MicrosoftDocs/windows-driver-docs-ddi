---
UID: NC:d3d10umddi.PFND3D11DDI_CLEARUNORDEREDACCESSVIEWFLOAT
title: PFND3D11DDI_CLEARUNORDEREDACCESSVIEWFLOAT
author: windows-driver-content
description: The ClearUnorderedAccessViewFLOAT function clears the specified unordered-access view by setting it to a constant value.
old-location: display\clearunorderedaccessviewfloat.htm
old-project: display
ms.assetid: 31734efd-0c17-4476-918d-942c015072bd
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: ClearUnorderedAccessViewFLOAT, ClearUnorderedAccessViewFLOAT callback function [Display Devices], PFND3D11DDI_CLEARUNORDEREDACCESSVIEWFLOAT, UserModeDisplayDriverDx11_Functions_002fe9ed-bdd4-46c4-b7fe-6b783ab47060.xml, d3d10umddi/ClearUnorderedAccessViewFLOAT, display.clearunorderedaccessviewfloat
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	ClearUnorderedAccessViewFLOAT
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11DDI_CLEARUNORDEREDACCESSVIEWFLOAT callback


## -description


The <b>ClearUnorderedAccessViewFLOAT</b> function clears the specified unordered-access view by setting it to a constant value. 


## -prototype


````
PFND3D11DDI_CLEARUNORDEREDACCESSVIEWFLOAT ClearUnorderedAccessViewFLOAT;

VOID APIENTRY ClearUnorderedAccessViewFLOAT(
  _In_       D3D10DDI_HDEVICE              hDevice,
  _In_       D3D11DDI_HUNORDEREDACCESSVIEW hUnorderedAccessView,
  _In_ const FLOAT[4]                      pFloats
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param D3D11DDI_HUNORDEREDACCESSVIEW


### -param FLOAT[4]








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - hUnorderedAccessView [in]

 A handle to the unordered-access view to clear. 


#### - pFloats [in]

 A four-element array of single-precision float vectors that the driver uses to clear an unordered-access view. 


## -returns



None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the Remarks section. 




## -remarks



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <b>ClearUnorderedAccessViewFLOAT</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11DDI_CLEARUNORDEREDACCESSVIEWFLOAT callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

