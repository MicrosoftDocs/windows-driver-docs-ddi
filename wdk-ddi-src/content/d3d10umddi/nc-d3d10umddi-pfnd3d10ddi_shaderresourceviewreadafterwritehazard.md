---
UID: NC:d3d10umddi.PFND3D10DDI_SHADERRESOURCEVIEWREADAFTERWRITEHAZARD
title: PFND3D10DDI_SHADERRESOURCEVIEWREADAFTERWRITEHAZARD
author: windows-driver-content
description: The ShaderResourceViewReadAfterWriteHazard function informs the user-mode display driver that the specified resource was used as an output from the graphics processing unit (GPU) and that the resource will be used as an input to the GPU.
old-location: display\shaderresourceviewreadafterwritehazard.htm
old-project: display
ms.assetid: bb391154-a9ff-4032-b86e-81fa4ea2e37c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.shaderresourceviewreadafterwritehazard, ShaderResourceViewReadAfterWriteHazard callback function [Display Devices], ShaderResourceViewReadAfterWriteHazard, PFND3D10DDI_SHADERRESOURCEVIEWREADAFTERWRITEHAZARD, PFND3D10DDI_SHADERRESOURCEVIEWREADAFTERWRITEHAZARD, d3d10umddi/ShaderResourceViewReadAfterWriteHazard, UserModeDisplayDriverDx10_Functions_fa240239-13b6-43b1-a5c7-137d3d793e0c.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3d10umddi.h
apiname:
-	ShaderResourceViewReadAfterWriteHazard
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3D10DDI_SHADERRESOURCEVIEWREADAFTERWRITEHAZARD callback


## -description


The <i>ShaderResourceViewReadAfterWriteHazard</i> function informs the user-mode display driver that the specified resource was used as an output from the graphics processing unit (GPU) and that the resource will be used as an input to the GPU. A shader resource view is also provided to indicate which view caused the hazard. 


## -prototype


````
PFND3D10DDI_SHADERRESOURCEVIEWREADAFTERWRITEHAZARD ShaderResourceViewReadAfterWriteHazard;

VOID APIENTRY ShaderResourceViewReadAfterWriteHazard(
  _In_ D3D10DDI_HDEVICE             hDevice,
  _In_ D3D10DDI_HSHADERRESOURCEVIEW hShaderResourceView,
  _In_ D3D10DDI_HRESOURCE           hResource
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE



### -param D3D10DDI_HSHADERRESOURCEVIEW



### -param D3D10DDI_HRESOURCE






#### - hDevice [in]

 A handle to the display device (graphics context).


#### - hShaderResourceView [in]

 A handle to the driver's private data for a shader resource view object. 


#### - hResource [in]

 A handle to the resource.


## -returns


None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.



## -remarks


The Microsoft Direct3D runtime calls <i>ShaderResourceViewReadAfterWriteHazard</i> immediately before the specified resource is bound as an input to the GPU. 

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>ShaderResourceViewReadAfterWriteHazard</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.



## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_SHADERRESOURCEVIEWREADAFTERWRITEHAZARD callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

