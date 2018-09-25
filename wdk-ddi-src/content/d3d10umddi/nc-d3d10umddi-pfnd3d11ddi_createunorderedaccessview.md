---
UID: NC:d3d10umddi.PFND3D11DDI_CREATEUNORDEREDACCESSVIEW
title: PFND3D11DDI_CREATEUNORDEREDACCESSVIEW
author: windows-driver-content
description: The CreateUnorderedAccessView function creates an unordered access view.
old-location: display\createunorderedaccessview.htm
ms.assetid: c5a258e7-6645-46bb-ab2c-a1c8f5e593b7
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: CreateUnorderedAccessView, CreateUnorderedAccessView callback function [Display Devices], PFND3D11DDI_CREATEUNORDEREDACCESSVIEW, PFND3D11DDI_CREATEUNORDEREDACCESSVIEW callback, UserModeDisplayDriverDx11_Functions_4b9c2d38-c780-47be-a5fa-dec2c860732b.xml, d3d10umddi/CreateUnorderedAccessView, display.createunorderedaccessview
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CreateUnorderedAccessView is supported beginning with the Windows 7 operating system.
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
-	CreateUnorderedAccessView
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11DDI_CREATEUNORDEREDACCESSVIEW callback function


## -description


The <b>CreateUnorderedAccessView</b> function creates an unordered access view.


## -parameters




### -param Arg1


### -param *


### -param Arg2


### -param Arg3








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - hRTUnorderedAccessView [in]

 A handle to the unordered access view that the driver should use when it calls back into the Direct3D runtime. 


#### - hUnorderedAccessView [in]

 A handle to the driver's private data for the unordered access view. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="https://msdn.microsoft.com/6aca5d33-c8c6-4c6b-a66a-e28a958cbc2e">CalcPrivateUnorderedAccessViewSize</a> function. The handle is  just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its unordered access view object. 


#### - pCreateUnorderedAccessView [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542086">D3D11DDIARG_CREATEUNORDEREDACCESSVIEW</a> structure that describes the parameters that the user-mode display driver uses to create an unordered access view. 


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver might run out of memory. Therefore, the driver can pass E_OUTOFMEMORY or D3DDDIERR_DEVICEREMOVED in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function. The Direct3D runtime determines that any other errors are critical. If the driver passes any errors, which includes D3DDDIERR_DEVICEREMOVED, the Direct3D runtime determines that the handle is invalid; therefore, the runtime does not call the <a href="https://msdn.microsoft.com/1bce3519-f333-4b47-b29b-bde1b5c3005c">DestroyUnorderedAccessView</a> function to destroy the handle that the <i>hUnorderedAccessView</i> parameter specifies.




## -see-also




<a href="https://msdn.microsoft.com/6aca5d33-c8c6-4c6b-a66a-e28a958cbc2e">CalcPrivateUnorderedAccessViewSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542086">D3D11DDIARG_CREATEUNORDEREDACCESSVIEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/1bce3519-f333-4b47-b29b-bde1b5c3005c">DestroyUnorderedAccessView</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

