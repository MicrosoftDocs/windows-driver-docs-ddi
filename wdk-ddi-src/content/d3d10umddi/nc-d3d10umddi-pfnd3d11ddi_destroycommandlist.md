---
UID: NC:d3d10umddi.PFND3D11DDI_DESTROYCOMMANDLIST
title: PFND3D11DDI_DESTROYCOMMANDLIST
author: windows-driver-content
description: The DestroyCommandList function destroys a command list.
old-location: display\destroycommandlist.htm
old-project: display
ms.assetid: 9f03c193-f017-4189-a082-908e28a2e9f7
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DestroyCommandList, DestroyCommandList callback function [Display Devices], PFND3D11DDI_DESTROYCOMMANDLIST, PFND3D11DDI_DESTROYCOMMANDLIST callback, UserModeDisplayDriverDx11_Functions_cf01bd33-1921-4d56-a377-f8eda35a8d04.xml, d3d10umddi/DestroyCommandList, display.destroycommandlist
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: DestroyCommandList is supported beginning with the Windows 7 operating system.
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
-	DestroyCommandList
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3D11DDI_DESTROYCOMMANDLIST callback function


## -description


The <b>DestroyCommandList</b> function destroys a command list.


## -parameters




### -param Arg1


### -param Arg2








#### - hCommandList [in]

 A handle to the driver's private data for the command list to destroy. The Microsoft Direct3D runtime frees the memory region that it previously allocated for the command list. Therefore, the driver can no longer access this memory region. 


#### - hDevice [in]

 A handle to the display device (graphics context).


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver is only required to implement <b>DestroyCommandList</b> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability that can be returned in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542163">D3D11DDI_THREADING_CAPS</a> structure from a call to the <a href="https://msdn.microsoft.com/83cd5f34-5f12-4ead-ad33-366fc3c6e804">GetCaps(D3D10_2)</a> function.

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <b>DestroyCommandList</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

The driver can implement a <b>DestroyCommandList</b> function that contains a <b>switch</b> statement to process the destruction of command lists and the lightweight destruction of command lists. That is, the driver can implement one <b>DestroyCommandList</b>, and can set the <b>pfnRecycleDestroyCommandList</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a> structure to point to <b>DestroyCommandList</b> along with the <b>pfnRecycleDestroyCommandList</b> member of D3D11DDI_DEVICEFUNCS to point to <b>DestroyCommandList</b>. However, to improve performance, the driver can implement separate <b>DestroyCommandList</b> and <b>RecycleDestroyCommandList</b> functions.

For more information about <b>RecycleDestroyCommandList</b>, see <a href="https://msdn.microsoft.com/7bede247-680d-4fd3-a10b-6ef63f0a88ec">Optimization for Small Command Lists</a>.




## -see-also




<a href="https://msdn.microsoft.com/583bde52-ba21-44ce-9f48-8ace6f7a70cc">CreateCommandList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542163">D3D11DDI_THREADING_CAPS</a>



<a href="https://msdn.microsoft.com/83cd5f34-5f12-4ead-ad33-366fc3c6e804">GetCaps(D3D10_2)</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

