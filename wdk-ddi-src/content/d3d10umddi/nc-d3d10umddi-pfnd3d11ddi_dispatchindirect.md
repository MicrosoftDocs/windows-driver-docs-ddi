---
UID: NC:d3d10umddi.PFND3D11DDI_DISPATCHINDIRECT
title: PFND3D11DDI_DISPATCHINDIRECT (d3d10umddi.h)
description: The DispatchIndirect function executes the compute shader.
old-location: display\dispatchindirect.htm
ms.date: 05/10/2018
keywords: ["PFND3D11DDI_DISPATCHINDIRECT callback function"]
ms.keywords: DispatchIndirect, DispatchIndirect callback function [Display Devices], PFND3D11DDI_DISPATCHINDIRECT, PFND3D11DDI_DISPATCHINDIRECT callback, UserModeDisplayDriverDx11_Functions_39c7b613-66de-4dd8-8b43-d1ae2a926e77.xml, d3d10umddi/DispatchIndirect, display.dispatchindirect
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: DispatchIndirect is supported beginning with the Windows 7 operating system.
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
 - PFND3D11DDI_DISPATCHINDIRECT
 - d3d10umddi/PFND3D11DDI_DISPATCHINDIRECT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - PFND3D11DDI_DISPATCHINDIRECT
---

# PFND3D11DDI_DISPATCHINDIRECT callback function


## -description

The <b>DispatchIndirect</b> function executes the compute shader.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hBufferForArgs* [in]

A handle to a buffer that contains three UINT values that hold the sizes, in thread groups, of the X, Y, and Z dimensions of the thread-group grid. The buffer contains the following tightly packed structure:

```cpp
struct DispatchArgs {
  UINT ThreadGroupCountX; 
  UINT ThreadGroupCountY;
  UINT ThreadGroupCountZ;
}
```

### -param Arg3

*AlignedByteOffsetForArgs* [in]

The offset, in bytes, into the buffer that <i>hBufferForArgs</i> specifies. <i>AlignedByteOffsetForArgs</i> must be a multiple of 4.

## -remarks

The driver can use the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 



The DispatchIndirect function performs the same task as the call to the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_dispatch">Dispatch</a> function. The Direct3D runtime calls the driver's <b>DispatchIndirect</b> function on the display device to execute the compute shader over a number of threads in a grid of thread groups. However, <b>DispatchIndirect</b> obtains the number of thread groups to execute from the contents of the buffer that the <i>hBufferForArgs</i> parameter specifies.  <b>DispatchIndirect</b> reads three UINT values, starting at the byte offset that the <i>AlignedByteOffsetForArgs</i> parameter specifies.

When the Direct3D runtime calls the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createresource">CreateResource(D3D11)</a> function to create the buffer resource that the <i>hBufferForArgs</i> parameter specifies, the runtime must set the D3D11_DDI_RESOURCE_MISC_DRAWINDIRECT_ARGS flag in the <b>MiscFlags</b> member of the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createresource">D3D11DDIARG_CREATERESOURCE</a> structure.

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <b>DispatchIndirect</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createresource">CreateResource(D3D11)</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createresource">D3D11DDIARG_CREATERESOURCE</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_dispatch">Dispatch</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

