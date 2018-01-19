---
UID: NS:ntddrilapitypes.RILSETSMSCPARAMS
title: RILSETSMSCPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetsmscparams.htm
old-project: netvista
ms.assetid: ebfb768a-fa6b-4781-96e1-787278237d5f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILSETSMSCPARAMS, RILSETSMSCPARAMS, *LPRILSETSMSCPARAMS
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
req.alt-api: RILSETSMSCPARAMS
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
req.typenames: RILSETSMSCPARAMS, *LPRILSETSMSCPARAMS
---

# RILSETSMSCPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILSETSMSCPARAMS {
  HUICCAPP    hUiccApp;
  RILADDRESS  raSvcCtrAddress;
} RILSETSMSCPARAMS, RILSETSMSCPARAMS;
````


## -struct-fields

### -field hUiccApp


### -field raSvcCtrAddress


## -remarks
