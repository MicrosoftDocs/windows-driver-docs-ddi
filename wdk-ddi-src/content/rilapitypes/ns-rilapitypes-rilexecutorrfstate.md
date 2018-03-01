---
UID: NS:rilapitypes.RILEXECUTORRFSTATE
title: RILEXECUTORRFSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilexecutorrfstate_2.htm
old-project: netvista
ms.assetid: 7a9e4b9a-f166-41bc-9525-8539ca8864f5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILEXECUTORRFSTATE, RILEXECUTORRFSTATE, RILEXECUTORRFSTATE structure [Network Drivers Starting with Windows Vista], netvista.rilexecutorrfstate_2, rilapitypes/RILEXECUTORRFSTATE"
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
-	RILEXECUTORRFSTATE
product: Windows
targetos: Windows
req.typenames: RILEXECUTORRFSTATE, *LPRILEXECUTORRFSTATE
req.product: Windows 10 or later.
---

# RILEXECUTORRFSTATE structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILEXECUTORRFSTATE {
  DWORD  cbSize;
  DWORD  dwParams;
  DWORD  dwExecutor;
  BOOL   fExecutorRFState;
} RILEXECUTORRFSTATE, RILEXECUTORRFSTATE;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwExecutor


### -field fExecutorRFState

