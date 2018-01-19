---
UID: NS:bdatypes._BDA_WMDRMTUNER_PURCHASEENTITLEMENT
title: _BDA_WMDRMTUNER_PURCHASEENTITLEMENT
author: windows-driver-content
description: .
old-location: stream\bda_wmdrmtuner_purchaseentitlement.htm
old-project: stream
ms.assetid: 348E7C25-4998-490E-A732-5780B0A21DE0
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _BDA_WMDRMTUNER_PURCHASEENTITLEMENT, BDA_WMDRMTUNER_PURCHASEENTITLEMENT, *PBDA_WMDRMTUNER_PURCHASEENTITLEMENT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdatypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BDA_WMDRMTUNER_PURCHASEENTITLEMENT
req.alt-loc: Bdatypes.h
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
req.typenames: BDA_WMDRMTUNER_PURCHASEENTITLEMENT, *PBDA_WMDRMTUNER_PURCHASEENTITLEMENT
---

# _BDA_WMDRMTUNER_PURCHASEENTITLEMENT structure



## -description




## -syntax

````
typedef struct _BDA_WMDRMTUNER_PURCHASEENTITLEMENT {
  PBDARESULT lResult;
  ULONG      ulDescrambleStatus;
  ULONG      ulCaptureTokenLength;
  BYTE       argbCaptureTokenBuffer[MIN_DIMENSION];
} BDA_WMDRMTUNER_PURCHASEENTITLEMENT, *PBDA_WMDRMTUNER_PURCHASEENTITLEMENT;
````


## -struct-fields

### -field lResult


### -field ulDescrambleStatus


### -field ulCaptureTokenLength


### -field argbCaptureTokenBuffer


## -remarks
