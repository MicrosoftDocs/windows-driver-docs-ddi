---
UID: NS:rilapitypes.RILSENDUICCTOOLKITENVELOPEPARAMS
title: RILSENDUICCTOOLKITENVELOPEPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsenduicctoolkitenvelopeparams_2.htm
old-project: netvista
ms.assetid: 17bf24fe-bee5-4e08-8e3f-b9d4a03e147e
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILSENDUICCTOOLKITENVELOPEPARAMS, *LPRILSENDUICCTOOLKITENVELOPEPARAMS, RILSENDUICCTOOLKITENVELOPEPARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILSENDUICCTOOLKITENVELOPEPARAMS
req.alt-loc: rilapitypes.h
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
req.typenames: *LPRILSENDUICCTOOLKITENVELOPEPARAMS, RILSENDUICCTOOLKITENVELOPEPARAMS
req.product: Windows 10 or later.
---

# RILSENDUICCTOOLKITENVELOPEPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILSENDUICCTOOLKITENVELOPEPARAMS {
  DWORD    dwSlotIndex;
  DWORD    dwEnvelopeSize;
  BYTE [1] bEnvelope;
} RILSENDUICCTOOLKITENVELOPEPARAMS, RILSENDUICCTOOLKITENVELOPEPARAMS;
````


## -struct-fields

### -field dwSlotIndex


### -field dwEnvelopeSize


### -field bEnvelope


## -remarks
