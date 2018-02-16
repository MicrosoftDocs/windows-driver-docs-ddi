---
UID: NS:rilapitypes.RILCALLLIST_V3
title: RILCALLLIST_V3
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcalllist_v3_2.htm
old-project: netvista
ms.assetid: 6ddeb8ab-076e-44a2-9705-8d5d527a9fd7
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilcalllist_v3_2, rilapitypes/RILCALLLIST_V3, *LPRILCALLLIST_V3, RILCALLLIST_V3 structure [Network Drivers Starting with Windows Vista], *LPRILCALLLIST, RILCALLLIST_V3, RILCALLLIST
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILCALLLIST_V3
product: Windows
targetos: Windows
req.typenames: RILCALLLIST_V3, RILCALLLIST, *LPRILCALLLIST, *LPRILCALLLIST_V3
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

