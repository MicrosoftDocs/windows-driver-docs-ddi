---
UID: NC:d3dumddi.PFND3DDDI_DESTROYLIGHT
title: PFND3DDDI_DESTROYLIGHT
author: windows-driver-content
description: The DestroyLight function deactivates a light source.
old-location: display\destroylight.htm
old-project: display
ms.assetid: dbc86e4d-a002-4270-a3c4-02d16972c921
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DestroyLight, DestroyLight callback function [Display Devices], PFND3DDDI_DESTROYLIGHT, UserModeDisplayDriver_Functions_fce83d93-bfe6-44f9-a1c4-ea92921bfb69.xml, d3dumddi/DestroyLight, display.destroylight
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	DestroyLight
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_DESTROYLIGHT callback


## -description


The <b>DestroyLight</b> function deactivates a light source.


## -prototype


````
PFND3DDDI_DESTROYLIGHT DestroyLight;

__checkReturn HRESULT APIENTRY DestroyLight(
  _In_       HANDLE                 hDevice,
  _In_ const D3DDDIARG_DESTROYLIGHT *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_destroylight.md">D3DDDIARG_DESTROYLIGHT</a> structure that describes how to set the light source.


## -returns



<b>DestroyLight</b> returns S_OK or an appropriate error result if the light source is not successfully deactivated.




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_destroylight.md">D3DDDIARG_DESTROYLIGHT</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DESTROYLIGHT callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

