---
UID: NS:printoem._PDEV_ADJUST_GRAPHICS_RESOLUTION
title: _PDEV_ADJUST_GRAPHICS_RESOLUTION
author: windows-driver-content
description: The PDEV_ADJUST_GRAPHICS_RESOLUTION structure specifies a graphics resolution value.
old-location: print\pdev_adjust_graphics_resolution.htm
old-project: print
ms.assetid: d6cebb0d-87ca-4e40-8a87-9579a1026567
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: print_unidrv-pscript_rendering_4e6d42c6-744c-4451-85a3-f5769c0ebfd3.xml, PDEV_ADJUST_GRAPHICS_RESOLUTION, printoem/PPDEV_ADJUST_GRAPHICS_RESOLUTION, PPDEV_ADJUST_GRAPHICS_RESOLUTION structure pointer [Print Devices], PDEV_ADJUST_GRAPHICS_RESOLUTION structure [Print Devices], _PDEV_ADJUST_GRAPHICS_RESOLUTION, *PPDEV_ADJUST_GRAPHICS_RESOLUTION, PPDEV_ADJUST_GRAPHICS_RESOLUTION, printoem/PDEV_ADJUST_GRAPHICS_RESOLUTION, print.pdev_adjust_graphics_resolution
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
-	PDEV_ADJUST_GRAPHICS_RESOLUTION
product: Windows
targetos: Windows
req.typenames: PDEV_ADJUST_GRAPHICS_RESOLUTION, *PPDEV_ADJUST_GRAPHICS_RESOLUTION
req.product: Windows 10 or later.
---

# _PDEV_ADJUST_GRAPHICS_RESOLUTION structure


## -description


The PDEV_ADJUST_GRAPHICS_RESOLUTION structure specifies a graphics resolution value.


## -syntax


````
typedef struct _PDEV_ADJUST_GRAPHICS_RESOLUTION {
  POINT ptGraphicsResolution;
} PDEV_ADJUST_GRAPHICS_RESOLUTION, *PPDEV_ADJUST_GRAPHICS_RESOLUTION;
````


## -struct-fields




### -field ptGraphicsResolution

A POINT structure that specifies the resolution of the graphics area, in dots per inch (DPI).


## -remarks


The PDEV_ADJUST_GRAPHICS_RESOLUTION structure is available in Windows Vista and later operating systems. 


