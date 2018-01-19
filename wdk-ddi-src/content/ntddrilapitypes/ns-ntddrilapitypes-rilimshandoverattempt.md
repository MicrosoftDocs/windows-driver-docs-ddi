---
UID: NS:ntddrilapitypes.RILIMSHANDOVERATTEMPT
title: RILIMSHANDOVERATTEMPT
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimshandoverattempt.htm
old-project: netvista
ms.assetid: 22491e3c-fa23-473d-b3e6-92c776b81204
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILIMSHANDOVERATTEMPT, RILIMSHANDOVERATTEMPT, *LPRILIMSHANDOVERATTEMPT
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
req.alt-api: RILIMSHANDOVERATTEMPT
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
req.typenames: RILIMSHANDOVERATTEMPT, *LPRILIMSHANDOVERATTEMPT
---

# RILIMSHANDOVERATTEMPT structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILIMSHANDOVERATTEMPT {
  DWORD             cbSize;
  RILIMSSYSTEMTYPE  dwOldSystemType;
  RILIMSSYSTEMTYPE  dwDestSystemType;
  HRESULT           hrHandOverResult;
} RILIMSHANDOVERATTEMPT, RILIMSHANDOVERATTEMPT;
````


## -struct-fields

### -field cbSize


### -field dwOldSystemType


### -field dwDestSystemType


### -field hrHandOverResult


## -remarks
