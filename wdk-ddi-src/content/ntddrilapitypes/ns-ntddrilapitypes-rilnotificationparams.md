---
UID: NS:ntddrilapitypes.RILNOTIFICATIONPARAMS
title: RILNOTIFICATIONPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilnotificationparams.htm
old-project: netvista
ms.assetid: c89c7df3-7ccb-46db-adcc-22c49cae5108
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILNOTIFICATIONPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilnotificationparams, ntddrilapitypes/RILNOTIFICATIONPARAMS, *LPRILNOTIFICATIONPARAMS, RILNOTIFICATIONPARAMS
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
-	RILNOTIFICATIONPARAMS
product: Windows
targetos: Windows
req.typenames: "*LPRILNOTIFICATIONPARAMS, RILNOTIFICATIONPARAMS"
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

