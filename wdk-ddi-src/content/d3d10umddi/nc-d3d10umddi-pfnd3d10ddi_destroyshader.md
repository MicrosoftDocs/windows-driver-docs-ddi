---
UID: NC:d3d10umddi.PFND3D10DDI_DESTROYSHADER
title: PFND3D10DDI_DESTROYSHADER
author: windows-driver-content
description: The DestroyShader function destroys the specified shader object. The shader object can be destoyed only if it is not currently bound to a display device.
old-location: display\destroyshader.htm
old-project: display
ms.assetid: 51a3e5aa-0f17-49a6-824d-7cfe8e0a1ded
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.destroyshader, DestroyShader callback function [Display Devices], DestroyShader, PFND3D10DDI_DESTROYSHADER, PFND3D10DDI_DESTROYSHADER, d3d10umddi/DestroyShader, UserModeDisplayDriverDx10_Functions_798387e4-b7c1-4b03-bef7-1dad6931b432.xml
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
-	DestroyShader
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_DESTROYSHADER callback


## -description


The <i>DestroyShader</i> function destroys the specified shader object. The shader object can be destoyed only if it is not currently bound to a display device. 


## -prototype


````
PFND3D10DDI_DESTROYSHADER DestroyShader;

VOID APIENTRY DestroyShader(
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

 A handle to the driver's private data for the shader object to destroy. The Microsoft Direct3D runtime will free the memory region that it previously allocated for the object. Therefore, the driver can no longer access this memory region. 


## -returns


None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.



## -remarks


The driver should not encounter any error, except for <b>D3DDDIERR_DEVICEREMOVED</b>. Therefore, if the driver passes any error, except for <b>D3DDDIERR_DEVICEREMOVED</b>, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Microsoft Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return <b>D3DDDIERR_DEVICEREMOVED</b>; however, if device removal interfered with the operation of <i>DestroyShader</i> (which typically should not happen), the driver can return <b>D3DDDIERR_DEVICEREMOVED</b>.



## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_DESTROYSHADER callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

