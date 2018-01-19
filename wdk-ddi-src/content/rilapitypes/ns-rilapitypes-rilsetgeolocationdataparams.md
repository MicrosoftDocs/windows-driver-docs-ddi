---
UID: NS:rilapitypes.RILSETGEOLOCATIONDATAPARAMS
title: RILSETGEOLOCATIONDATAPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetgeolocationdataparams_2.htm
old-project: netvista
ms.assetid: 4e0d035b-5528-4e69-bd6c-9311bf0af4cf
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILSETGEOLOCATIONDATAPARAMS, *LPRILSETGEOLOCATIONDATAPARAMS, RILSETGEOLOCATIONDATAPARAMS
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
req.alt-api: RILSETGEOLOCATIONDATAPARAMS
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
req.typenames: *LPRILSETGEOLOCATIONDATAPARAMS, RILSETGEOLOCATIONDATAPARAMS
req.product: Windows 10 or later.
---

# RILSETGEOLOCATIONDATAPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILSETGEOLOCATIONDATAPARAMS {
  DWORD                 cbSize;
  DWORD                 dwExecutor;
  RILOSGEOLOCATIONINFO  locationInfo;
} RILSETGEOLOCATIONDATAPARAMS, RILSETGEOLOCATIONDATAPARAMS;
````


## -struct-fields

### -field cbSize


### -field dwExecutor


### -field locationInfo


## -remarks
