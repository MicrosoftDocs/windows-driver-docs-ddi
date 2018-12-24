---
UID: NC:d3d10umddi.PFND3D11DDI_DISPATCHINDIRECT
title: PFND3D11DDI_DISPATCHINDIRECT
description: The DispatchIndirect function executes the compute shader.
old-location: display\dispatchindirect.htm
ms.assetid: 0c818515-163f-48ba-ad57-f4405672c98f
ms.date: 05/10/2018
ms.keywords: DispatchIndirect, DispatchIndirect callback function [Display Devices], PFND3D11DDI_DISPATCHINDIRECT, PFND3D11DDI_DISPATCHINDIRECT callback, UserModeDisplayDriverDx11_Functions_39c7b613-66de-4dd8-8b43-d1ae2a926e77.xml, d3d10umddi/DispatchIndirect, display.dispatchindirect
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	DispatchIndirect
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
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




## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The DispatchIndirect function performs the same task as the call to the driver's <a href="https://msdn.microsoft.com/6fbbf05a-efb0-4f24-8811-b87141cf2daa">Dispatch</a> function. The Direct3D runtime calls the driver's <b>DispatchIndirect</b> function on the display device to execute the compute shader over a number of threads in a grid of thread groups. However, <b>DispatchIndirect</b> obtains the number of thread groups to execute from the contents of the buffer that the <i>hBufferForArgs</i> parameter specifies.  <b>DispatchIndirect</b> reads three UINT values, starting at the byte offset that the <i>AlignedByteOffsetForArgs</i> parameter specifies.

When the Direct3D runtime calls the driver's <a href="https://msdn.microsoft.com/2dff9d2e-c497-422f-824b-a7101904fd67">CreateResource(D3D11)</a> function to create the buffer resource that the <i>hBufferForArgs</i> parameter specifies, the runtime must set the D3D11_DDI_RESOURCE_MISC_DRAWINDIRECT_ARGS flag in the <b>MiscFlags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542062">D3D11DDIARG_CREATERESOURCE</a> structure.

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <b>DispatchIndirect</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also




<a href="https://msdn.microsoft.com/2dff9d2e-c497-422f-824b-a7101904fd67">CreateResource(D3D11)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542062">D3D11DDIARG_CREATERESOURCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/6fbbf05a-efb0-4f24-8811-b87141cf2daa">Dispatch</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

