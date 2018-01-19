---
UID: NS:rilapitypes.RILCALLLIST_V3
title: RILCALLLIST_V3
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcalllist_v3_2.htm
old-project: netvista
ms.assetid: 6ddeb8ab-076e-44a2-9705-8d5d527a9fd7
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILCALLLIST_V3, RILCALLLIST, RILCALLLIST_V3, *LPRILCALLLIST_V3, *LPRILCALLLIST
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
req.alt-api: RILCALLLIST_V3
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
req.typenames: RILCALLLIST, RILCALLLIST_V3, *LPRILCALLLIST_V3, *LPRILCALLLIST
req.product: Windows 10 or later.
---

# RILCALLLIST_V3 structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILCALLLIST_V3 {
  DWORD              dwNumberOfCalls;
  RILCALLINFO_V3 [1] rciCallInfo;
} RILCALLLIST_V3, RILCALLLIST_V3;
````


## -struct-fields

### -field dwNumberOfCalls


### -field rciCallInfo


## -remarks
