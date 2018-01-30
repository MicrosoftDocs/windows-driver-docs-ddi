---
UID: NC:d3d10umddi.PFND3D10DDI_CREATERENDERTARGETVIEW
title: PFND3D10DDI_CREATERENDERTARGETVIEW
author: windows-driver-content
description: The CreateRenderTargetView function creates a render target view.
old-location: display\createrendertargetview.htm
old-project: display
ms.assetid: bf9fc732-5f9a-4fee-8ea0-19b140789463
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.createrendertargetview, CreateRenderTargetView callback function [Display Devices], CreateRenderTargetView, PFND3D10DDI_CREATERENDERTARGETVIEW, PFND3D10DDI_CREATERENDERTARGETVIEW, d3d10umddi/CreateRenderTargetView, UserModeDisplayDriverDx10_Functions_abef4fc8-0aac-40a9-9f45-de2160c347af.xml
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
-	CreateRenderTargetView
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_CREATERENDERTARGETVIEW callback


## -description


The <b>CreateRenderTargetView</b> function creates a render target view.


## -prototype


````
PFND3D10DDI_CREATERENDERTARGETVIEW CreateRenderTargetView;

VOID APIENTRY CreateRenderTargetView(
  _In_       D3D10DDI_HDEVICE                   hDevice,
  _In_ const D3D10DDIARG_CREATERENDERTARGETVIEW *pCreateRenderTargetView,
  _In_       D3D10DDI_HRENDERTARGETVIEW         hRenderTargetView,
  _In_       D3D10DDI_HRTRENDERTARGETVIEW       hRTRenderTargetView
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE



### -param *



### -param D3D10DDI_HRENDERTARGETVIEW



### -param D3D10DDI_HRTRENDERTARGETVIEW






#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pCreateRenderTargetView [in]

 A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createrendertargetview.md">D3D10DDIARG_CREATERENDERTARGETVIEW</a> structure that describes the parameters that the user-mode display driver uses to create a render target view. 


#### - hRenderTargetView [in]

 A handle to the driver's private data for the render target view. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivaterendertargetviewsize.md">CalcPrivateRenderTargetViewSize</a> function. The handle is really just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its render target view object. 


#### - hRTRenderTargetView [in]

 A handle to the render target view that the driver should use anytime it calls back into the Direct3D runtime. 


## -returns


None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.



## -remarks


The driver might run out of memory. Therefore, the driver can pass E_OUTOFMEMORY or D3DDDIERR_DEVICEREMOVED in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyrendertargetview.md">DestroyRenderTargetView</a> function to destroy the handle that the <i>hRenderTargetView</i> parameter specifies.



## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createrendertargetview.md">D3D10DDIARG_CREATERENDERTARGETVIEW</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivaterendertargetviewsize.md">CalcPrivateRenderTargetViewSize</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyrendertargetview.md">DestroyRenderTargetView</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_CREATERENDERTARGETVIEW callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

