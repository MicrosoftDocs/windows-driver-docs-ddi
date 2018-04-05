---
UID: NC:d3d10umddi.PFND3D11DDI_CLEARUNORDEREDACCESSVIEWUINT
title: PFND3D11DDI_CLEARUNORDEREDACCESSVIEWUINT
author: windows-driver-content
description: The ClearUnorderedAccessViewUINT function clears the specified unordered-access view by setting it to a constant value.
old-location: display\clearunorderedaccessviewuint.htm
old-project: display
ms.assetid: 7cdc81a9-e468-4da8-bc32-9e9cea1fd60d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: ClearUnorderedAccessViewUINT, ClearUnorderedAccessViewUINT callback function [Display Devices], PFND3D11DDI_CLEARUNORDEREDACCESSVIEWUINT, UserModeDisplayDriverDx11_Functions_c31370b0-9955-4ccb-b540-92b15fc27cc5.xml, d3d10umddi/ClearUnorderedAccessViewUINT, display.clearunorderedaccessviewuint
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: ClearUnorderedAccessViewUINT is supported beginning with the Windows 7 operating system.
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
-	ClearUnorderedAccessViewUINT
product:
- Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11DDI_CLEARUNORDEREDACCESSVIEWUINT callback


## -description


The <b>ClearUnorderedAccessViewUINT</b> function clears the specified unordered-access view by setting it to a constant value. 


## -parameters




### -param Arg1


### -param Arg2


### -param UINT[4]








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - hUnorderedAccessView [in]

 A handle to the unordered-access view to clear. 


#### - pUints [in]

 A four-element array of unsigned integers that the driver uses to clear an unordered-access view. 


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the Remarks section. 




## -remarks



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <b>ClearUnorderedAccessViewUINT</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

