---
UID: NS:rilapitypes.RILWRITEMSGPARAMS
title: RILWRITEMSGPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilwritemsgparams_2.htm
old-project: netvista
ms.assetid: 7221efdc-1751-4539-9dc1-5ba3cd40c5ce
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILWRITEMSGPARAMS, RILWRITEMSGPARAMS, *LPRILWRITEMSGPARAMS
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
req.alt-api: RILWRITEMSGPARAMS
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
req.typenames: RILWRITEMSGPARAMS, *LPRILWRITEMSGPARAMS
req.product: Windows 10 or later.
---

# RILWRITEMSGPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILWRITEMSGPARAMS {
  HUICCAPP          hUiccApp;
  RILMESSAGE        rmMessage;
  RILMESSAGESTATUS  dwStatus;
} RILWRITEMSGPARAMS, RILWRITEMSGPARAMS;
````


## -struct-fields

### -field hUiccApp


### -field rmMessage


### -field dwStatus


## -remarks
