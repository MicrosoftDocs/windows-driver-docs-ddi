---
UID: NC:d3d10umddi.PFND3D10DDI_SETCONSTANTBUFFERS
title: PFND3D10DDI_SETCONSTANTBUFFERS
author: windows-driver-content
description: The CsSetConstantBuffers function sets constant buffers for a compute shader.
old-location: display\cssetconstantbuffers.htm
ms.assetid: 159ee0ac-7ddf-4ffd-a07f-3d58130b90e8
ms.date: 05/10/2018
ms.keywords: CsSetConstantBuffers, CsSetConstantBuffers callback function [Display Devices], PFND3D10DDI_SETCONSTANTBUFFERS, PFND3D10DDI_SETCONSTANTBUFFERS callback, UserModeDisplayDriverDx11_Functions_ae0b7e35-f8c5-428d-97d0-e22d5b609c72.xml, d3d10umddi/CsSetConstantBuffers, display.cssetconstantbuffers
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CsSetConstantBuffers is supported beginning with the Windows 7 operating system.
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
-	CsSetConstantBuffers
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_SETCONSTANTBUFFERS callback function


## -description


The <b>CsSetConstantBuffers</b> function sets constant buffers for a compute shader. 


## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).


### -param StartSlot

[in] The starting constant buffer to set.

### -param NumBuffers 

[in] The total number of buffers to set. 


### -param *

*phBuffers* [in]

An array of handles to the constant buffers, beginning with the buffer that <b>StartBuffer</b> specifies.


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



Buffers that the <b>CsSetConstantBuffers</b> function specifies are created with the D3D10_BIND_CONSTANT_BUFFER flag. 

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <b>CsSetConstantBuffers</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

The <b>VsSetConstantBuffers</b> function sets constant buffers for a vertex shader.

The <b>GsSetConstantBuffers</b> function sets constant buffers for a geometry shader.

The <b>HsSetConstantBuffers</b> function sets constant buffers for a hull shader.

The <b>PsSetConstantBuffers</b> function sets constant buffers for a pixel shader.

The <b>DsSetConstantBuffers</b> function sets constant buffers for a domain shader.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

