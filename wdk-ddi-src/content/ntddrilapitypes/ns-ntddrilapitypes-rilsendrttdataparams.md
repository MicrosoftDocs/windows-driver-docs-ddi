---
UID: NS:ntddrilapitypes.RILSENDRTTDATAPARAMS
title: RILSENDRTTDATAPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsendrttdataparams.htm
old-project: netvista
ms.assetid: 733b8ccc-5335-4c7e-bfc0-4618b0b3a4d8
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILSENDRTTDATAPARAMS, *LPRILSENDRTTDATAPARAMS, RILSENDRTTDATAPARAMS
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
req.alt-api: RILSENDRTTDATAPARAMS
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
req.typenames: *LPRILSENDRTTDATAPARAMS, RILSENDRTTDATAPARAMS
---

# RILSENDRTTDATAPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILSENDRTTDATAPARAMS {
  DWORD       cbSize;
  DWORD       dwID;
  DWORD       dwExecutor;
  WCHAR [127] wszRTTText;
} RILSENDRTTDATAPARAMS, RILSENDRTTDATAPARAMS;
````


## -struct-fields

### -field cbSize


### -field dwID


### -field dwExecutor


### -field wszRTTText


## -remarks
