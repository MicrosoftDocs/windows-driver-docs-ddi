---
UID: NC:d3d10umddi.PFND3D10DDI_IA_SETINDEXBUFFER
title: PFND3D10DDI_IA_SETINDEXBUFFER (d3d10umddi.h)
description: The IaSetIndexBuffer function sets an index buffer for an input assembler.
old-location: display\iasetindexbuffer.htm
ms.assetid: 042ebb72-b794-4cb8-9d81-bd52a785f1e0
ms.date: 05/10/2018
ms.keywords: IaSetIndexBuffer, IaSetIndexBuffer callback function [Display Devices], PFND3D10DDI_IA_SETINDEXBUFFER, PFND3D10DDI_IA_SETINDEXBUFFER callback, UserModeDisplayDriverDx10_Functions_5b51e721-283c-447e-8170-17af90a29081.xml, d3d10umddi/IaSetIndexBuffer, display.iasetindexbuffer
ms.topic: callback
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
- IaSetIndexBuffer
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_IA_SETINDEXBUFFER callback function


## -description


The <i>IaSetIndexBuffer</i> function sets an index buffer for an input assembler.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hBuffer* [in]

A handle to the index buffer to set.

### -param Arg3

*Format* [in]

A DXGI_FORMAT-typed value that indicates the pixel format of the index buffer. Only the DXGI_FORMAT_R16_UINT and DXGI_FORMAT_R32_UINT formats are valid; all other formats are invalid. 

### -param Arg4

*Offset* [in]

The offset, in bytes, into the index buffer. 


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>IaSetIndexBuffer</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

