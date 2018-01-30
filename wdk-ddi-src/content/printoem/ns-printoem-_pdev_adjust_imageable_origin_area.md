---
UID: NS:printoem._PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA
title: "_PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA"
author: windows-driver-content
description: The PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA structure specifies the imageable origin area.
old-location: print\pdev_adjust_imageable_origin_area.htm
old-project: print
ms.assetid: 7b66ed24-64c2-49bc-a417-05fe11178b9f
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: print.pdev_adjust_imageable_origin_area, printoem/PPDEV_ADJUST_IMAGEABLE_ORIGIN_AREA, print_unidrv-pscript_rendering_64db57fb-903d-411f-8106-b4c9a4c2a04e.xml, *PPDEV_ADJUST_IMAGEABLE_ORIGIN_AREA, printoem/PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA, _PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA, PPDEV_ADJUST_IMAGEABLE_ORIGIN_AREA structure pointer [Print Devices], PPDEV_ADJUST_IMAGEABLE_ORIGIN_AREA, PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA, PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA structure [Print Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: printoem.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
-	printoem.h
apiname:
-	PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA
product: Windows
targetos: Windows
req.typenames: "*PPDEV_ADJUST_IMAGEABLE_ORIGIN_AREA, PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA"
req.product: Windows 10 or later.
---

# _PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA structure


## -description


The PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA structure specifies the imageable origin area.


## -syntax


````
typedef struct _PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA {
  POINT ptImageOrigin;
  SIZEL szlImageableArea;
} PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA, *PPDEV_ADJUST_IMAGEABLE_ORIGIN_AREA;
````


## -struct-fields




### -field ptImageOrigin

A POINT structure that specifies the origin of the imageable area, in graphics device units (pixels).


### -field szlImageableArea

A SIZEL structure that specifies the size of the image area, in graphics device units (pixels).


## -remarks


The PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA structure is available in Windows Vista and later operating systems. 


