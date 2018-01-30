---
UID: NS:d3dumddi.D3DDDIARG_PRESENTSURFACE
title: D3DDDIARG_PRESENTSURFACE
author: windows-driver-content
description: Describes a surface to display.
old-location: display\d3dddiarg_presentsurface.htm
old-project: display
ms.assetid: 2104BF68-DF35-44DE-AD83-3026FF9314B4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDIARG_PRESENTSURFACE, display.d3dddiarg_presentsurface, d3dumddi/D3DDDIARG_PRESENTSURFACE, D3DDDIARG_PRESENTSURFACE structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDIARG_PRESENTSURFACE
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_PRESENTSURFACE
---

# D3DDDIARG_PRESENTSURFACE structure


## -description


Describes a surface to display.


## -syntax


````
typedef struct D3DDDIARG_PRESENTSURFACE {
  HANDLE hResource;
  UINT   SubResourceIndex;
} D3DDDIARG_PRESENTSURFACE;
````


## -struct-fields




### -field hResource

[in] A handle to the resource that contains the surface. <b>hResource</b> can be <b>NULL</b> if the user-mode display driver should perform a color-fill operation to the screen.


### -field SubResourceIndex

[in] The zero-based index into the resource, which is specified by the handle in the <b>hResource</b> member. This index indicates the subresource or surface to display.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_present.md">Present</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_PRESENTSURFACE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

