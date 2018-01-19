---
UID: NS:rilapitypes.RILSMSREADYSTATUS
title: RILSMSREADYSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsmsreadystatus_2.htm
old-project: netvista
ms.assetid: a7039749-3f7d-4eca-919c-db27f9e62bf2
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILSMSREADYSTATUS, *LPRILSMSREADYSTATUS, RILSMSREADYSTATUS
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
req.alt-api: RILSMSREADYSTATUS
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
req.typenames: *LPRILSMSREADYSTATUS, RILSMSREADYSTATUS
req.product: Windows 10 or later.
---

# RILSMSREADYSTATUS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILSMSREADYSTATUS {
  DWORD             cbSize;
  DWORD             dwParams;
  DWORD             dwExecutor;
  RILSMSREADYSTATE  dwReadyState;
} RILSMSREADYSTATUS, RILSMSREADYSTATUS;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwExecutor


### -field dwReadyState


## -remarks
