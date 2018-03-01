---
UID: NS:rilapitypes.RILEXECUTORSTATE
title: RILEXECUTORSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilexecutorstate_2.htm
old-project: netvista
ms.assetid: 1333c13b-5d39-4143-a7ab-8425528eb4c9
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILEXECUTORSTATE, RILEXECUTORSTATE, RILEXECUTORSTATE structure [Network Drivers Starting with Windows Vista], netvista.rilexecutorstate_2, rilapitypes/RILEXECUTORSTATE"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILEXECUTORSTATE
product: Windows
targetos: Windows
req.typenames: RILEXECUTORSTATE, *LPRILEXECUTORSTATE
req.product: Windows 10 or later.
---

# RILEXECUTORSTATE structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILEXECUTORSTATE {
  DWORD  cbSize;
  DWORD  dwExecutor;
  DWORD  dwFlags;
} RILEXECUTORSTATE, RILEXECUTORSTATE;
````


## -struct-fields




### -field cbSize


### -field dwExecutor


### -field dwFlags

