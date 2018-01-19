---
UID: NS:rilapitypes.RILGETDRIVERVERSIONPARAMS
title: RILGETDRIVERVERSIONPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetdriverversionparams_2.htm
old-project: netvista
ms.assetid: b396b12e-f8c4-4e5e-b3c4-9822bcd996a4
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILGETDRIVERVERSIONPARAMS, RILGETDRIVERVERSIONPARAMS, *LPRILGETDRIVERVERSIONPARAMS
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
req.alt-api: RILGETDRIVERVERSIONPARAMS
req.alt-loc: rilapitypes.h
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
req.product: Windows 10 or later.
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
