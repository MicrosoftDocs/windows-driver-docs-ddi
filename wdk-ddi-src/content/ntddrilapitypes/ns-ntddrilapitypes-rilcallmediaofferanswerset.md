---
UID: NS:ntddrilapitypes.RILCALLMEDIAOFFERANSWERSET
title: RILCALLMEDIAOFFERANSWERSET
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmediaofferanswerset.htm
old-project: netvista
ms.assetid: 5d2f913e-10a3-4e96-a12f-5c4ea1dc061f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILCALLMEDIAOFFERANSWERSET, *LPRILCALLMEDIAOFFERANSWERSET, RILCALLMEDIAOFFERANSWERSET
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
req.alt-api: RILCALLMEDIAOFFERANSWERSET
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
req.typenames: *LPRILCALLMEDIAOFFERANSWERSET, RILCALLMEDIAOFFERANSWERSET
---

# RILCALLMEDIAOFFERANSWERSET structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILCALLMEDIAOFFERANSWERSET {
  DWORD                        cbSize;
  RILCALLMEDIAOFFERANSWERTYPE  dwType;
  DWORD                        dwNumberOfItems;
  RILCALLMEDIAOFFERANSWER [4]  stOfferAnswer;
} RILCALLMEDIAOFFERANSWERSET, RILCALLMEDIAOFFERANSWERSET;
````


## -struct-fields

### -field cbSize


### -field dwType


### -field dwNumberOfItems


### -field stOfferAnswer


## -remarks
