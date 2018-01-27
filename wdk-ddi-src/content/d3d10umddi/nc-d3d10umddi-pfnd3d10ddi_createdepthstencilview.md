---
UID: NC:d3d10umddi.PFND3D10DDI_CREATEDEPTHSTENCILVIEW
title: PFND3D10DDI_CREATEDEPTHSTENCILVIEW
author: windows-driver-content
description: The CreateDepthStencilView function creates a depth stencil view.
old-location: display\createdepthstencilview.htm
old-project: display
ms.assetid: 1a1c28f0-8343-4255-8055-d31eb643b7d5
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.createdepthstencilview, CreateDepthStencilView callback function [Display Devices], CreateDepthStencilView, PFND3D10DDI_CREATEDEPTHSTENCILVIEW, PFND3D10DDI_CREATEDEPTHSTENCILVIEW, d3d10umddi/CreateDepthStencilView, UserModeDisplayDriverDx10_Functions_299a6bcd-ba94-4568-a4fc-d89c84742c45.xml
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
-	CreateDepthStencilView
product: Windows
targetos: Windows
req.typenames: *PSETRESULT_INFO, SETRESULT_INFO
---

# PFND3D10DDI_CREATEDEPTHSTENCILVIEW callback


## -description


The <b>CreateDepthStencilView</b> function creates a depth stencil view.


## -prototype


````
PFND3D10DDI_CREATEDEPTHSTENCILVIEW CreateDepthStencilView;

VOID APIENTRY CreateDepthStencilView(
  _In_       D3D10DDI_HDEVICE                   hDevice,
  _In_ const D3D10DDIARG_CREATEDEPTHSTENCILVIEW *pCreateDepthStencilView,
  _In_       D3D10DDI_HDEPTHSTENCILVIEW         hDepthStencilView,
  _In_       D3D10DDI_HRTDEPTHSTENCILVIEW       hRTDepthStencilView
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE



### -param *



### -param D3D10DDI_HDEPTHSTENCILVIEW



### -param D3D10DDI_HRTDEPTHSTENCILVIEW






#### - hRTDepthStencilView [in]

 A handle to the depth stencil view that the driver should use anytime it calls back into the Direct3D runtime. 


#### - pCreateDepthStencilView [in]

 A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdepthstencilview.md">D3D10DDIARG_CREATEDEPTHSTENCILVIEW</a> structure that describes the parameters that the user-mode display driver uses to create a depth stencil view. 


#### - hDepthStencilView [in]

 A handle to the driver's private data for the depth stencil view. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivatedepthstencilviewsize.md">CalcPrivateDepthStencilViewSize</a> function. The handle is really just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its depth stencil view object.


#### - hDevice [in]

 A handle to the display device (graphics context).


## -returns


None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.



## -remarks


The driver might run out of memory. Therefore, the driver can pass E_OUTOFMEMORY or D3DDDIERR_DEVICEREMOVED in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroydepthstencilview.md">DestroyDepthStencilView</a> function to destroy the handle that the <i>hDepthStencilView</i> parameter specifies.



## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroydepthstencilview.md">DestroyDepthStencilView</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdepthstencilview.md">D3D10DDIARG_CREATEDEPTHSTENCILVIEW</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivatedepthstencilviewsize.md">CalcPrivateDepthStencilViewSize</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_CREATEDEPTHSTENCILVIEW callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

