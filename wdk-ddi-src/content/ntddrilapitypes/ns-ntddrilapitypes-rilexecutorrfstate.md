---
UID: NS:ntddrilapitypes.RILEXECUTORRFSTATE
title: RILEXECUTORRFSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilexecutorrfstate.htm
old-project: netvista
ms.assetid: b56f71c3-3c24-4f6b-ba50-203e17374c81
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILEXECUTORRFSTATE structure [Network Drivers Starting with Windows Vista], ntddrilapitypes/RILEXECUTORRFSTATE, *LPRILEXECUTORRFSTATE, netvista.rilexecutorrfstate, RILEXECUTORRFSTATE
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
-	RILEXECUTORRFSTATE
product: Windows
targetos: Windows
req.typenames: "*LPRILEXECUTORRFSTATE, RILEXECUTORRFSTATE"
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




#### - cbSize



#### - dwParams



#### - dwExecutor



#### - fExecutorRFState


