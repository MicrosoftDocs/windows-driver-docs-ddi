---
UID: NS:rilapitypes.RILNOTIFICATIONPARAMS
title: RILNOTIFICATIONPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilnotificationparams_2.htm
old-project: netvista
ms.assetid: 25a67292-b6fd-448a-a7bd-2867b3f46f13
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILNOTIFICATIONPARAMS, RILNOTIFICATIONPARAMS structure [Network Drivers Starting with Windows Vista], rilapitypes/RILNOTIFICATIONPARAMS, netvista.rilnotificationparams_2, *LPRILNOTIFICATIONPARAMS
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
-	RILNOTIFICATIONPARAMS
product: Windows
targetos: Windows
req.typenames: RILNOTIFICATIONPARAMS, *LPRILNOTIFICATIONPARAMS
req.product: Windows 10 or later.
---

# RILNOTIFICATIONPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILNOTIFICATIONPARAMS {
  DWORD     dwNotificationCount;
  DWORD [1] pdwNotifications;
} RILNOTIFICATIONPARAMS, RILNOTIFICATIONPARAMS;
````


## -struct-fields




### -field dwNotificationCount



### -field pdwNotifications


