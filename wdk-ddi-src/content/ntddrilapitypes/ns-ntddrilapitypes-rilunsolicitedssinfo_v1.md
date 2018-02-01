---
UID: NS:ntddrilapitypes.RILUNSOLICITEDSSINFO_V1
title: RILUNSOLICITEDSSINFO_V1
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilunsolicitedssinfo_v1.htm
old-project: netvista
ms.assetid: c9681207-6cdd-40b6-8878-7ea37f383e4f
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*LPRILUNSOLICITEDSSINFO_V1, RILUNSOLICITEDSSINFO_V1, netvista.rilunsolicitedssinfo_v1, ntddrilapitypes/RILUNSOLICITEDSSINFO_V1, RILUNSOLICITEDSSINFO_V1 structure [Network Drivers Starting with Windows Vista]"
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
-	RILUNSOLICITEDSSINFO_V1
product: Windows
targetos: Windows
req.typenames: "*LPRILUNSOLICITEDSSINFO_V1, RILUNSOLICITEDSSINFO_V1"
---

# RILUNSOLICITEDSSINFO_V1 structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILUNSOLICITEDSSINFO_V1 {
  DWORD                                 cbSize;
  DWORD                                 dwParams;
  DWORD                                 dwExecutor;
  DWORD                                 dwID;
  RILUNSOLICITEDSSINFONOTIFICATIONCODE  dwNotificationCode;
  RILADDRESS                            raAddress;
  RILSUBADDRESS                         rsaSubAddress;
  DWORD                                 dwCUGIndex;
} RILUNSOLICITEDSSINFO_V1, RILUNSOLICITEDSSINFO_V1;
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


