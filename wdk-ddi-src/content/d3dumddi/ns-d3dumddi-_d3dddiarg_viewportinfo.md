---
UID: NS:d3dumddi._D3DDDIARG_VIEWPORTINFO
title: "_D3DDDIARG_VIEWPORTINFO"
author: windows-driver-content
description: The D3DDDIARG_VIEWPORTINFO structure describes the location and size of a view-clipping rectangle.
old-location: display\d3dddiarg_viewportinfo.htm
old-project: display
ms.assetid: 37e69980-fb3a-4abe-a76b-b2bd6827ae64
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DDDIARG_VIEWPORTINFO, D3DDDIARG_VIEWPORTINFO structure [Display Devices], UMDisplayDriver_param_Structs_ece888d8-61e4-4e7f-b052-c6e0169a6a97.xml, _D3DDDIARG_VIEWPORTINFO, d3dumddi/D3DDDIARG_VIEWPORTINFO, display.d3dddiarg_viewportinfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
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
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDIARG_VIEWPORTINFO
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_VIEWPORTINFO
---

# _D3DDDIARG_VIEWPORTINFO structure


## -description


The D3DDDIARG_VIEWPORTINFO structure describes the location and size of a view-clipping rectangle. 


## -syntax


````
typedef struct _D3DDDIARG_VIEWPORTINFO {
  UINT X;
  UINT Y;
  UINT Width;
  UINT Height;
} D3DDDIARG_VIEWPORTINFO;
````


## -struct-fields




### -field X

[in] The x coordinate, in screen coordinates, for the upper-left corner of the view-clipping rectangle.


### -field Y

[in] The y coordinate, in screen coordinates, for the upper-left corner of the view-clipping rectangle.


### -field Width

[in] The width, in screen coordinates, of the view-clipping rectangle where the application is rendering.


### -field Height

[in] The height, in screen coordinates, of the view-clipping rectangle where the application is rendering.


## -remarks



The user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setviewport.md">SetViewport</a> function should update the viewport portion of its internal rendering context with the location and size values that are specified in the D3DDDIARG_VIEWPORTINFO structure. The driver can use this information to perform guard band clipping.




## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setviewport.md">SetViewport</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_VIEWPORTINFO structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

