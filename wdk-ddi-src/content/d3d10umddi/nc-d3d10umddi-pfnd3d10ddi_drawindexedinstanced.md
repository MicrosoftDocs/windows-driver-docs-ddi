---
UID: NC:d3d10umddi.PFND3D10DDI_DRAWINDEXEDINSTANCED
title: PFND3D10DDI_DRAWINDEXEDINSTANCED (d3d10umddi.h)
description: The DrawIndexedInstanced function draws particular instances of indexed primitives.
old-location: display\drawindexedinstanced.htm
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_DRAWINDEXEDINSTANCED callback function"]
ms.keywords: DrawIndexedInstanced, DrawIndexedInstanced callback function [Display Devices], PFND3D10DDI_DRAWINDEXEDINSTANCED, PFND3D10DDI_DRAWINDEXEDINSTANCED callback, UserModeDisplayDriverDx10_Functions_7452fd0b-4fff-4321-b0ce-464ac0ad2f6d.xml, d3d10umddi/DrawIndexedInstanced, display.drawindexedinstanced
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D10DDI_DRAWINDEXEDINSTANCED
 - d3d10umddi/PFND3D10DDI_DRAWINDEXEDINSTANCED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - DrawIndexedInstanced
---

# PFND3D10DDI_DRAWINDEXEDINSTANCED callback function


## -description

The <b>DrawIndexedInstanced</b> function draws particular instances of indexed primitives.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*IndexCountPerInstance* [in]

The number of indexes per instance of the index buffer that indexes are read from to draw the primitives.

### -param Arg3

*InstanceCount* [in]

The number of instances of the index buffer that indexes are read from to draw the primitives.

### -param Arg4

*StartIndexLocation* [in]

The first index in the index buffer that indexes are read from to draw the primitives.

### -param Arg5

*BaseVertexLocation* [in]

The number that should be added to each index that is referenced by the various primitives to determine the actual index of the vertex elements in each vertex stream.

### -param Arg6

*StartInstanceLocation* [in]

The first instance of the index buffer that indexes are read from to draw the primitives.

## -remarks

The driver can use the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code.  









The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>DrawIndexedInstanced</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
