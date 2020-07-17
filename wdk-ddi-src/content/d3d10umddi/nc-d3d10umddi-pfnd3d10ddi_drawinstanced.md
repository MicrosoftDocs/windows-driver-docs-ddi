---
UID: NC:d3d10umddi.PFND3D10DDI_DRAWINSTANCED
title: PFND3D10DDI_DRAWINSTANCED (d3d10umddi.h)
description: The DrawInstanced function draws particular instances of nonindexed primitives.
old-location: display\drawinstanced.htm
ms.assetid: c539cf8b-e056-476a-9b23-7e360917a7d9
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_DRAWINSTANCED callback function"]
ms.keywords: DrawInstanced, DrawInstanced callback function [Display Devices], PFND3D10DDI_DRAWINSTANCED, PFND3D10DDI_DRAWINSTANCED callback, UserModeDisplayDriverDx10_Functions_15fe8a07-36ca-4ab1-8570-01250eed4866.xml, d3d10umddi/DrawInstanced, display.drawinstanced
f1_keywords:
 - "d3d10umddi/DrawInstanced"
 - "DrawInstanced"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
- DrawInstanced
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_DRAWINSTANCED callback function


## -description


The <b>DrawInstanced</b> function draws particular instances of nonindexed primitives.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*VertexCountPerInstance* [in]

The number of vertices per instance of the buffer that vertices are read from to draw the primitives.

### -param Arg3

*InstanceCount* [in]

The number of instances of the buffer that vertices are read from to draw the primitives.

### -param Arg4

*StartVertexLocation* [in]

The first vertex in the buffer that vertices are read from to draw the primitives.

### -param Arg5

*StartInstanceLocation* [in]

The first instance of the buffer that vertices are read from to draw the primitives. 



## -remarks

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <b>DrawInstanced</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
 

 

