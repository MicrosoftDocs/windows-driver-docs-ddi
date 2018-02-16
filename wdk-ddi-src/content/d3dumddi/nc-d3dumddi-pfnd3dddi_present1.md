---
UID: NC:d3dumddi.PFND3DDDI_PRESENT1
title: PFND3DDDI_PRESENT1
author: windows-driver-content
description: Notifies the user-mode display driver that an application finished rendering and that all ownership of the shared resource is released, and requests that the driver display to the destination surface.
old-location: display\pfnpresent1_d3d_.htm
old-project: display
ms.assetid: 8BB8E85F-B081-422E-ACE1-C2312BA28B9F
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfnpresent1_d3d_, pfnPresent1 callback function [Display Devices], pfnPresent1, PFND3DDDI_PRESENT1, PFND3DDDI_PRESENT1, d3dumddi/pfnPresent1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
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
-	pfnPresent1
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_PRESENT1 callback


## -description


Notifies the user-mode display driver that an application finished rendering and that all ownership of the shared resource is released, and requests that the driver display to the destination surface.


## -prototype


````
PFND3DDDI_PRESENT1 pfnPresent1;

__checkReturn HRESULT* pfnPresent1(
  _In_       HANDLE             *hDevice,
  _In_ const D3DDDIARG_PRESENT1 *pPresentData
)
{ ... }
````


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








#### - pPresentData [in]

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_present1.md">D3DDDIARG_PRESENT1</a> structure that describes how to display to the destination surface. 


## -returns




      Returns <b>S_OK</b> or an appropriate error result if the function does not complete successfully.




## -remarks



The user-mode display driver must submit all partially built render data (command buffers) by calling the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rendercb.md">pfnRenderCb</a>  function. The driver must make only  a single call to <b>pfnRenderCb</b>.




## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rendercb.md">pfnRenderCb</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_present1.md">D3DDDIARG_PRESENT1</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_PRESENT1 callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

