---
UID: NS:strmini.KSSCATTER_GATHER
title: KSSCATTER_GATHER
author: windows-driver-content
description: "."
old-location: stream\ksscatter_gather.htm
old-project: stream
ms.assetid: 10AFDC4B-75E5-4E88-A614-60043848C570
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSSCATTER_GATHER structure [Streaming Media Devices], PKSSCATTER_GATHER, KSSCATTER_GATHER, *PKSSCATTER_GATHER, strmini/KSSCATTER_GATHER, strmini/PKSSCATTER_GATHER, PKSSCATTER_GATHER structure pointer [Streaming Media Devices], stream.ksscatter_gather
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Strmini.h
apiname:
-	KSSCATTER_GATHER
product: Windows
targetos: Windows
req.typenames: "*PKSSCATTER_GATHER, KSSCATTER_GATHER"
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


