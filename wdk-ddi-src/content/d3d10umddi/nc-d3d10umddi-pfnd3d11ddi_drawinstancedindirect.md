---
UID: NC:d3d10umddi.PFND3D11DDI_DRAWINSTANCEDINDIRECT
title: PFND3D11DDI_DRAWINSTANCEDINDIRECT (d3d10umddi.h)
description: The DrawInstancedIndirect function draws particular instances of non-indexed primitives.
old-location: display\drawinstancedindirect.htm
ms.assetid: 99520dae-3934-496f-80bf-e5b306554415
ms.date: 05/10/2018
ms.keywords: DrawInstancedIndirect, DrawInstancedIndirect callback function [Display Devices], PFND3D11DDI_DRAWINSTANCEDINDIRECT, PFND3D11DDI_DRAWINSTANCEDINDIRECT callback, UserModeDisplayDriverDx11_Functions_40c5a4c2-55dd-4ec1-ae2e-99fbe6ce11a9.xml, d3d10umddi/DrawInstancedIndirect, display.drawinstancedindirect
ms.topic: callback
f1_keywords:
 - "d3d10umddi/DrawInstancedIndirect"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: DrawInstancedIndirect is supported beginning with the Windows 7 operating system.
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
- DrawInstancedIndirect
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11DDI_DRAWINSTANCEDINDIRECT callback function


## -description


The <b>DrawInstancedIndirect</b> function draws particular instances of non-indexed primitives.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hBufferForArgs* [in]

A handle to a buffer that contains the arguments for <b>DrawInstancedIndirect</b> to process. The buffer contains the following tightly packed structure:

```cpp
struct DrawInstancedIndirectArgs {
  UINT VertexCountPerInstance; 
  UINT InstanceCount;
  UINT StartVertexLocation;
  UINT StartInstanceLocation;
}
```

For more information about these arguments, see the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_drawinstanced">DrawInstanced</a> reference page. 


### -param Arg3

*AlignedByteOffsetForArgs* [in]

The offset, in bytes, into the buffer that <i>hBufferForArgs</i> specifies. <i>AlignedByteOffsetForArgs</i> must be a multiple of four. 


## -returns



None

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The <b>DrawInstancedIndirect</b> function performs the same task as the call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_drawinstanced">DrawInstanced</a> function. However, <b>DrawInstancedIndirect</b> obtains information about the non-indexed primitives from the contents of the buffer that the <i>hBufferForArgs</i> parameter specifies. <b>DrawInstancedIndirect</b> reads the contents of the buffer, starting at the byte offset that the <i>AlignedByteOffsetForArgs</i> parameter specifies.

When the Direct3D runtime calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createresource">CreateResource(D3D11)</a> function to create the buffer resource that the <i>hBufferForArgs</i> parameter specifies, the runtime must set the D3D11_DDI_RESOURCE_MISC_DRAWINDIRECT_ARGS flag in the <b>MiscFlags</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createresource">D3D11DDIARG_CREATERESOURCE</a> structure.

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <b>DrawInstancedIndirect</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createresource">CreateResource(D3D11)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createresource">D3D11DDIARG_CREATERESOURCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_drawinstanced">DrawInstanced</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
 

 

