---
UID: NS:d3dkmddi._DXGK_QUERYPHYSICALADAPTERCAPSIN
title: "_DXGK_QUERYPHYSICALADAPTERCAPSIN"
author: windows-driver-content
description: The DXGK_QUERYPHYSICALADAPTERCAPSIN structure is used to query the display driver for the capabilities of the physical display adapter.
old-location: display\dxgk_queryphysicaladaptercapsin.htm
old-project: display
ms.assetid: 4B01E62F-5E5B-4316-B237-EADAA3C72242
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, A, C, D, DXGK_QUERYPHYSICALADAPTERCAPSIN, DXGK_QUERYPHYSICALADAPTERCAPSIN structure [Display Devices], E, G, H, I, K, L, N, P, Q, R, S, T, U, X, Y, _, _DXGK_QUERYPHYSICALADAPTERCAPSIN, d3dkmddi/DXGK_QUERYPHYSICALADAPTERCAPSIN, display.dxgk_queryphysicaladaptercapsin"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_QUERYPHYSICALADAPTERCAPSIN
product: Windows
targetos: Windows
req.typenames: DXGK_QUERYPHYSICALADAPTERCAPSIN
---

# _DXGK_QUERYPHYSICALADAPTERCAPSIN structure


## -description


The <b>DXGK_QUERYPHYSICALADAPTERCAPSIN</b> structure is used to query the display driver for the capabilities of the physical display adapter.


## -syntax


````
typedef struct _DXGK_QUERYPHYSICALADAPTERCAPSIN {
  UINT PhysicalAdapterIndex;
} DXGK_QUERYPHYSICALADAPTERCAPSIN;
````


## -struct-fields




### -field PhysicalAdapterIndex

Index of a physical adapter in a link.

