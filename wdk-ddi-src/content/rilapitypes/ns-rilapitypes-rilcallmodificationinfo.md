---
UID: NS:rilapitypes.RILCALLMODIFICATIONINFO
title: RILCALLMODIFICATIONINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmodificationinfo_2.htm
old-project: netvista
ms.assetid: 2e17e480-325a-4a7c-84b8-07775ddd52bc
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *LPRILCALLMODIFICATIONINFO, ,, A, C, D, F, I, L, M, N, O, P, R, RILCALLMODIFICATIONINFO, RILCALLMODIFICATIONINFO structure [Network Drivers Starting with Windows Vista], T, netvista.rilcallmodificationinfo_2, rilapitypes/RILCALLMODIFICATIONINFO"
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
-	RILCALLMODIFICATIONINFO
product: Windows
targetos: Windows
req.typenames: RILCALLMODIFICATIONINFO, *LPRILCALLMODIFICATIONINFO
req.product: Windows 10 or later.
---

# RILCALLMODIFICATIONINFO structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILCALLMODIFICATIONINFO {
  DWORD                                    cbSize;
  DWORD                                    dwParams;
  DWORD                                    dwExecutor;
  DWORD                                    dwID;
  RILCALLMODIFICATIONINFOMODIFICATIONTYPE  dwModificationType;
  RILCALLTYPE                              dwOldCallType;
  RILCALLTYPE                              dwNewCallType;
  RILADDRESS                               raAddress;
  RILALPHAIDENTIFIER                       aiIdentifier;
} RILCALLMODIFICATIONINFO, RILCALLMODIFICATIONINFO;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwExecutor


### -field dwID


### -field dwModificationType


### -field dwOldCallType


### -field dwNewCallType


### -field raAddress


### -field aiIdentifier

