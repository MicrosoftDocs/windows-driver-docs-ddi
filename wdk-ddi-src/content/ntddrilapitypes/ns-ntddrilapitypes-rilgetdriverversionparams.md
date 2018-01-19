---
UID: NS:ntddrilapitypes.RILGETDRIVERVERSIONPARAMS
title: RILGETDRIVERVERSIONPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetdriverversionparams.htm
old-project: netvista
ms.assetid: 42167f2f-0bd5-452c-9b41-d18efac28a33
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILGETDRIVERVERSIONPARAMS, RILGETDRIVERVERSIONPARAMS, *LPRILGETDRIVERVERSIONPARAMS
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
req.alt-api: RILGETDRIVERVERSIONPARAMS
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
req.typenames: RILGETDRIVERVERSIONPARAMS, *LPRILGETDRIVERVERSIONPARAMS
---

# RILGETDRIVERVERSIONPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILGETDRIVERVERSIONPARAMS {
  DWORD  dwMinVersion;
  DWORD  dwMaxVersion;
} RILGETDRIVERVERSIONPARAMS, RILGETDRIVERVERSIONPARAMS;
````


## -struct-fields

### -field dwMinVersion


### -field dwMaxVersion


## -remarks
