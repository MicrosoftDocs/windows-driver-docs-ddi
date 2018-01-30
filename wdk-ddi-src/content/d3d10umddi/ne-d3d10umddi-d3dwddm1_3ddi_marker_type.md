---
UID: NE:d3d10umddi.D3DWDDM1_3DDI_MARKER_TYPE
title: D3DWDDM1_3DDI_MARKER_TYPE
author: windows-driver-content
description: Indicates the type of marker that the user-mode display driver supports.
old-location: display\d3dwddm1_3ddi_marker_type.htm
old-project: display
ms.assetid: E57CA17F-FB96-4E9B-A38D-67A4F925D3B4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3d10umddi/D3DWDDM1_3DDI_MARKER_TYPE_NONE, D3DWDDM1_3DDI_MARKER_TYPE_NONE, d3d10umddi/D3DWDDM1_3DDI_MARKER_TYPE, D3DWDDM1_3DDI_MARKER_TYPE enumeration [Display Devices], display.d3dwddm1_3ddi_marker_type, D3DWDDM1_3DDI_MARKER_TYPE_PROFILE, d3d10umddi/D3DWDDM1_3DDI_MARKER_TYPE_PROFILE, D3DWDDM1_3DDI_MARKER_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
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
-	D3d10umddi.h
apiname:
-	D3DWDDM1_3DDI_MARKER_TYPE
product: Windows
targetos: Windows
req.typenames: D3DWDDM1_3DDI_MARKER_TYPE
---

# D3DWDDM1_3DDI_MARKER_TYPE enumeration


## -description


Indicates the type of marker that the user-mode display driver supports.


## -syntax


````
typedef enum D3DWDDM1_3DDI_MARKER_TYPE { 
  D3DWDDM1_3DDI_MARKER_TYPE_NONE,
  D3DWDDM1_3DDI_MARKER_TYPE_PROFILE
} D3DWDDM1_3DDI_MARKER_TYPE;
````


## -enum-fields




### -field D3DWDDM1_3DDI_MARKER_TYPE_NONE

No marker type is supported.


### -field D3DWDDM1_3DDI_MARKER_TYPE_PROFILE

The context submits GPU work for single-threaded user-mode DDIs. In this case, each time stamp denotes the end of GPU work.

