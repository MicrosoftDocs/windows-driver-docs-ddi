---
UID: NC:d3d10umddi.PFND3D11DDI_DRAWINDEXEDINSTANCEDINDIRECT
title: PFND3D11DDI_DRAWINDEXEDINSTANCEDINDIRECT (d3d10umddi.h)
description: The DrawIndexedInstancedIndirect function draws particular instances of indexed primitives.
old-location: display\drawindexedinstancedindirect.htm
ms.assetid: 3debfb11-4de9-456b-a094-feb2f68e96a5
ms.date: 05/10/2018
ms.keywords: DrawIndexedInstancedIndirect, DrawIndexedInstancedIndirect callback function [Display Devices], PFND3D11DDI_DRAWINDEXEDINSTANCEDINDIRECT, PFND3D11DDI_DRAWINDEXEDINSTANCEDINDIRECT callback, UserModeDisplayDriverDx11_Functions_18c492b3-4d4b-413c-82c3-7290af5aade6.xml, d3d10umddi/DrawIndexedInstancedIndirect, display.drawindexedinstancedindirect
ms.topic: callback
f1_keywords:
 - "d3d10umddi/DrawIndexedInstancedIndirect"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: DrawIndexedInstancedIndirect is supported beginning with the Windows 7 operating system.
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
- D3d10umddi.h
api_name:
- DrawIndexedInstancedIndirect
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11DDI_DRAWINDEXEDINSTANCEDINDIRECT callback function


## -description


The <b>DrawIndexedInstancedIndirect</b> function draws particular instances of indexed primitives. 


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hBufferForArgs*

A handle to a buffer that contains the arguments for <b>DrawIndexedInstancedIndirect</b> to process. The buffer contains the following tightly packed structure:

```cpp
struct DrawIndexedInstancedIndirectArgs {
  UINT IndexCountPerInstance; 
  UINT InstanceCount;
  UINT StartIndexLocation;
  INT BaseVertexLocation;
  UINT StartInstanceLocation;
}
```

For more information about these arguments, see the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_drawindexedinstanced">DrawIndexedInstanced</a> reference page. 

### -param Arg3

*AlignedByteOffsetForArgs*

The offset, in bytes, into the buffer that <i>hBufferForArgs</i> specifies. <i>AlignedByteOffsetForArgs</i> must be a multiple of 4. 





## -returns



None

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the Remarks section. 




## -remarks



The <b>DrawIndexedInstancedIndirect</b> function performs the same task as the call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_drawindexedinstanced">DrawIndexedInstanced</a> function. However, <b>DrawIndexedInstancedIndirect</b> obtains information about the index primitives from the contents of the buffer that the <i>hBufferForArgs</i> parameter specifies. <b>DrawIndexedInstancedIndirect</b> reads the contents of the buffer, starting at the byte offset that the <i>AlignedByteOffsetForArgs</i> parameter specifies.

When the Direct3D runtime calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createresource">CreateResource(D3D11)</a> function to create the buffer resource that the <i>hBufferForArgs</i> parameter specifies, the runtime must set the D3D11_DDI_RESOURCE_MISC_DRAWINDIRECT_ARGS flag in the <b>MiscFlags</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createresource">D3D11DDIARG_CREATERESOURCE</a> structure.

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <b>DrawIndexedInstancedIndirect</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createresource">CreateResource(D3D11)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createresource">D3D11DDIARG_CREATERESOURCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_drawindexedinstanced">DrawIndexedInstanced</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
 

 

