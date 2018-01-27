---
UID: NC:d3dumddi.PFND3DDDI_COLORFILL
title: PFND3DDDI_COLORFILL
author: windows-driver-content
description: The ColorFill function fills a rectangle on the surface with a particular color.
old-location: display\colorfill.htm
old-project: display
ms.assetid: c120421d-6a10-4d37-b936-98dac75e236b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.colorfill, ColorFill callback function [Display Devices], ColorFill, PFND3DDDI_COLORFILL, PFND3DDDI_COLORFILL, d3dumddi/ColorFill, UserModeDisplayDriver_Functions_ce1cba12-de0d-426d-981f-b95d58caa33d.xml
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
-	ColorFill
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_COLORFILL callback


## -description


The <b>ColorFill</b> function fills a rectangle on the surface with a particular color.


## -prototype


````
PFND3DDDI_COLORFILL ColorFill;

__checkReturn HRESULT APIENTRY ColorFill(
  _In_       HANDLE              hDevice,
  _In_ const D3DDDIARG_COLORFILL *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *






#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_colorfill.md">D3DDDIARG_COLORFILL</a> structure that describes the parameters of the color-fill operation.


## -returns


<b>ColorFill</b> returns S_OK or an appropriate error result if the color-fill operation is not successfully performed.



## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_colorfill.md">D3DDDIARG_COLORFILL</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_COLORFILL callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

