---
UID: NS:d3dumddi.D3DDDIARG_PRESENTSURFACE
title: D3DDDIARG_PRESENTSURFACE
author: windows-driver-content
description: Describes a surface to display.
old-location: display\d3dddiarg_presentsurface.htm
old-project: display
ms.assetid: 2104BF68-DF35-44DE-AD83-3026FF9314B4
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DDDIARG_PRESENTSURFACE, D3DDDIARG_PRESENTSURFACE structure [Display Devices], d3dumddi/D3DDDIARG_PRESENTSURFACE, display.d3dddiarg_presentsurface
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDIARG_PRESENTSURFACE
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_PRESENTSURFACE
---

# D3DDDIARG_PRESENTSURFACE structure


## -description


Describes a surface to display.


## -struct-fields




### -field hResource

[in] A handle to the resource that contains the surface. <b>hResource</b> can be <b>NULL</b> if the user-mode display driver should perform a color-fill operation to the screen.


### -field SubResourceIndex

[in] The zero-based index into the resource, which is specified by the handle in the <b>hResource</b> member. This index indicates the subresource or surface to display.


## -see-also




<a href="https://msdn.microsoft.com/e90683b4-64b6-4018-96a5-b50118df3367">Present</a>
 

 

