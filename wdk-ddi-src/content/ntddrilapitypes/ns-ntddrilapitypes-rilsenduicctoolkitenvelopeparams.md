---
UID: NS:ntddrilapitypes.RILSENDUICCTOOLKITENVELOPEPARAMS
title: RILSENDUICCTOOLKITENVELOPEPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsenduicctoolkitenvelopeparams.htm
old-project: netvista
ms.assetid: df1ce4d6-e335-4ffa-8e37-85221eb57521
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILSENDUICCTOOLKITENVELOPEPARAMS, *LPRILSENDUICCTOOLKITENVELOPEPARAMS, RILSENDUICCTOOLKITENVELOPEPARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILSENDUICCTOOLKITENVELOPEPARAMS
req.alt-loc: ntddrilapitypes.h
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
