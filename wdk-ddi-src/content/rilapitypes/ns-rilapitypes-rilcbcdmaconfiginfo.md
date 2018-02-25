---
UID: NS:rilapitypes.RILCBCDMACONFIGINFO
title: RILCBCDMACONFIGINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcbcdmaconfiginfo_2.htm
old-project: netvista
ms.assetid: a12254b0-fb4d-49ff-a046-cae99c12f535
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *LPRILCBCDMACONFIGINFO, ,, A, B, C, D, F, G, I, L, M, N, O, P, R, RILCBCDMACONFIGINFO, RILCBCDMACONFIGINFO structure [Network Drivers Starting with Windows Vista], netvista.rilcbcdmaconfiginfo_2, rilapitypes/RILCBCDMACONFIGINFO"
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
-	RILCBCDMACONFIGINFO
product: Windows
targetos: Windows
req.typenames: RILCBCDMACONFIGINFO, *LPRILCBCDMACONFIGINFO
req.product: Windows 10 or later.
---

# RILCBCDMACONFIGINFO structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILCBCDMACONFIGINFO {
  BOOL   fAccept;
  DWORD  dwBroadcastMsgLang;
  DWORD  dwBroadcastServiceCategory;
} RILCBCDMACONFIGINFO, RILCBCDMACONFIGINFO;
````


## -struct-fields




### -field fAccept


### -field dwBroadcastMsgLang


### -field dwBroadcastServiceCategory

