---
UID: NE:ks.KSCOMPLETION_INVOCATION
title: KSCOMPLETION_INVOCATION
author: windows-driver-content
description: .
old-location: stream\kscompletion_invocation.htm
old-project: stream
ms.assetid: 2BD1A2F8-BAA2-40A3-9C97-667780A6F395
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSCOMPLETION_INVOCATION, KSCOMPLETION_INVOCATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ks.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSCOMPLETION_INVOCATION
req.alt-loc: Ks.h
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
req.typenames: KSCOMPLETION_INVOCATION
---

# KSCOMPLETION_INVOCATION enumeration



## -description




## -syntax

````
typedef enum  { 
  KsInvokeOnSuccess  = 1,
  KsInvokeOnError    = 2,
  KsInvokeOnCancel   = 4
} KSCOMPLETION_INVOCATION;
````


## -enum-fields

### -field KsInvokeOnSuccess

Invokes the completion routine on success.


### -field KsInvokeOnError

Invokes the completion routine on error.


### -field KsInvokeOnCancel

Invokes the completion routine on cancellation.


## -remarks
