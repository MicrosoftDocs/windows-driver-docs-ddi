---
UID: NS:d3dumddi._DXVAHDDDI_RATIONAL
title: "_DXVAHDDDI_RATIONAL"
author: windows-driver-content
description: The DXVAHDDDI_RATIONAL structure describes a fractional value that represents the vertical and horizontal frequencies of a video mode (that is, vertical sync and horizontal sync).
old-location: display\dxvahdddi_rational.htm
old-project: display
ms.assetid: 4560fb48-24c3-4beb-acc3-b8d2ed3a81d3
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.dxvahdddi_rational, DXVAHDDDI_RATIONAL structure [Display Devices], _DXVAHDDDI_RATIONAL, d3dumddi/DXVAHDDDI_RATIONAL, DXVA2_Structs_9e1313ee-e48b-4e3d-9f13-40af1babef82.xml, DXVAHDDDI_RATIONAL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_RATIONAL is supported beginning with the Windows 7 operating system.
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
-	DXVAHDDDI_RATIONAL
product: Windows
targetos: Windows
req.typenames: DXVAHDDDI_RATIONAL
---

# _DXVAHDDDI_RATIONAL structure


## -description


The DXVAHDDDI_RATIONAL structure describes a fractional value that represents the vertical and horizontal frequencies of a video mode (that is, vertical sync and horizontal sync). 


## -syntax


````
typedef struct _DXVAHDDDI_RATIONAL {
  UINT Numerator;
  UINT Denominator;
} DXVAHDDDI_RATIONAL;
````


## -struct-fields




### -field Numerator

[in] The numerator of the frequency fraction. 


### -field Denominator

[in] The denominator of the frequency fraction. 


## -remarks



An output rate of 0/0 is valid. The driver interprets 0/0 as 0/1. The driver interprets 0/any value as zero. 

The NTSC frame rate is 30000/1001, and the PAL frame rate is 25/1. 



