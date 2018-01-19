---
UID: NS:ntddrilapitypes.RILCALLLIST_V3
title: RILCALLLIST_V3
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcalllist_v3.htm
old-project: netvista
ms.assetid: d602f68a-8fe9-45f4-a54a-abc652578e9c
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILCALLLIST_V3, RILCALLLIST, *LPRILCALLLIST_V3, RILCALLLIST_V3, *LPRILCALLLIST
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
req.alt-api: RILCALLLIST_V3
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
req.typenames: RILCALLLIST, *LPRILCALLLIST_V3, RILCALLLIST_V3, *LPRILCALLLIST
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
