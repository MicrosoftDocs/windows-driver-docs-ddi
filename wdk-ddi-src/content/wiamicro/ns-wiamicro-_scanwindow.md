---
UID: NS:wiamicro._SCANWINDOW
title: _SCANWINDOW
author: windows-driver-content
description: The SCANWINDOW structure is used by the WIA Flatbed driver to tell the microdriver what image area to scan.
old-location: image\scanwindow.htm
old-project: image
ms.assetid: c4b507ac-af32-4949-add0-e19c00e328fe
ms.author: windowsdriverdev
ms.date: 1/17/2018
ms.keywords: _SCANWINDOW, *PSCANWINDOW, SCANWINDOW
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wiamicro.h
req.include-header: Wiamicro.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SCANWINDOW
req.alt-loc: wiamicro.h
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
req.typenames: *PSCANWINDOW, SCANWINDOW
req.product: Windows 10 or later.
---

# _SCANWINDOW structure



## -description
The SCANWINDOW structure is used by the WIA Flatbed driver to tell the microdriver what image area to scan.



## -syntax

````
typedef struct _SCANWINDOW {
  LONG xPos;
  LONG yPos;
  LONG xExtent;
  LONG yExtent;
} SCANWINDOW, *PSCANWINDOW;
````


## -struct-fields

### -field xPos

Specifies the horizontal position of the left edge of the scan window in pixels.


### -field yPos

Specifies the vertical position of the top edge of the scan window in pixels.


### -field xExtent

Specifies the width of the scan window in pixels.


### -field yExtent

Specifies the height of the scan window in pixels.


## -remarks
