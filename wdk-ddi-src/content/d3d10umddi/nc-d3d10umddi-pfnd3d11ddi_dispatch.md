---
UID: NC:d3d10umddi.PFND3D11DDI_DISPATCH
title: PFND3D11DDI_DISPATCH (d3d10umddi.h)
description: The Dispatch function executes the compute shader.
old-location: display\dispatch.htm
ms.date: 05/10/2018
keywords: ["PFND3D11DDI_DISPATCH callback function"]
ms.keywords: Dispatch, Dispatch callback function [Display Devices], PFND3D11DDI_DISPATCH, PFND3D11DDI_DISPATCH callback, UserModeDisplayDriverDx11_Functions_1b4b62fc-3cc5-4506-9a61-30ee65f8ffcd.xml, d3d10umddi/Dispatch, display.dispatch
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Dispatch is supported beginning with the Windows 7 operating system.
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D11DDI_DISPATCH
 - d3d10umddi/PFND3D11DDI_DISPATCH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - PFND3D11DDI_DISPATCH
---

# PFND3D11DDI_DISPATCH callback function


## -description

The <b>Dispatch</b> function executes the compute shader.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*ThreadGroupCountX* [in]

 The size, in thread groups, of the x-dimension of the thread-group grid.  The maximum size is 65535.

### -param Arg3

*ThreadGroupCountY* [in]

 The size, in thread groups, of the y-dimension of the thread-group grid.  The maximum size is 65535.

### -param Arg4

*ThreadGroupCountZ* [in]

 The size, in thread groups, of the z-dimension of the thread-group grid.  The maximum size is 65535.

## -remarks

The driver can use the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 



The Direct3D runtime calls the driver's <b>Dispatch</b> function on the display device to execute the compute shader.  A compiled compute shader defines the set of instructions to execute per thread and the number of threads to run per group.  The thread-group parameters (<i>ThreadGroupCountX</i>, <i>ThreadGroupCountY</i>, and <i>ThreadGroupCountZ</i>) indicate how many thread groups to execute. Each thread group contains the same number of threads, as defined by the compiled compute shader.  The thread groups are organized in a three-dimensional grid. The total number of thread groups that the compiled compute shader executes is determined by the following calculation:

```cpp
ThreadGroupCountX * ThreadGroupCountY * ThreadGroupCountZ
```

In particular, if any of the values in the thread-group parameters are 0, the <b>Dispatch</b> function does nothing.  

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <b>Dispatch</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

