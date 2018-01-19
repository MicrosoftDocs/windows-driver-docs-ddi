---
UID: NS:rilapitypes.RILCALLMEDIAID
title: RILCALLMEDIAID
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmediaid_2.htm
old-project: netvista
ms.assetid: ad367969-217c-4b9a-b9b1-1b6d1bf04f2e
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILCALLMEDIAID, *LPRILCALLMEDIAID, RILCALLMEDIAID
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
req.alt-api: RILCALLMEDIAID
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
req.typenames: *LPRILCALLMEDIAID, RILCALLMEDIAID
req.product: Windows 10 or later.
---

# RILCALLMEDIAID structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILCALLMEDIAID {
  RILCALLMEDIATYPE  dwType;
  DWORD             dwID;
} RILCALLMEDIAID, RILCALLMEDIAID;
````


## -struct-fields

### -field dwType


### -field dwID


## -remarks
