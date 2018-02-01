---
UID: NC:d3dumddi.PFND3DDDI_SETLIGHT
title: PFND3DDDI_SETLIGHT
author: windows-driver-content
description: The SetLight function sets properties for a light source.
old-location: display\setlight.htm
old-project: display
ms.assetid: 28e3992e-a636-47e2-a5a6-5da06d276b5c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.setlight, SetLight callback function [Display Devices], SetLight, PFND3DDDI_SETLIGHT, PFND3DDDI_SETLIGHT, d3dumddi/SetLight, UserModeDisplayDriver_Functions_82c42629-2344-4778-aaf4-e41acac4cfce.xml
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
-	SetLight
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_SETLIGHT callback


## -description


The <i>SetLight</i> function sets properties for a light source.


## -prototype


````
PFND3DDDI_SETLIGHT SetLight;

__checkReturn HRESULT APIENTRY SetLight(
  _In_       HANDLE             hDevice,
  _In_ const D3DDDIARG_SETLIGHT *pData,
  _In_ const D3DDDI_LIGHT       *pLightProperties
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *






#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setlight.md">D3DDDIARG_SETLIGHT</a> structure that describes how to set the light source.


#### - pLightProperties [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddi_light.md">D3DDDI_LIGHT</a> structure that describes the light properties to set.


## -returns


<i>SetLight</i> returns S_OK or an appropriate error result if the light properties are not successfully set.



## -remarks


Light properties describe the type and color of a light source. Depending on the type of light that is being used, a light can have properties for attenuation and range or for spotlight effects. However, not all types of lights will use all of the properties. For more information about light properties, see the Microsoft Windows SDK documentation.



## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_light.md">D3DDDI_LIGHT</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setlight.md">D3DDDIARG_SETLIGHT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETLIGHT callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

