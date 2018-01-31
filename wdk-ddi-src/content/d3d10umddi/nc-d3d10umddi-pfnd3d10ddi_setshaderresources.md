---
UID: NC:d3d10umddi.PFND3D10DDI_SETSHADERRESOURCES
title: PFND3D10DDI_SETSHADERRESOURCES
author: windows-driver-content
description: The CsSetShaderResources function sets resources for a compute shader.
old-location: display\cssetshaderresources.htm
old-project: display
ms.assetid: 29570c3b-eb3b-4d8f-b471-8f3ea6226e23
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.cssetshaderresources, CsSetShaderResources callback function [Display Devices], CsSetShaderResources, PFND3D10DDI_SETSHADERRESOURCES, PFND3D10DDI_SETSHADERRESOURCES, d3d10umddi/CsSetShaderResources, UserModeDisplayDriverDx11_Functions_0fe556e4-8c6f-4848-b502-d35744c60713.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CsSetShaderResources is supported beginning with the Windows 7 operating system.
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
-	CsSetShaderResources
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3D10DDI_SETSHADERRESOURCES callback


## -description


The <b>CsSetShaderResources</b> function sets resources for a compute shader.


## -prototype


````
PFND3D10DDI_SETSHADERRESOURCES CsSetShaderResources;

VOID APIENTRY CsSetShaderResources(
  _In_       D3D10DDI_HDEVICE             hDevice,
  _In_       UINT                         Offset,
  _In_       UINT                         NumViews,
  _In_ const D3D10DDI_HSHADERRESOURCEVIEW *phShaderResourceViews
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE



### -param StartSlot



#### - NumViews [in]

 The total number of views to set. 


### -param *






#### - hDevice [in]

 A handle to the display device (graphics context).


#### - Offset [in]

 The offset to the first view to set. 


#### - phShaderResourceViews [in]

 An array of handles to the shader resource views, beginning at the offset that <i>Offset</i> specifies.


## -returns


None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.



## -remarks


The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <b>CsSetShaderResources</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.



## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_SETSHADERRESOURCES callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

