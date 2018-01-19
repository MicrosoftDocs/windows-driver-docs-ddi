---
UID: NE:ksproxy.FRAMING_CACHE_OPS
title: FRAMING_CACHE_OPS
author: windows-driver-content
description: .
old-location: stream\framing_cache_ops.htm
old-project: stream
ms.assetid: EA496897-7D5A-43A8-A61E-34E986288E8B
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FRAMING_CACHE_OPS, FRAMING_CACHE_OPS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ksproxy.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FRAMING_CACHE_OPS
req.alt-loc: Ksproxy.h
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
req.typenames: FRAMING_CACHE_OPS
---

# FRAMING_CACHE_OPS enumeration



## -description




## -syntax

````
typedef enum  { 
  Framing_Cache_Update,
  Framing_Cache_ReadLast,
  Framing_Cache_ReadOrig,
  Framing_Cache_Write
} FRAMING_CACHE_OPS;
````


## -enum-fields

### -field Framing_Cache_Update

Specifies a request to bypass the cache when reading or writing.


### -field Framing_Cache_ReadLast


### -field Framing_Cache_ReadOrig


### -field Framing_Cache_Write


## -remarks
