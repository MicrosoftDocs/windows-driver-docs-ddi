---
UID: NS:rilapitypes.RILCALLMEDIAOFFERANSWERSET
title: RILCALLMEDIAOFFERANSWERSET
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmediaofferanswerset_2.htm
old-project: netvista
ms.assetid: 272e2bf5-9d84-407d-9126-41bcb4f43d91
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILCALLMEDIAOFFERANSWERSET, *LPRILCALLMEDIAOFFERANSWERSET, RILCALLMEDIAOFFERANSWERSET
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
req.alt-api: RILCALLMEDIAOFFERANSWERSET
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
req.typenames: *LPRILCALLMEDIAOFFERANSWERSET, RILCALLMEDIAOFFERANSWERSET
req.product: Windows 10 or later.
---

# RILCALLMEDIAOFFERANSWERSET structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILCALLMEDIAOFFERANSWERSET {
  DWORD                                       cbSize;
  RILCALLMEDIAOFFERANSWERTYPE                 dwType;
  DWORD                                       dwNumberOfItems;
  RILCALLMEDIAOFFERANSWER [MAXNUM_CALL_MEDIA] stOfferAnswer;
} RILCALLMEDIAOFFERANSWERSET, RILCALLMEDIAOFFERANSWERSET;
````


## -struct-fields

### -field cbSize


### -field dwType


### -field dwNumberOfItems


### -field stOfferAnswer


## -remarks
