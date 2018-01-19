---
UID: NS:ntddrilapitypes.RILSETMSGINUICCSTATUSPARAMS
title: RILSETMSGINUICCSTATUSPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetmsginuiccstatusparams.htm
old-project: netvista
ms.assetid: 3c35e2e0-8f8a-456f-b0ce-494a050d11dc
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILSETMSGINUICCSTATUSPARAMS, RILSETMSGINUICCSTATUSPARAMS, *LPRILSETMSGINUICCSTATUSPARAMS
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
req.alt-api: RILSETMSGINUICCSTATUSPARAMS
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
req.typenames: RILSETMSGINUICCSTATUSPARAMS, *LPRILSETMSGINUICCSTATUSPARAMS
---

# RILSETMSGINUICCSTATUSPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILSETMSGINUICCSTATUSPARAMS {
  HUICCAPP          hUiccApp;
  DWORD             dwIndex;
  RILMESSAGESTATUS  dwStatus;
} RILSETMSGINUICCSTATUSPARAMS, RILSETMSGINUICCSTATUSPARAMS;
````


## -struct-fields

### -field hUiccApp


### -field dwIndex


### -field dwStatus


## -remarks
