---
UID: NS:ntddrilapitypes.RILGETCALLBARRINGSTATUSPARAMS
title: RILGETCALLBARRINGSTATUSPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetcallbarringstatusparams.htm
old-project: netvista
ms.assetid: ce4ff193-1699-4712-93c1-c623474e1993
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILGETCALLBARRINGSTATUSPARAMS, *LPRILGETCALLBARRINGSTATUSPARAMS, RILGETCALLBARRINGSTATUSPARAMS
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
req.alt-api: RILGETCALLBARRINGSTATUSPARAMS
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
req.typenames: *LPRILGETCALLBARRINGSTATUSPARAMS, RILGETCALLBARRINGSTATUSPARAMS
---

# RILGETCALLBARRINGSTATUSPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILGETCALLBARRINGSTATUSPARAMS {
  DWORD                           dwExecutor;
  RILCALLBARRINGSTATUSPARAMSTYPE  dwType;
  BOOL                            fAllClasses;
  DWORD                           dwInfoClasses;
} RILGETCALLBARRINGSTATUSPARAMS, RILGETCALLBARRINGSTATUSPARAMS;
````


## -struct-fields

### -field dwExecutor


### -field dwType


### -field fAllClasses


### -field dwInfoClasses


## -remarks
