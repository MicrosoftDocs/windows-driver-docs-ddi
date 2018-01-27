---
UID: NS:dxgiddi.DXGI_DDI_ARG_PRESENTSURFACE
title: DXGI_DDI_ARG_PRESENTSURFACE
author: windows-driver-content
description: Describes a surface to display.
old-location: display\dxgi_ddi_arg_presentsurface.htm
old-project: display
ms.assetid: 1A1E2644-7411-4D69-8D45-B19D707221AB
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgi_ddi_arg_presentsurface, DXGI_DDI_ARG_PRESENTSURFACE structure [Display Devices], dxgiddi/DXGI_DDI_ARG_PRESENTSURFACE, DXGI_DDI_ARG_PRESENTSURFACE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxgiddi.h
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
-	Dxgiddi.h
apiname: 
-	DXGI_DDI_ARG_PRESENTSURFACE
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_ARG_PRESENTSURFACE
---

# DXGI_DDI_ARG_PRESENTSURFACE structure


## -description


Describes a surface to display.


## -syntax


````
typedef struct DXGI_DDI_ARG_PRESENTSURFACE {
  DXGI_DDI_HRESOURCE hSurface;
  UINT               SubResourceIndex;
} DXGI_DDI_ARG_PRESENTSURFACE;
````


## -struct-fields




### -field hSurface

[in] A handle to the resource that contains the surface. 


### -field SubResourceIndex

The zero-based index into the resource, which the handle in the <b>hSurface</b> member specifies. The <b>SubResourceIndex</b> index indicates the surface.

