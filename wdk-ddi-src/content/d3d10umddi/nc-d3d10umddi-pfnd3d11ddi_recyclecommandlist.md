---
UID: NC:d3d10umddi.PFND3D11DDI_RECYCLECOMMANDLIST
title: PFND3D11DDI_RECYCLECOMMANDLIST (d3d10umddi.h)
description: The RecycleCommandList function recycles a command list.
old-location: display\recyclecommandlist.htm
ms.assetid: 4cff7f3d-ba13-4389-bafc-edffc0697ce9
ms.date: 05/10/2018
keywords: ["PFND3D11DDI_RECYCLECOMMANDLIST callback function"]
ms.keywords: PFND3D11DDI_RECYCLECOMMANDLIST, PFND3D11DDI_RECYCLECOMMANDLIST callback, RecycleCommandList, RecycleCommandList callback function [Display Devices], UserModeDisplayDriverDx11_Functions_a917a4c2-4226-46e8-a696-8c51b2960bda.xml, d3d10umddi/RecycleCommandList, display.recyclecommandlist
f1_keywords:
 - "d3d10umddi/RecycleCommandList"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: RecycleCommandList is supported beginning with the Windows 7 operating system.
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
- RecycleCommandList
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11DDI_RECYCLECOMMANDLIST callback function


## -description


The <i>RecycleCommandList</i> function recycles a command list.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hCommandList* [in]

An immediate-context handle to the driver's private data for the command list to recycle. 


## -remarks

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 



The driver is only required to implement <i>RecycleCommandList</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 threading-capability bit. The driver can return D3D11DDICAPS_COMMANDLISTS_BUILD_2 in the <b>Caps</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_threading_caps">D3D11DDI_THREADING_CAPS</a> structure from a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10_2ddi_getcaps">GetCaps(D3D10_2)</a> function.

For more information about <i>RecycleCommandList</i>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/supporting-command-lists">Optimization for Small Command Lists</a>.

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED. However, if device removal interferes with the operation of <i>RecycleCommandList</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_threading_caps">D3D11DDI_THREADING_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10_2ddi_getcaps">GetCaps(D3D10_2)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
 

 

