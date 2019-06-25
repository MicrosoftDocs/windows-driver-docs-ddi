---
UID: NC:d3d10umddi.PFND3D11DDI_SETSHADER_WITH_IFACES
title: PFND3D11DDI_SETSHADER_WITH_IFACES (d3d10umddi.h)
description: The CsSetShaderWithIfaces function sets the compute shader code along with a group of interfaces so that all of the subsequent dispatching operations use that code and those interfaces.
old-location: display\cssetshaderwithifaces.htm
ms.assetid: 2e7170e8-2b77-45a7-9ff5-834452c13ddf
ms.date: 05/10/2018
ms.keywords: CsSetShaderWithIfaces, CsSetShaderWithIfaces callback function [Display Devices], PFND3D11DDI_SETSHADER_WITH_IFACES, PFND3D11DDI_SETSHADER_WITH_IFACES callback, UserModeDisplayDriverDx11_Functions_bffc7a50-c0dd-420e-b599-5fb1e223ef3c.xml, d3d10umddi/CsSetShaderWithIfaces, display.cssetshaderwithifaces
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3d10umddi.h
api_name:
- CsSetShaderWithIfaces
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11DDI_SETSHADER_WITH_IFACES callback function


## -description


The <b>CsSetShaderWithIfaces</b> function sets the compute shader code along with a group of interfaces so that all of the subsequent dispatching operations use that code and those interfaces. 


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hShader* [in]

A handle to the compute shader code object. 

### -param NumClassInstances [in]

The number of class instances for implementations of the interfaces. 


### -param *

*pPointerData* [in]

An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_pointerdata">D3D11DDIARG_POINTERDATA</a> structures. Each structure describes the location of the data that is referenced by a class instance that is assigned to an interface implementation. The number of elements in the array is specified by the <i>NumClassInstances</i> parameter. 

### -param *

*pIfaces* [in]

An array of function table identifiers. Each identifier corresponds to a class instance that is assigned to an interface implementation. The number of elements in the array is specified by the <i>NumClassInstances</i> parameter. 



## -returns



None

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




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

The driver can pass E_OUTOFMEMORY (if the driver runs out of memory) or D3DDDIERR_DEVICEREMOVED (if the device is removed) in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function. The Direct3D runtime determines that any other errors are critical. If the driver passes any errors, which includes D3DDDIERR_DEVICEREMOVED, the Direct3D runtime determines that the handle is invalid; therefore, the runtime does not call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyshader">DestroyShader</a> function to destroy the handle that the <i>hShader</i> parameter specifies.

The <b>GsSetShaderWithIfaces</b> function sets the geometry shader code along with a group of interfaces so that all of the subsequent drawing operations use that code and those interfaces. 

The <b>PsSetShaderWithIfaces</b> function sets the pixel shader code along with a group of interfaces so that all of the subsequent drawing operations use that code and those interfaces.

The <b>DsSetShaderWithIfaces</b> function sets the domain shader code along with a group of interfaces so that all of the subsequent drawing operations use that code and those interfaces.

The <b>HsSetShaderWithIfaces</b> function sets the hull shader code along with a group of interfaces so that all of the subsequent drawing operations use that code and those interfaces.

The <b>VsSetShaderWithIfaces</b> function sets the vertex shader code along with a group of interfaces so that all of the subsequent drawing operations use that code and those interfaces.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_pointerdata">D3D11DDIARG_POINTERDATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyshader">DestroyShader</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
 

 

