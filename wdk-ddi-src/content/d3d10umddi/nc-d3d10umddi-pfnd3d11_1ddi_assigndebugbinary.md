---
UID: NC:d3d10umddi.PFND3D11_1DDI_ASSIGNDEBUGBINARY
title: PFND3D11_1DDI_ASSIGNDEBUGBINARY
author: windows-driver-content
description: Provides the full shader binary that is available after shader creation. The full shader binary lets a driver retrieve debugging information or other shader binary information that would not normally be available to the driver.
old-location: display\assigndebugbinary.htm
old-project: display
ms.assetid: eb1e3c27-71c1-4920-9aa4-3253306fa3f4
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.assigndebugbinary, AssignDebugBinary callback function [Display Devices], AssignDebugBinary, PFND3D11_1DDI_ASSIGNDEBUGBINARY, PFND3D11_1DDI_ASSIGNDEBUGBINARY, d3d10umddi/AssignDebugBinary, display.pfnassigndebugbinary, display.assigndebugbinary_d3d11_1_
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	D3d10umddi.h
apiname:
-	AssignDebugBinary
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3D11_1DDI_ASSIGNDEBUGBINARY callback


## -description


Provides the full shader binary that is available after shader creation. The full shader binary lets a driver retrieve debugging information or other shader binary information that would not normally be available to the driver.


## -prototype


````
PFND3D11_1DDI_ASSIGNDEBUGBINARY AssignDebugBinary;

VOID APIENTRY* AssignDebugBinary(
             D3D10DDI_HDEVICE hDevice,
             D3D10DDI_HSHADER hShader,
             UINT             uBinarySize,
  _In_ const VOID             *pBinary
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param D3D10DDI_HSHADER


### -param uBinarySize

The size, in bytes, of the full shader binary.


### -param *pBinary [in]

A pointer to the full shader binary.


#### - hDevice

A handle to the display device (graphics context).


#### - hShader

A handle to the driver's private data for the shader object.


## -returns



None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



<i>AssignDebugBinary</i> is called only if all of the following are true:

<ul>
<li>The device can be debugged.</li>
<li>The user-mode display driver has set the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_d3d11_options_data.md">D3D11_1DDI_D3D11_OPTIONS_DATA</a>.<b>AssignDebugBinarySupport</b> flag to <b>TRUE</b>.</li>
<li>A shader creation function  <i>CreateXxxShaderXxx</i> has been called, has succeeded, and has returned a handle to the shader.</li>
</ul>
The driver should not encounter any error, except for <b>D3DDDIERR_DEVICEREMOVED</b>. Therefore, if the driver passes any error, except for <b>D3DDDIERR_DEVICEREMOVED</b>, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Microsoft Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return <b>D3DDDIERR_DEVICEREMOVED</b>; however, if device removal interfered with the operation of <i>AssignDebugBinary</i> (which typically should not happen), the driver can return <b>D3DDDIERR_DEVICEREMOVED</b>.




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_d3d11_options_data.md">D3D11_1DDI_D3D11_OPTIONS_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_ASSIGNDEBUGBINARY callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

