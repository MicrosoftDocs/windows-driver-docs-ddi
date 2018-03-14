---
UID: NC:d3d10umddi.PFND3D10DDI_SETSHADER
title: PFND3D10DDI_SETSHADER
author: windows-driver-content
description: The CsSetShader function sets the compute shader code so that all of the subsequent dispatching operations use that code.
old-location: display\cssetshader.htm
old-project: display
ms.assetid: ab689c60-3099-4d69-a7e2-5edfb623cbc3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CsSetShader, CsSetShader callback function [Display Devices], PFND3D10DDI_SETSHADER, UserModeDisplayDriverDx11_Functions_4e96f922-1a22-45c3-9c50-a4b71a79f695.xml, d3d10umddi/CsSetShader, display.cssetshader
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CsSetShader is supported beginning with the Windows 7 operating system.
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
-	CsSetShader
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_SETSHADER callback


## -description


The <b>CsSetShader</b> function sets the compute shader code so that all of the subsequent dispatching operations use that code. 


## -prototype


````
PFND3D10DDI_SETSHADER CsSetShader;

VOID APIENTRY CsSetShader(
  _In_ D3D10DDI_HDEVICE hDevice,
  _In_ D3D10DDI_HSHADER hShader
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param D3D10DDI_HSHADER








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - hShader [in]

 A handle to the compute shader code object. 


## -returns



None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of<b>CsSetShader</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a>



 

 


