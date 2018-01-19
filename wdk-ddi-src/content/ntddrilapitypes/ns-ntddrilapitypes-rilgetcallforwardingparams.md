---
UID: NS:ntddrilapitypes.RILGETCALLFORWARDINGPARAMS
title: RILGETCALLFORWARDINGPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetcallforwardingparams.htm
old-project: netvista
ms.assetid: 94e24172-a149-4e74-9600-2fcb7396ef34
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILGETCALLFORWARDINGPARAMS, *LPRILGETCALLFORWARDINGPARAMS, RILGETCALLFORWARDINGPARAMS
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
req.alt-api: RILGETCALLFORWARDINGPARAMS
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
req.typenames: *LPRILGETCALLFORWARDINGPARAMS, RILGETCALLFORWARDINGPARAMS
---

# RILGETCALLFORWARDINGPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILGETCALLFORWARDINGPARAMS {
  DWORD                            dwExecutor;
  RILCALLFORWARDINGSETTINGSREASON  dwReason;
  BOOL                             fAllClasses;
  DWORD                            dwInfoClasses;
} RILGETCALLFORWARDINGPARAMS, RILGETCALLFORWARDINGPARAMS;
````


## -struct-fields

### -field dwExecutor


### -field dwReason


### -field fAllClasses


### -field dwInfoClasses


## -remarks
