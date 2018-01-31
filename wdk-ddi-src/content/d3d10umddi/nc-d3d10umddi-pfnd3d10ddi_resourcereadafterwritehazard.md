---
UID: NC:d3d10umddi.PFND3D10DDI_RESOURCEREADAFTERWRITEHAZARD
title: PFND3D10DDI_RESOURCEREADAFTERWRITEHAZARD
author: windows-driver-content
description: The ResourceReadAfterWriteHazard function informs the user-mode display driver that the specified resource was used as an output from the graphics processing unit (GPU) and that the resource will be used as an input to the GPU.
old-location: display\resourcereadafterwritehazard.htm
old-project: display
ms.assetid: 4d7dd4f5-9792-48cb-bf69-3903ac9dda75
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.resourcereadafterwritehazard, ResourceReadAfterWriteHazard callback function [Display Devices], ResourceReadAfterWriteHazard, PFND3D10DDI_RESOURCEREADAFTERWRITEHAZARD, PFND3D10DDI_RESOURCEREADAFTERWRITEHAZARD, d3d10umddi/ResourceReadAfterWriteHazard, UserModeDisplayDriverDx10_Functions_6a240dd4-86e0-4876-b4c3-8dd2d3f086e8.xml
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
-	ResourceReadAfterWriteHazard
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3D10DDI_RESOURCEREADAFTERWRITEHAZARD callback


## -description


The <i>ResourceReadAfterWriteHazard</i> function informs the user-mode display driver that the specified resource was used as an output from the graphics processing unit (GPU) and that the resource will be used as an input to the GPU. 


## -prototype


````
PFND3D10DDI_RESOURCEREADAFTERWRITEHAZARD ResourceReadAfterWriteHazard;

VOID APIENTRY ResourceReadAfterWriteHazard(
  _In_ D3D10DDI_HDEVICE   hDevice,
  _In_ D3D10DDI_HRESOURCE hResource
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE



### -param D3D10DDI_HRESOURCE






#### - hDevice [in]

 A handle to the display device (graphics context).


#### - hResource [in]

 A handle to the resource.


## -returns


None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the Remarks section. 



## -remarks


The Microsoft Direct3D runtime calls <i>ResourceReadAfterWriteHazard</i> immediately before the specified resource is bound as an input to the GPU.

<i>ResourceReadAfterWriteHazard</i> is used with bind points other than <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md">GsSetShaderResources</a>, <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md">PsSetShaderResources</a>, and <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md">VsSetShaderResources</a> (for example, <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_ia_setindexbuffer.md">IaSetIndexBuffer</a>). Because these types of bind points accept only buffers, the entire resource is considered affected by the hazard, and not just a particular view.

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>ResourceReadAfterWriteHazard</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.



## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_RESOURCEREADAFTERWRITEHAZARD callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

