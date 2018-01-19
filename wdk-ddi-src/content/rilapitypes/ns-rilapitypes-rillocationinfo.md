---
UID: NS:rilapitypes.RILLOCATIONINFO
title: RILLOCATIONINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rillocationinfo_2.htm
old-project: netvista
ms.assetid: 057f8cb0-0473-470e-b993-457de90d98fd
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILLOCATIONINFO, RILLOCATIONINFO, *LPRILLOCATIONINFO
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
req.alt-api: RILLOCATIONINFO
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
req.typenames: RILLOCATIONINFO, *LPRILLOCATIONINFO
req.product: Windows 10 or later.
---

# RILLOCATIONINFO structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILLOCATIONINFO {
  DWORD  cbSize;
  DWORD  dwParams;
  DWORD  dwExecutor;
  DWORD  hUiccApp;
  DWORD  dwLocationAreaCode;
  DWORD  dwTrackingAreaCode;
  DWORD  dwCellID;
} RILLOCATIONINFO, RILLOCATIONINFO;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwExecutor


### -field hUiccApp


### -field dwLocationAreaCode


### -field dwTrackingAreaCode


### -field dwCellID


## -remarks
