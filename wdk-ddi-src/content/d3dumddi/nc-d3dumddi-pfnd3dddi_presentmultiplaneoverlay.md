---
UID: NC:d3dumddi.PFND3DDDI_PRESENTMULTIPLANEOVERLAY
title: PFND3DDDI_PRESENTMULTIPLANEOVERLAY
author: windows-driver-content
description: Called by the Microsoft Direct3D runtime to notify the user-mode display driver that an application finished rendering and requests that the driver display the source surface by either copying or flipping or that the driver perform a color-fill operation. Must be implemented by Windows Display Driver Model (WDDM) 1.3 or later drivers that support multiplane overlays.
old-location: display\pfnpresentmultiplaneoverlay__d3d_.htm
old-project: display
ms.assetid: 3AC47977-A5F3-44A6-8F89-A1EA5E0BB6E4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfnpresentmultiplaneoverlay__d3d_, pfnPresentMultiPlaneOverlay callback function [Display Devices], pfnPresentMultiPlaneOverlay, PFND3DDDI_PRESENTMULTIPLANEOVERLAY, PFND3DDDI_PRESENTMULTIPLANEOVERLAY, d3dumddi/pfnPresentMultiPlaneOverlay
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	D3dumddi.h
apiname:
-	pfnPresentMultiPlaneOverlay
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_PRESENTMULTIPLANEOVERLAY callback


## -description


Called by the Microsoft Direct3D runtime to notify the user-mode display driver that an application finished rendering and requests that the driver display the source surface by either copying or flipping or that the driver perform a color-fill operation. Must be implemented by Windows Display Driver Model (WDDM) 1.3 or later drivers that support multiplane overlays.


## -prototype


````
PFND3DDDI_PRESENTMULTIPLANEOVERLAY pfnPresentMultiPlaneOverlay;

_Check_return_ HRESULT APIENTRY* pfnPresentMultiPlaneOverlay(
  _In_       HANDLE                             hDevice,
  _In_ const D3DDDIARG_PRESENTMULTIPLANEOVERLAY *pPresent
)
{ ... }
````


## -parameters




#### - hDevice [in]

A handle to the display device (graphics context).


### -param *






#### - pPresent [in]

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-d3dddiarg_presentmultiplaneoverlay.md">D3DDDIARG_PRESENTMULTIPLANEOVERLAY</a> structure that describes how to display to the destination surface. 


## -returns


If this routine succeeds, it returns <b>S_OK</b>. Otherwise, it returns an <b>HRESULT</b> error code.



## -remarks


When the user-mode display driver successfully completes its processing of a call to this function, it presents the source surface to the display by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/hh780323">pfnPresentMultiPlaneOverlayCb (D3D)</a> function.



## -see-also

<a href="..\d3dumddi\ns-d3dumddi-d3dddiarg_presentmultiplaneoverlay.md">D3DDDIARG_PRESENTMULTIPLANEOVERLAY</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh780323">pfnPresentMultiPlaneOverlayCb (D3D)</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_PRESENTMULTIPLANEOVERLAY (D3D) callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

