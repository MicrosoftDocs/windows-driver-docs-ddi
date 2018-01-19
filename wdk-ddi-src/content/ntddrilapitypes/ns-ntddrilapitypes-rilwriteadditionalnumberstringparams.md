---
UID: NS:ntddrilapitypes.RILWRITEADDITIONALNUMBERSTRINGPARAMS
title: RILWRITEADDITIONALNUMBERSTRINGPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilwriteadditionalnumberstringparams.htm
old-project: netvista
ms.assetid: 2adcf421-c651-46a5-b82a-db62591e69f0
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILWRITEADDITIONALNUMBERSTRINGPARAMS, RILWRITEADDITIONALNUMBERSTRINGPARAMS, *LPRILWRITEADDITIONALNUMBERSTRINGPARAMS
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
req.alt-api: RILWRITEADDITIONALNUMBERSTRINGPARAMS
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
req.typenames: RILWRITEADDITIONALNUMBERSTRINGPARAMS, *LPRILWRITEADDITIONALNUMBERSTRINGPARAMS
---

# RILWRITEADDITIONALNUMBERSTRINGPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILWRITEADDITIONALNUMBERSTRINGPARAMS {
  HUICCAPP                            hUiccApp;
  RILPHONEBOOKADDITIONALNUMBERSTRING  RilPBANS;
} RILWRITEADDITIONALNUMBERSTRINGPARAMS, RILWRITEADDITIONALNUMBERSTRINGPARAMS;
````


## -struct-fields

### -field hUiccApp


### -field RilPBANS


## -remarks
