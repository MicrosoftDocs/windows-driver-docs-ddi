---
UID: NS:ks.KS_COMPRESSION
title: KS_COMPRESSION
author: windows-driver-content
description: The KS_COMPRESSION structure defines the compression of frames on an output pin.
old-location: stream\ks_compression.htm
old-project: stream
ms.assetid: 065f51c3-f476-4f04-880a-5c42e493d458
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KS_COMPRESSION, KS_COMPRESSION, *PKS_COMPRESSION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KS_COMPRESSION
req.alt-loc: ks.h
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
req.typenames: KS_COMPRESSION, *PKS_COMPRESSION
---

# KS_COMPRESSION structure



## -description
The KS_COMPRESSION structure defines the compression of frames on an output pin.



## -syntax

````
typedef struct {
  ULONG RatioNumerator;
  ULONG RatioDenominator;
  ULONG RatioConstantMargin;
} KS_COMPRESSION, *PKS_COMPRESSION;
````


## -struct-fields

### -field RatioNumerator

Specifies the numerator of the compression/expansion ratio.


### -field RatioDenominator

Specifies the denominator of the compression/expansion ratio.


### -field RatioConstantMargin

Specifies a scalar constant to apply to the compression ratio. Set this to zero for no compression.


## -remarks
For compression, specify a fraction less than 1. For decompression, specify a fraction greater than 1. For example, a compressor might specify 1:3. A decompressor could specify 3:1.</p>