---
UID: NS:ntddrilapitypes.RILUNSOLICITEDSSINFO_V2
title: RILUNSOLICITEDSSINFO_V2
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilunsolicitedssinfo_v2.htm
old-project: netvista
ms.assetid: f4b93f1e-8559-4145-a122-74d62b146afa
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *LPRILUNSOLICITEDSSINFO, *LPRILUNSOLICITEDSSINFO_V2, ,, 2, C, D, E, F, I, L, N, O, P, R, RILUNSOLICITEDSSINFO, RILUNSOLICITEDSSINFO_V2, RILUNSOLICITEDSSINFO_V2 structure [Network Drivers Starting with Windows Vista], S, T, U, V, _, netvista.rilunsolicitedssinfo_v2, ntddrilapitypes/RILUNSOLICITEDSSINFO_V2"
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
-	ntddrilapitypes.h
apiname:
-	RILUNSOLICITEDSSINFO_V2
product: Windows
targetos: Windows
req.typenames: RILUNSOLICITEDSSINFO_V2, *LPRILUNSOLICITEDSSINFO_V2, RILUNSOLICITEDSSINFO, *LPRILUNSOLICITEDSSINFO
---

# RILUNSOLICITEDSSINFO_V2 structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILUNSOLICITEDSSINFO_V2 {
  DWORD                                 cbSize;
  DWORD                                 dwParams;
  DWORD                                 dwExecutor;
  DWORD                                 dwID;
  RILUNSOLICITEDSSINFONOTIFICATIONCODE  dwNotificationCode;
  RILADDRESS                            raAddress;
  RILSUBADDRESS                         rsaSubAddress;
  DWORD                                 dwCUGIndex;
  DWORD                                 dwHistorynfoLength;
  WCHAR [1]                             wszHistoryInfo;
} RILUNSOLICITEDSSINFO_V2, RILUNSOLICITEDSSINFO_V2;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwExecutor


### -field dwID


### -field dwNotificationCode


### -field raAddress


### -field rsaSubAddress


### -field dwCUGIndex


### -field dwHistorynfoLength


### -field wszHistoryInfo

