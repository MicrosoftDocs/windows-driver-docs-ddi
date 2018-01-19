---
UID: NS:ntddrilapitypes.RILSETCELLBROADCASTMSGCONFIGPARAMS
title: RILSETCELLBROADCASTMSGCONFIGPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetcellbroadcastmsgconfigparams.htm
old-project: netvista
ms.assetid: bfaad47a-44eb-471d-9ed9-e1adf845ab9c
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILSETCELLBROADCASTMSGCONFIGPARAMS, RILSETCELLBROADCASTMSGCONFIGPARAMS, *LPRILSETCELLBROADCASTMSGCONFIGPARAMS
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
req.alt-api: RILSETCELLBROADCASTMSGCONFIGPARAMS
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
req.typenames: RILSETCELLBROADCASTMSGCONFIGPARAMS, *LPRILSETCELLBROADCASTMSGCONFIGPARAMS
---

# RILSETCELLBROADCASTMSGCONFIGPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILSETCELLBROADCASTMSGCONFIGPARAMS {
  HUICCAPP        hUiccApp;
  RILCBMSGCONFIG  rmCBConfig;
} RILSETCELLBROADCASTMSGCONFIGPARAMS, RILSETCELLBROADCASTMSGCONFIGPARAMS;
````


## -struct-fields

### -field hUiccApp


### -field rmCBConfig


## -remarks
