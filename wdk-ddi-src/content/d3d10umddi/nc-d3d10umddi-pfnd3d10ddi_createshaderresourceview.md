---
UID: NC:d3d10umddi.PFND3D10DDI_CREATESHADERRESOURCEVIEW
title: PFND3D10DDI_CREATESHADERRESOURCEVIEW
author: windows-driver-content
description: The CreateShaderResourceView function creates a shader resource view.
old-location: display\createshaderresourceview.htm
old-project: display
ms.assetid: 3b1c998d-3fde-4712-ba74-7c8033033182
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.createshaderresourceview, CreateShaderResourceView callback function [Display Devices], CreateShaderResourceView, PFND3D10DDI_CREATESHADERRESOURCEVIEW, PFND3D10DDI_CREATESHADERRESOURCEVIEW, d3d10umddi/CreateShaderResourceView, UserModeDisplayDriverDx10_Functions_183935f7-c6ab-4ea9-9e33-a4586daf3097.xml
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
-	CreateShaderResourceView
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_CREATESHADERRESOURCEVIEW callback


## -description


The <b>CreateShaderResourceView</b> function creates a shader resource view.


## -prototype


````
PFND3D10DDI_CREATESHADERRESOURCEVIEW CreateShaderResourceView;

VOID APIENTRY CreateShaderResourceView(
  _In_       D3D10DDI_HDEVICE                     hDevice,
  _In_ const D3D10DDIARG_CREATESHADERRESOURCEVIEW *pCreateShaderResourceView,
  _In_       D3D10DDI_HSHADERRESOURCEVIEW         hShaderResourceView,
  _In_       D3D10DDI_HRTSHADERRESOURCEVIEW       hRTShaderResourceView
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE



### -param *



### -param D3D10DDI_HSHADERRESOURCEVIEW



### -param D3D10DDI_HRTSHADERRESOURCEVIEW






#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pCreateShaderResourceView [in]

 A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createshaderresourceview.md">D3D10DDIARG_CREATESHADERRESOURCEVIEW</a> structure that describes the parameters that the user-mode display driver uses to create a shader resource view. 


#### - hShaderResourceView [in]

 A handle to the driver's private data for the shader resource view. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivateshaderresourceviewsize.md">CalcPrivateShaderResourceViewSize</a> function. The handle is really just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its shader resource view object. 


#### - hRTShaderResourceView [in]

 A handle to the shader resource view that the driver should use anytime it calls back into the Direct3D runtime. 


## -returns


None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.



## -remarks


The driver might run out of memory. Therefore, the driver can pass E_OUTOFMEMORY or D3DDDIERR_DEVICEREMOVED in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyshaderresourceview.md">DestroyShaderResourceView</a> function to destroy the handle that the <i>hShaderResourceView</i> parameter specifies.



## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyshaderresourceview.md">DestroyShaderResourceView</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createshaderresourceview.md">D3D10DDIARG_CREATESHADERRESOURCEVIEW</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivateshaderresourceviewsize.md">CalcPrivateShaderResourceViewSize</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_CREATESHADERRESOURCEVIEW callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

