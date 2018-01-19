---
UID: NS:rilapitypes.RILUNSOLICITEDSSINFO_V2
title: RILUNSOLICITEDSSINFO_V2
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilunsolicitedssinfo_v2_2.htm
old-project: netvista
ms.assetid: 1c59c4fa-610e-4200-a94a-2c28754dfe43
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILUNSOLICITEDSSINFO_V2, RILUNSOLICITEDSSINFO_V2, *LPRILUNSOLICITEDSSINFO_V2, *LPRILUNSOLICITEDSSINFO, RILUNSOLICITEDSSINFO
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
req.alt-api: RILUNSOLICITEDSSINFO_V2
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
req.typenames: RILUNSOLICITEDSSINFO_V2, *LPRILUNSOLICITEDSSINFO_V2, *LPRILUNSOLICITEDSSINFO, RILUNSOLICITEDSSINFO
req.product: Windows 10 or later.
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


## -remarks
