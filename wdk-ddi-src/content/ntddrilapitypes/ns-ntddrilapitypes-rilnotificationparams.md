---
UID: NS:ntddrilapitypes.RILNOTIFICATIONPARAMS
title: RILNOTIFICATIONPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilnotificationparams.htm
old-project: netvista
ms.assetid: c89c7df3-7ccb-46db-adcc-22c49cae5108
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILNOTIFICATIONPARAMS, RILNOTIFICATIONPARAMS, *LPRILNOTIFICATIONPARAMS
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
req.alt-api: RILNOTIFICATIONPARAMS
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
req.typenames: RILNOTIFICATIONPARAMS, *LPRILNOTIFICATIONPARAMS
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


## -remarks
