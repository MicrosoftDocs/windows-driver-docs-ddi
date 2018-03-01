---
UID: NS:rilapitypes.RILSETEXECUTORRFSTATEPARAMS
title: RILSETEXECUTORRFSTATEPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetexecutorrfstateparams.htm
old-project: netvista
ms.assetid: d7f36cbd-56bb-470e-b965-369b9e49f5e2
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILSETEXECUTORRFSTATEPARAMS, RILSETEXECUTORRFSTATEPARAMS, RILSETEXECUTORRFSTATEPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilsetexecutorrfstateparams, ntddrilapitypes/RILSETEXECUTORRFSTATEPARAMS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
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




### -field dwExecutor


### -field fExecutorRFState

