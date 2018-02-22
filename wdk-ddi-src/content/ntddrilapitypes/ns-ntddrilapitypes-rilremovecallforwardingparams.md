---
UID: NS:ntddrilapitypes.RILREMOVECALLFORWARDINGPARAMS
title: RILREMOVECALLFORWARDINGPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilremovecallforwardingparams.htm
old-project: netvista
ms.assetid: f6eaaa56-8444-496b-8b14-63bb2368d6ba
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILREMOVECALLFORWARDINGPARAMS, netvista.rilremovecallforwardingparams, ntddrilapitypes/RILREMOVECALLFORWARDINGPARAMS, RILREMOVECALLFORWARDINGPARAMS structure [Network Drivers Starting with Windows Vista], *LPRILREMOVECALLFORWARDINGPARAMS
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
-	RILREMOVECALLFORWARDINGPARAMS
product: Windows
targetos: Windows
req.typenames: RILREMOVECALLFORWARDINGPARAMS, *LPRILREMOVECALLFORWARDINGPARAMS
---

# RILREMOVECALLFORWARDINGPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILREMOVECALLFORWARDINGPARAMS {
  DWORD                            dwExecutor;
  RILCALLFORWARDINGSETTINGSREASON  dwReason;
  DWORD                            dwInfoClasses;
} RILREMOVECALLFORWARDINGPARAMS, RILREMOVECALLFORWARDINGPARAMS;
````


## -struct-fields




### -field dwExecutor


### -field dwReason


### -field dwInfoClasses

