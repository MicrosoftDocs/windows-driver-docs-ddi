---
UID: NS:rilapitypes.RILSETEXECUTORRFSTATEPARAMS
title: RILSETEXECUTORRFSTATEPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetexecutorrfstateparams_2.htm
old-project: netvista
ms.assetid: c1638b6e-7270-4511-a0bb-3766dbd6c6f5
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilsetexecutorrfstateparams_2, *LPRILSETEXECUTORRFSTATEPARAMS, rilapitypes/RILSETEXECUTORRFSTATEPARAMS, RILSETEXECUTORRFSTATEPARAMS structure [Network Drivers Starting with Windows Vista], RILSETEXECUTORRFSTATEPARAMS
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
-	RILSETEXECUTORRFSTATEPARAMS
product: Windows
targetos: Windows
req.typenames: RILSETEXECUTORRFSTATEPARAMS, *LPRILSETEXECUTORRFSTATEPARAMS
req.product: Windows 10 or later.
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




#### - dwExecutor



#### - fExecutorRFState


