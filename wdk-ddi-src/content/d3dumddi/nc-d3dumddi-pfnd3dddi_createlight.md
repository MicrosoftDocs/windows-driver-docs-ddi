---
UID: NC:d3dumddi.PFND3DDDI_CREATELIGHT
title: PFND3DDDI_CREATELIGHT
author: windows-driver-content
description: The CreateLight function creates a light source.
old-location: display\createlight.htm
old-project: display
ms.assetid: 4649b1d1-6fd3-48fb-b25f-1228851bb682
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.createlight, CreateLight callback function [Display Devices], CreateLight, PFND3DDDI_CREATELIGHT, PFND3DDDI_CREATELIGHT, d3dumddi/CreateLight, UserModeDisplayDriver_Functions_c6b9e247-5a6b-4e90-bcbd-bc02708ca555.xml
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
-	CreateLight
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_CREATELIGHT callback


## -description


The <b>CreateLight</b> function creates a light source.


## -prototype


````
PFND3DDDI_CREATELIGHT CreateLight;

__checkReturn HRESULT APIENTRY CreateLight(
  _In_       HANDLE                hDevice,
  _In_ const D3DDDIARG_CREATELIGHT *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *






#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createlight.md">D3DDDIARG_CREATELIGHT</a> structure that contains the index into the light array.


## -returns


<b>CreateLight</b> should return S_OK or an appropriate error result if it cannot successfully create a light source.



## -remarks


The user-mode display driver should enlarge its light array as necessary to accommodate at least as many light sources as specified by the <b>Index</b> member in <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createlight.md">D3DDDIARG_CREATELIGHT</a>.



## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createlight.md">D3DDDIARG_CREATELIGHT</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_CREATELIGHT callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

