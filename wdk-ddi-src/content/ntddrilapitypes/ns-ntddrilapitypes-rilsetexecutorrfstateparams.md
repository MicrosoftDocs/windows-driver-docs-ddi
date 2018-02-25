---
UID: NS:ntddrilapitypes.RILSETEXECUTORRFSTATEPARAMS
title: RILSETEXECUTORRFSTATEPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetexecutorrfstateparams.htm
old-project: netvista
ms.assetid: d7f36cbd-56bb-470e-b965-369b9e49f5e2
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *LPRILSETEXECUTORRFSTATEPARAMS, ,, A, C, E, F, I, L, M, O, P, R, RILSETEXECUTORRFSTATEPARAMS, RILSETEXECUTORRFSTATEPARAMS structure [Network Drivers Starting with Windows Vista], S, T, U, X, netvista.rilsetexecutorrfstateparams, ntddrilapitypes/RILSETEXECUTORRFSTATEPARAMS"
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
-	RILSETEXECUTORRFSTATEPARAMS
product: Windows
targetos: Windows
req.typenames: RILSETEXECUTORRFSTATEPARAMS, *LPRILSETEXECUTORRFSTATEPARAMS
---

# RILSETEXECUTORRFSTATEPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILSETEXECUTORRFSTATEPARAMS {
  DWORD  dwExecutor;
  BOOL   fExecutorRFState;
} RILSETEXECUTORRFSTATEPARAMS, RILSETEXECUTORRFSTATEPARAMS;
````


## -struct-fields




### -field dwExecutor


### -field fExecutorRFState

