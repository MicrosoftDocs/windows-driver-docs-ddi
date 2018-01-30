---
UID: NC:d3dumddi.PFND3DDDI_SETVIEWPORT
title: PFND3DDDI_SETVIEWPORT
author: windows-driver-content
description: The SetViewport function informs guard-band-aware drivers of the view-clipping rectangle.
old-location: display\setviewport.htm
old-project: display
ms.assetid: ef0847a3-d4f5-4a9e-a041-1b8f8523fdf7
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.setviewport, SetViewport callback function [Display Devices], SetViewport, PFND3DDDI_SETVIEWPORT, PFND3DDDI_SETVIEWPORT, d3dumddi/SetViewport, UserModeDisplayDriver_Functions_6b0d00a2-6316-4ac0-878c-e8554e92ef57.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
apiname:
-	SetViewport
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_SETVIEWPORT callback


## -description


The <i>SetViewport</i> function informs guard-band-aware drivers of the view-clipping rectangle.


## -prototype


````
PFND3DDDI_SETVIEWPORT SetViewport;

__checkReturn HRESULT APIENTRY SetViewport(
  _In_       HANDLE                 hDevice,
  _In_ const D3DDDIARG_VIEWPORTINFO *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *






#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_viewportinfo.md">D3DDDIARG_VIEWPORTINFO</a> structure that describes the view-clipping rectangle.


## -returns


<i>SetViewport</i> returns S_OK or an appropriate error result if the driver is not successfully informed about the view-clipping rectangle.



## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_viewportinfo.md">D3DDDIARG_VIEWPORTINFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETVIEWPORT callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

