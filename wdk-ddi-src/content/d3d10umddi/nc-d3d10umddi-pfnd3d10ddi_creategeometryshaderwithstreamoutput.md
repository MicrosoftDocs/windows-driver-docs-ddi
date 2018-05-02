---
UID: NC:d3d10umddi.PFND3D10DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
title: PFND3D10DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
author: windows-driver-content
description: The CreateGeometryShaderWithStreamOutput function creates a geometry shader with stream output.
old-location: display\creategeometryshaderwithstreamoutput.htm
old-project: display
ms.assetid: 6ad1573d-4377-4795-8511-5d6cae96ee4f
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: CreateGeometryShaderWithStreamOutput, CreateGeometryShaderWithStreamOutput callback function [Display Devices], PFND3D10DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT, PFND3D10DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT callback, UserModeDisplayDriverDx10_Functions_e7442d66-9ff1-4ac0-b72d-cf23a1f34017.xml, d3d10umddi/CreateGeometryShaderWithStreamOutput, display.creategeometryshaderwithstreamoutput
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	CreateGeometryShaderWithStreamOutput
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3D10DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT callback function


## -description


The <b>CreateGeometryShaderWithStreamOutput</b> function creates a geometry shader with stream output.


## -parameters




### -param Arg1


### -param *








### -param Arg2


### -param Arg3


#### - hDevice [in]

 A handle to the display device (graphics context).


#### - hRTShader [in]

 A handle to the geometry shader with stream output that the driver should use anytime it calls back into the Direct3D runtime. 


#### - hShader [in]

 A handle to the driver's private data for the geometry shader with stream output. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="https://msdn.microsoft.com/3e760b93-e859-4175-a24a-6bf3648db6db">CalcPrivateGeometryShaderWithStreamOutput</a> function. The handle is really just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its shader object. 


#### - pCreateGeometryWithShaderOutput [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541681">D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT</a> structure that describes the parameters that the user-mode display driver uses to create a geometry shader with stream output. 


#### - pSignatures [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541746">D3D10DDIARG_STAGE_IO_SIGNATURES</a> structure that makes up the shader's signature.


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver can pass E_OUTOFMEMORY (if the driver runs out of memory) or D3DDDIERR_DEVICEREMOVED (if the device has been removed) in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="https://msdn.microsoft.com/51a3e5aa-0f17-49a6-824d-7cfe8e0a1ded">DestroyShader</a> function to destroy the handle that the <i>hShader</i> parameter specifies.




## -see-also




<a href="https://msdn.microsoft.com/3e760b93-e859-4175-a24a-6bf3648db6db">CalcPrivateGeometryShaderWithStreamOutput</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541681">D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541746">D3D10DDIARG_STAGE_IO_SIGNATURES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/51a3e5aa-0f17-49a6-824d-7cfe8e0a1ded">DestroyShader</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

