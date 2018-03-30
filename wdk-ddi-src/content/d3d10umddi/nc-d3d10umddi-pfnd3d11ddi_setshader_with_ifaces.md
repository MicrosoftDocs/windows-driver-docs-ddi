---
UID: NC:d3d10umddi.PFND3D11DDI_SETSHADER_WITH_IFACES
title: PFND3D11DDI_SETSHADER_WITH_IFACES
author: windows-driver-content
description: The CsSetShaderWithIfaces function sets the compute shader code along with a group of interfaces so that all of the subsequent dispatching operations use that code and those interfaces.
old-location: display\cssetshaderwithifaces.htm
old-project: display
ms.assetid: 2e7170e8-2b77-45a7-9ff5-834452c13ddf
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CsSetShaderWithIfaces, CsSetShaderWithIfaces callback function [Display Devices], PFND3D11DDI_SETSHADER_WITH_IFACES, UserModeDisplayDriverDx11_Functions_bffc7a50-c0dd-420e-b599-5fb1e223ef3c.xml, d3d10umddi/CsSetShaderWithIfaces, display.cssetshaderwithifaces
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CsSetShaderWithIfaces is supported beginning with the Windows 7 operating system.
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
-	CsSetShaderWithIfaces
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11DDI_SETSHADER_WITH_IFACES callback


## -description


The <b>CsSetShaderWithIfaces</b> function sets the compute shader code along with a group of interfaces so that all of the subsequent dispatching operations use that code and those interfaces. 


## -parameters




### -param Arg1


### -param Arg2


### -param NumClassInstances [in]

 The number of class instances for implementations of the interfaces. 


### -param *








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - hShader [in]

 A handle to the compute shader code object. 


#### - pIfaces [in]

 An array of function table identifiers. Each identifier corresponds to a class instance that is assigned to an interface implementation. The number of elements in the array is specified by the <i>NumClassInstances</i> parameter. 


#### - pPointerData [in]

 An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff542095">D3D11DDIARG_POINTERDATA</a> structures. Each structure describes the location of the data that is referenced by a class instance that is assigned to an interface implementation. The number of elements in the array is specified by the <i>NumClassInstances</i> parameter. 


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



Each class instance for an interface implementation has the following pieces of information:  

<ul>
<li>
Code that is associated with that class instance

</li>
<li>
A location for the data that is used by that class instance

</li>
</ul>
The <i>NumClassInstances</i> parameter specifies the number of interfaces that must be assigned values at run time. For each interface, each element of the <b>pIfaces</b> array provides a function table identifier, and each element of the <b>pPointerData</b> array provides the data locations for a class instance that is assigned to the interface. 

The driver can pass E_OUTOFMEMORY (if the driver runs out of memory) or D3DDDIERR_DEVICEREMOVED (if the device is removed) in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function. The Direct3D runtime determines that any other errors are critical. If the driver passes any errors, which includes D3DDDIERR_DEVICEREMOVED, the Direct3D runtime determines that the handle is invalid; therefore, the runtime does not call the <a href="https://msdn.microsoft.com/51a3e5aa-0f17-49a6-824d-7cfe8e0a1ded">DestroyShader</a> function to destroy the handle that the <i>hShader</i> parameter specifies.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542095">D3D11DDIARG_POINTERDATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/51a3e5aa-0f17-49a6-824d-7cfe8e0a1ded">DestroyShader</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

