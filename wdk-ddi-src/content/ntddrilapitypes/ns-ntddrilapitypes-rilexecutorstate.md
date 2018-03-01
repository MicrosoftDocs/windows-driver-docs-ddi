---
UID: NS:ntddrilapitypes.RILEXECUTORSTATE
title: RILEXECUTORSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilexecutorstate.htm
old-project: netvista
ms.assetid: 3d820c24-6f07-4ba2-b2e3-f3c799c6a1ef
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILEXECUTORSTATE, RILEXECUTORSTATE, RILEXECUTORSTATE structure [Network Drivers Starting with Windows Vista], netvista.rilexecutorstate, ntddrilapitypes/RILEXECUTORSTATE"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddrilapitypes.h
api_name:
-	RILEXECUTORSTATE
product: Windows
targetos: Windows
req.typenames: RILEXECUTORSTATE, *LPRILEXECUTORSTATE
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

