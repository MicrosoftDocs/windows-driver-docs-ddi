---
UID: NS:rilapitypes.RILUNSOLICITEDSSINFO_V1
title: RILUNSOLICITEDSSINFO_V1
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilunsolicitedssinfo_v1_2.htm
old-project: netvista
ms.assetid: 37bd1dcd-3cf1-46af-847d-200d0c04167d
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*LPRILUNSOLICITEDSSINFO_V1, RILUNSOLICITEDSSINFO_V1, rilapitypes/RILUNSOLICITEDSSINFO_V1, netvista.rilunsolicitedssinfo_v1_2, RILUNSOLICITEDSSINFO_V1 structure [Network Drivers Starting with Windows Vista]"
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
-	RILUNSOLICITEDSSINFO_V1
product: Windows
targetos: Windows
req.typenames: "*LPRILUNSOLICITEDSSINFO_V1, RILUNSOLICITEDSSINFO_V1"
req.product: Windows 10 or later.
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


