---
UID: NS:strmini.KSSCATTER_GATHER
title: KSSCATTER_GATHER
author: windows-driver-content
description: "."
old-location: stream\ksscatter_gather.htm
old-project: stream
ms.assetid: 10AFDC4B-75E5-4E88-A614-60043848C570
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSSCATTER_GATHER, KSSCATTER_GATHER, KSSCATTER_GATHER structure [Streaming Media Devices], PKSSCATTER_GATHER, PKSSCATTER_GATHER structure pointer [Streaming Media Devices], stream.ksscatter_gather, strmini/KSSCATTER_GATHER, strmini/PKSSCATTER_GATHER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: strmini.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Strmini.h
api_name:
-	KSSCATTER_GATHER
product: Windows
targetos: Windows
req.typenames: KSSCATTER_GATHER, *PKSSCATTER_GATHER
req.product: Windows 10 or later.
---

# KSSCATTER_GATHER structure


## -description





## -syntax


````
typedef struct {
  PHYSICAL_ADDRESS PhysicalAddress;
  ULONG            Length;
} KSSCATTER_GATHER, *PKSSCATTER_GATHER;
````


## -struct-fields




### -field PhysicalAddress


### -field Length

